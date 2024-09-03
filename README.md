A `priority_queue` in C++ is a container adapter that provides constant time lookup of the largest (by default) element. A priority queue is a type of container in the C++ Standard Library, found in the `<queue>` header, that operates similarly to a heap. It is often implemented as a binary heap.

### Key Features of `priority_queue`:

1. **Automatic Ordering**:
   - By default, a `priority_queue` is a max-heap, meaning the largest element is always at the top (front).
   - You can also configure it as a min-heap, where the smallest element is at the top, by using a custom comparator.

2. **Efficient Operations**:
   - **Insertion** (`push`): Adds a new element to the queue and reorders it to maintain the heap property. Time complexity: \(O(\log n)\).
   - **Accessing the Top Element** (`top`): Returns the top element (largest or smallest, depending on the heap type). Time complexity: \(O(1)\).
   - **Removal** (`pop`): Removes the top element and reorders the remaining elements to maintain the heap property. Time complexity: \(O(\log n)\).

3. **Container Underlying the `priority_queue`**:
   - The default underlying container is a `std::vector`, but it can also be a `std::deque` or another container that provides random access iterators.

### Basic Usage Example:

```cpp
#include <iostream>
#include <queue>
#include <vector>

int main() {
    // Declare a max-heap priority queue (default behavior)
    std::priority_queue<int> maxHeap;

    // Add elements to the priority queue
    maxHeap.push(10);
    maxHeap.push(20);
    maxHeap.push(5);

    // Display and remove the top element (largest)
    std::cout << "Max-heap top: " << maxHeap.top() << std::endl;  // Output: 20
    maxHeap.pop();

    std::cout << "Max-heap top after pop: " << maxHeap.top() << std::endl;  // Output: 10

    // Declare a min-heap priority queue
    std::priority_queue<int, std::vector<int>, std::greater<int>> minHeap;

    // Add elements to the priority queue
    minHeap.push(10);
    minHeap.push(20);
    minHeap.push(5);

    // Display and remove the top element (smallest)
    std::cout << "Min-heap top: " << minHeap.top() << std::endl;  // Output: 5
    minHeap.pop();

    std::cout << "Min-heap top after pop: " << minHeap.top() << std::endl;  // Output: 10

    return 0;
}
```

### Explanation:

1. **Max-Heap (default)**:
   - In this example, `maxHeap` is a max-heap `priority_queue`. The largest element is always at the top.
   - After inserting `10`, `20`, and `5`, `20` is at the top.
   - When you call `pop`, `20` is removed, and `10` becomes the new top.

2. **Min-Heap**:
   - A min-heap can be created by specifying `std::greater<int>` as the comparator.
   - After inserting `10`, `20`, and `5`, `5` is at the top.
   - When you call `pop`, `5` is removed, and `10` becomes the new top.

### Use Cases:
- **Scheduling tasks** based on priority.
- **Finding the k-th largest/smallest element** in a stream of data.
- **Dijkstra's algorithm** and other graph algorithms where you need to access the minimum or maximum element efficiently.

### Summary:
A `priority_queue` is a powerful tool in C++ for managing a collection of elements where you need quick access to the largest or smallest element. It is implemented as a heap and provides efficient insertion, removal, and access to the top element.
