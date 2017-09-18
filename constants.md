#Constants

{% method -%}

A constant is defined as a variable that can't be changed.

Constants are in ALL\_UPPERCASE\_WITH\_UNDERSCORES (capitalized snake case)

{% sample lang="java" -%}

Constants always have `static final`

```java
public static final String THIS_IS_A_CONSTANT = "Constantly following the rules!";
```

{% sample lang="cpp" -%}

Constants can be macros or `const` variables. It is highly recommended to make constants `constexpr` and `inline` as well.

```cpp

#define FRC5431_CONSTANT_INOPLE 3.45921321 

namespace frc5431 {
    const constexpr int SPECIAL_NUMBER = 342131;
}

```

If using a macro as a constant, always prefix it. This prefix should be unique to your project. If you can't think one of, `FRC5431_` is always good.

Functional macros follow the same rules as a normal constant. They must also be verbs.

```cpp
#define FRC5431_STRINGIFY(name) #name
#define FRC5431_SUM(a, b) a + b
```
Functional macros with multiple lines must be wrapped in a `do...while` block

```cpp
#define FRC5431_DO_MULTILINE() do{ ... }while(0)
```

*REASONING:* [See this post for the do...while rule](https://stackoverflow.com/a/1067238)

{% endmethod %}

