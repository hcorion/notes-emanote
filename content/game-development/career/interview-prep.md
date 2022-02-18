---
date: 2022-02-16T23:01
tags:
  - career
  - unity
  - unreal
---

# Interview Prep

## Software Engineering        
- **Q:** Implement a Dictionary

	**A:** Dictionary looks something like this
  ```csharp
  ///
  List<V> items;
  
  public V Get(K key)
  {
  	hashCode = GetHashCode(key);
  }
  ```
## C++
- **Q:** What is the Big O of C++ STL containers

	**A:** [Source of information](https://web.archive.org/web/20190821171108/https://users.cs.northwestern.edu/~riesbeck/programming/c++/stl-summary.html)
    
    - `vector<T>` (C#: `List<T>`)
    	- construct: O(1)
        - construct with N elements: O(n)
        - Accessor: O(1)
        - insert: O(n)
        - push_back O(1)
        - pop_back: O(1)
    - `deque<T>` (C#: `Queue<T>`)
    	- construct: O(1)
        - construct with N elements: O(n)
        - Accessor: O(1)
        - insert: O(n)
        - push_front: O(1)
        - push_back: O(1)
        - pop_front: O(1)
        - pop_back: O(1)
    - `list<T>` (doubly linked list) (C#: `LinkedList<T>`)
    	- construct: O(1)
        - construct with N elements: O(n)
        - Index Accessor: O(n)
        - begin: O(1)
        - end: O(1)
        - front: O(1)
        - back: O(1)
        - push_front: O(1)
        - push_back: O(1)
        - insert(iterator, x): O(1)
        - pop_front: O(1)
        - pop_back: O(1)
        - remove(value): O(n)
        - reverse: O(n)
        - sort: O(n log n)
        - merge(list2): O(n)
    - `stack<container<T>>` (C#: `Stack<T>`)
    	- construct: O(1)
        - top: (1)
        - Index Accessor: O(n)
        - push(value): Same as `push_back` for underlying `container`
        - pop: O(1)
    - `set<T>`/`multiset<T>` (C#: `HashSet<T>`/no equivalent for `multiset`)
    	- **Note:** `multiset` is a set which allows duplicate keys
        - construct: O(1)
        - construct with values: O(n log n)
        - find: O(log n)
        - lower_bound: O(log n)
        - upper_bound: O(log n)
        - equal_range: O(log n)
        - count(key): O(log n) (only useful in multiset)
        - size: O(1)
    - `map<K, V>`/`multimap<K, V>` (C#: `Dictionary<K,V>`/no equivalent for `multimap`)
    	- **Note:** `multimap` is a map which allows duplicate keys

## Unreal Engine

- - **Q:** What are the main Unreal container types?

	**A:**
    - 

## Unity
