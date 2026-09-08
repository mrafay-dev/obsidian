Automatically handles warmups, runs it many time, and gives average time and iterations per second

`sudo apt install libbenchmark-dev`

```cpp
#include <benchmark/benchmark.h>
int func_name(){
	for (auto _ : state) {
        // DoNotOptimize prevents the compiler from optimizing the call away
        bool res = validator.isValid(msg);
        benchmark::DoNotOptimize(res);
	    //...
    }
}

BENCHMARK(func_name);

BENCHMARK_MAIN();

```
