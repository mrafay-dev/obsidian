```cpp
class VolumeAccumulator{
private:
        //Each thread gets its own independent `acc`.
        // `inline` (C++17) lets us define it in the class body.
        // `static`  ties storage to the class, not per-instance.
        // `thread_local` makes it per-thread.
    static inline thread_local double acc = 0.0;
public:
    void add(double volume) {
        acc += volume;
    }
    double getThreadLocalVolume() {
        return acc;
    }
};
```
per thread var instance, otherwise we'd have a global var and then we could have data races