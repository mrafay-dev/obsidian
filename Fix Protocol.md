Financial Information Exchange protocol - exchange real-time information related to financial markets

EVery FIX message ends in checksum field: `Ex. 10=018` 

```cpp
class FIXValidator {
private:
public:
    bool isValid(const std::string& message) {
        //pointer which has access to the chars in message
        const char* p_start = message.data();

        //the last seven are always the checksum
        const char* p_end = p_start + message.size() - 7;

        //dereferences the pointer, then +1 for next round, till we reach end
        int total = 0;
        while(p_start < p_end) {
            total += static_cast<unsigned char>(*p_start++);
        }

        //manually finds the checksum at the end
        int provided = (p_start[3]-'0')*100 + (p_start[4]-'0')*10 + (p_start[5] - '0');
        return (total%256) == provided;
            }
};

static void BM_FixValidator(benchmark::State& state) {
    FIXValidator validator;
    std::string msg = "8=FIX.4.2|9=5|35=0|10=018|";
    for (auto _ : state) {
        // DoNotOptimize prevents the compiler from optimizing the call away
        bool res = validator.isValid(msg);
        benchmark::DoNotOptimize(res);
    }
}
BENCHMARK(BM_FixValidator);

BENCHMARK_MAIN();

```

