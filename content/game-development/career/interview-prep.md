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
- **Q:** Heap vs Stack

	**A:** Stack is where local variables and structs get stored/used, getting stuff from the stack is usually really fast, since it's usually stored on the CPU cache.
    
    Heap is where classes/objects get allocated, and is stored on the RAM, but the CPU can store it on the local cache if it decides to do so. Heap is generally slower than the stack, but you have a lot more space 

- **Q:** Classes vs Struct

	**A:** 
- **Q:** What is memory fragmentation?

	**A:** 
- **Q:** What is a cache miss?

	**A:** 
- **Q:** How does a garbage collector work?

	**A:** 
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
        - top: O(1)
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
- **Q:** What are the performance considerations of virtual functions in C++?

	**A:** 

## Unreal Engine

- **Q:** What are the main Unreal container types?

	**A:**
    - [Unreal Containers Documentation](https://docs.unrealengine.com/5.0/en-US/API/Runtime/Core/Containers/)
    - `FBitSet<>` (C# )
- **Q:** What are the Unreal string types and their purposes?

	**A:**
    - [`FString`](https://docs.unrealengine.com/5.0/en-US/API/Runtime/Core/Containers/FString/)
      - Standard dynamically sizeable string, similar to a c++ `std::string` or C# `string`
      - Format function:
        ```cpp
        TArray< FStringFormatArg > args;
        args.Add( FStringFormatArg( name ) );
        args.Add( FStringFormatArg( mana ) );
        FString string = FString::Format( TEXT( "Name = {0} Mana = {1}" ), args );
        ```
    - [`FName`](https://docs.unrealengine.com/5.0/en-US/API/Runtime/Core/UObject/FName/)
      - Case-insensitive (but case-preserving (when WITH_CASE_PRESERVING_NAME is 1)
    - [`FText`](https://docs.unrealengine.com/4.27/en-US/ProgrammingAndScripting/ProgrammingWithCPP/UnrealArchitecture/StringHandling/FText/)
      - Used for text localization
      - What you want to expose to designers or use in UI
      - Can be converted to and from FString
      - Format function: 
        ```csharp
        FText::Format(LOCTEXT("ExampleFText", "You currently have {0} health left."), CurrentHealth);
        ```
- **Q:** What are the common UPROPERTY and UCLASS meta properties?

	**A:**
    - d
- **Q:** How to use `UInterface`?

	**A:**
    - Implementing a `UInterface`
    - Checking if a class implements an `UInterface`
- **Q:** How do you create events/delegates?

	**A:**
    - Delegate bound to UFUNCTION
    - Unregistering delegate
    - Delegate that takes input param
    - Passing a payload with a delegate binding
    - Creating a multicast delegate
    - Creating a custom Event
- **Q:** How to use managed memory with Unreal?

	**A:**
    - Allocating:
      - `NewObject<>`:
        - 
      - `ConstructObject<>`
        - d
    - De-allocating
      - d
    - `UPROPERTY` and GC
      - Forcing GC
- **Q:** How to use unmanaged memory with Unreal?

	**A:**
    - Allocating:
      - `malloc`/`new`
    - De-allocating
      - `free`/`delete`
- **Q:** What are the Unreal smart pointers?

	**A:**
    - `TSharedPtr<T>`
      - D
    - `TWeakPtr<T>`
      - D
    - `TAutoPtr<T>`
      - D
    - `TScopedPtr<T>`


## Unity
- **Q:** What is boxing in C#?

	**A:**
    - 