struct timespec has 2 members
tv_sec
tv_nsec

so find diff between the two, convert to common unit, then add

this is posix

```cpp
struct timespec start, end;

clock_gettime(CLOCK_MONOTONIC, &start);
// do something
clock_gettime(CLOCK_MONOTONIC, &end);

long ns_elapsed = (end.tv_sec - start.tv_sec) * 1000000000L + (end.tv_nsec - start.tv_nsec);
```

monotonic because it only goes forward

    __rdtsc() takes around 5ns to get time ->has cycle to ns conversion via TSC frequency
TSC is time stamp counter of the cpu (in GHz usually)
```cpp
auto t0 = __rdtsc();
//work
auto dt = __rdstc() - t0;
Then divide by cpu frequency
```

https://github.com/mrafay-dev/LowLevelDev/tree/main/MyntBitChallenges/timespec