Able to block the calling thread until notified to resume

Uses a [[std unique_lock]]  to block the thread when `wait` is called on it
Will stay in that state until woken up by another thread

