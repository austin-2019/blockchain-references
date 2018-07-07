#### https://medium.com/@lhartikk/a-blockchain-in-200-lines-of-code-963cc1cc0e54
#### A blockchain in 200 lines of code

#### EXCERPTS From the article by Lauri Hartikka | Mar 4, 2017

![](images/200-linescode-A.png)



        class Block {
            constructor(index, previousHash, timestamp, data, hash) {
                this.index = index;
                this.previousHash = previousHash.toString();
                this.timestamp = timestamp;
                this.data = data;
                this.hash = hash.toString();
            }
        }

#### The block needs to be hashed to keep the integrity of the data. A SHA-256 is taken over the content of the block. It should be noted that this hash has nothing to do with “mining”, since there is no Proof Of Work problem to solve.

        var calculateHash = (index, previousHash, timestamp, data) => {
            return CryptoJS.SHA256(index + previousHash + timestamp + data).toString();
        };
