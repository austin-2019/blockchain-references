#### C++ Rvalue references and move semantics
#### https://stackoverflow.com/questions/9498381/c-rvalue-references-and-move-semantics

#### IMPORTANT EXCERPTS

##### The problem comes up a lot. Someone I want to hold onto a unique copy of an object that no one else can modify. How do I do that?
1. Make a deep copy of whatever object someone gives me? That would work, but it's not efficient.
1. Ask people to give me a new object and not to keep a copy? That's faster if you're brave. Bugs can come from a completely unrelated piece of code modifying the object hours later.
C++ style: Move all the items from the input to my own new object. If the caller accidentally tries to use the object again, 1. he will immediately see the problem.
1. Sometimes a C# read only collection can help. But in my experiences that's usually a pain at best.
