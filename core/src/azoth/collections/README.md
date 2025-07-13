# `azoth.collections`

## Planned

* `Bag[T]`: hash based and order based (order based is a sorted list?)
  * They are hash based or order based since they store items with a count. Perhaps there is another collection that just stores items unordered.
* `Set[T]`: hash based and order based
* `Dictionary[T, V]`: hash based and order based
* Concurrent Collections
* [Persistent Data Structures](https://en.wikipedia.org/wiki/Persistent_data_structure)
* `Queue[T]`
* `Indexable_Queue[T]`: a queue that allows random read access
* `Indexable_Stack[T]`: a stack that allows random read access
* `Deque[T]`
* `Priority_Queue<E>` (heap and double-ended heap)
* Multimap (better name?)
* Iteration Direction
* BitList
* BitArray
* DisjointSet/UnionFind
* Specialized
  * `Buffer[T]`: struct used as the basis of implementations like `List[T]`?
  * `Ring_Buffer[T]`: struct used as the basis of implementations like `Deque[T]`?

## Ideas

* `Sorted_Collection[T]`
* Snapshotting?
* BoundedQueue and BoundedPriorityQueue
* BoundedList
* Trait for collections backed by `Buffer` or `RingBuffer` that has methods for managing capacity?
