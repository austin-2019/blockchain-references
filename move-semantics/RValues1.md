#### C++ Rvalue references and move semantics
#### https://stackoverflow.com/questions/9498381/c-rvalue-references-and-move-semantics

#### IMPORTANT EXCERPTS

##### The problem comes up a lot. Someone I want to hold onto a unique copy of an object that no one else can modify. How do I do that?
1. Make a deep copy of whatever object someone gives me? That would work, but it's not efficient.
1. Ask people to give me a new object and not to keep a copy? That's faster if you're brave. Bugs can come from a completely unrelated piece of code modifying the object hours later.
1. C++ style: Move all the items from the input to my own new object. If the caller accidentally tries to use the object again,  he will immediately see the problem.
1. Sometimes a C# read only collection can help. But in my experiences that's usually a pain at best.

##### Here's what I'm talking about:

        class LongLivedObject
        {
            private Dictionary <string, string> _settings;
            public LongLivedObject(Dictionary <string, string> settings)
            {   // In C# this always duplicates the data structure and takes O(n) time.
                // C++ will automatically try to decide if it could do a swap instead.
                // C++ always lets you explicitly say you want to do the swap.
                _settings = new Dictionary <string, string>(settings);
            }
        }
        
##### This question is at the heart of Clojure and other functional languages!

##### In summary, yes, I often wish I had C++11 style data structures and operations in C#.

### RESPONSE

##### You can try to emulate move semantics. For instance in Trade-Ideas Philip's example you can pass custom MovableDictionary instead of Dictionary:

          public class MovableDictionary<K, V> // : IDictionary<K, V>, IReadOnlyDictionary<K, V>...
          {
              private Dictionary<K, V> _map;

              // Implement all Dictionary<T>'s methods by calling Map's ones.

              public Dictionary<K, V> Move()
              {
                  var result = Map;
                  _map = null;
                  return result;
              }

              private Dictionary<K, V> Map
              {
                  get
                  {
                      if (_map == null)
                          _map = new Dictionary<K, V>();

                      return _map;
                  }
              }
          }
