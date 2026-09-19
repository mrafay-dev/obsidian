writes characters of string into array
returns pointer to the arrray

raw pointer

only available on contiguos memory

different than [[std begin()]]

```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello";
    const char* ptr = str.data();
    
    // Safe to use as long as str is not modified
    std::cout << ptr << std::endl; 
    return 0;
}
```

