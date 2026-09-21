
```cpp
#include <type_traits>

// Both of these accomplish the exact same thing:
constexpr bool with_value = std::is_trivially_copy_constructible<int>::value; // C++11 style
constexpr bool with_v     = std::is_trivially_copy_constructible_v<int>;     // C++17 style (cleaner)

```

2 ways. Without or with _ v (C++17)

Checks if we can copy raw bytes. Wont work with user defined or non - trrivial constructors, destructors, or virtual functions (those have their own checks)

Good for using with memcpy