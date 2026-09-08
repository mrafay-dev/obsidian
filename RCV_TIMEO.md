Prevents an application blocking indefinitely if a data source goes silent

```cpp
struct Timeval {
    long tv_sec;
    long tv_usec;
};

Timeval compute_socket_timeout(int timeout_ms) {
    Timeval time;
    time.tv_sec = timeout_ms / 1000L;
    time.tv_usec = (timeout_ms % 1000L) * 1000L;
    return time;
}

```

return the Timeval to `setsockopt(sockfd, SOL_SOCKET, SO_RCV_TIMEO, &tv, sizeof(tv)` 
After timeout, recv() returns -1, and errno will be `EAGAIN` or `EWOULDBLOCK`