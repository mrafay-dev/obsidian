Atomically compares 2 memory locations:
1. If they are same: Returns true
2. If not, updates mem1 to mem2, and returns false.

Helps with multithreading and synchronising data

Used it in my ThreadSafeQueue.cpp to check next valid push() and pop() indexes in the queue.
