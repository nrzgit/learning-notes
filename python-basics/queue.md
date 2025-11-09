# First-in-first-out Data Structure
[Source](https://leetcode.com/explore/learn/card/queue-stack/228/first-in-first-out-data-structure/1355/)

<img width="540" height="208" alt="image" src="https://github.com/user-attachments/assets/2a3709ed-2f60-4fa4-83e1-f03521fe1e53" />

In a FIFO data structure, <mark>the first element added to the queue will be processed first.</mark>

As shown in the picture above, the queue is a typical FIFO data stucture. The insert operation is also called enqueue and the new element is always <mark>added at the end of the queue</mark>. The delete operation is called dequeue. You are only allowed to <mark>remove the first element.</mark>

<img width="392" height="103" alt="image" src="https://github.com/user-attachments/assets/8f36f6ad-0add-422f-871d-d2cbb3ef2960" />

1. Enqueue: a new element 6 is added to the queue

<img width="440" height="128" alt="image" src="https://github.com/user-attachments/assets/321ca6ce-db36-4e86-a226-5b5eb626374f" />

2.  Dequeue:

<img width="438" height="125" alt="image" src="https://github.com/user-attachments/assets/a48e0bd7-6081-43e3-a791-cd65a37dfc44" />

### Implementation:
**Queue.put(item):** Adds an item to the queue.

**Queue.get():** Removes and returns an item from the queue.

**Queue.qsize():** Returns the approximate size of the queue.

**Queue.empty():** Returns True if the queue is empty, False otherwise.

**Queue.full():** Returns True if the queue is full, False otherwise.
```
import queue

# Create a FIFO queue
q = queue.Queue(maxsize=3)

# Add items to the queue
q.put('a')
q.put('b')
q.put('c')

# Check if the queue is full
print(q.full()) # Output: True

# Remove items from the queue
print(q.get()) # Output: 'a'
print(q.get()) # Output: 'b'
print(q.get()) # Output: 'c'

# Check if the queue is empty
print(q.empty()) # Output: True
```
# Circle queue:
[Source](https://leetcode.com/explore/learn/card/queue-stack/228/first-in-first-out-data-structure/1396/)

A more efficient way is to use a circular queue. Specifically, we may use <mark>a fixed-size array</mark> and <mark>two pointers</mark> to indicate the starting position and the ending position. And the goal is to reuse <mark>the wasted storage</mark> we mentioned previously.

<details>
<summary>🌀 Click to view the Circular Queue implementation in Python</summary>

  ```python
  
class CircularQueue:
    def __init__(self, size):
        self.maxSize = size
        self.queue = [None] * size
        self.front = -1
        self.rear = -1

    def enqueue(self, item):
        # Check if the queue is full
        if (self.rear + 1) % self.maxSize == self.front:
            print("Queue is full. Cannot enqueue.")
            return False
        # Insert the first element
        if self.front == -1:
            self.front = 0
        # Update rear and add the item
        self.rear = (self.rear + 1) % self.maxSize
        self.queue[self.rear] = item
        return True

    def dequeue(self):
        # Check if the queue is empty
        if self.front == -1:
            print("Queue is empty. Cannot dequeue.")
            return None
        # Remove the front element
        item = self.queue[self.front]
        if self.front == self.rear:  # Queue becomes empty after this operation
            self.front = -1
            self.rear = -1
        else:
            self.front = (self.front + 1) % self.maxSize
        return item

    def peek(self):
        if self.front == -1:
            print("Queue is empty. No peek value.")
            return None
        return self.queue[self.front]

    def is_empty(self):
        return self.front == -1

    def display(self):
        if self.is_empty():
            print("Queue is empty.")
            return
        print("Circular Queue elements:")
        i = self.front
        while True:
            print(self.queue[i], end=" ")
            if i == self.rear:
                break
            i = (i + 1) % self.maxSize
        print()


# Example Usage
if __name__ == "__main__":
    cq = CircularQueue(5)
    cq.enqueue(10)
    cq.enqueue(20)
    cq.enqueue(30)
    cq.display()  # Output: 10 20 30
    print("Dequeued:", cq.dequeue())  # Output: Dequeued: 10
    cq.display()  # Output: 20 30
```
</details>
