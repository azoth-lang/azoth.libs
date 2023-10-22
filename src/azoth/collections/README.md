# `azoth.collections`

## Planned

* `Bag[T]`: hash based and order based (order based is a sorted list?)
* `Set[T]`: hash based and order based
* `Dictionary[T, V]`: hash based and order based
* Concurrent Collections
* [Persistent Data Structures](https://en.wikipedia.org/wiki/Persistent_data_structure)
* `Queue[T]`
* `IndexableQueue[T]`: a queue that allows random read access
* `IndexableStack[T]`: a stack that allows random read access
* `Deque[T]`
* `PriorityQueue<E>` (heap and double-ended heap)
* Multimap (better name?)
* Iteration Direction
* BitList
* BitArray
* DisjointSet/UnionFind
* Specialized
  * `Buffer[T]`: struct used as the basis of implementations like `List[T]`?
  * `RingBuffer[T]`: struct used as the basis of implementations like `Deque[T]`?

## Ideas

* `IndexableCollection[T]`
* `SortedCollection[T]`
* Snapshotting?
* BoundedQueue and BoundedPriorityQueue
* BoundedList
