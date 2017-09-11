{% method -%}

A constant is defined as a variable that can't be changed.

Constants are in ALL\_UPPERCASE\_WITH\_UNDERSCORES (capitalized snake case)

{% sample lang="java" -%}

Constants always have `static final`

```java
public static final String THIS_IS_A_CONSTANT = "Constantly following the rules!";
```

{% sample lang="c++" -%}

Constants can be macros or `const` variables. It is highly recommended to make constants `constexpr` and `inline` as well.

```c++

#define FRC5431_CONSTANT_INOPLE 3.45921321 

namespace frc5431 {
    const constexpr int SPECIAL_NUMBER = 342131;
}

```

Functional macros meet the same naming requirements as a normal function.

If using a macro as a constant, always prefix it. This prefix should be unique to your project. If you can't think one of, `FRC5431_` is always good.

Remember that you must define the constant variable in the source, not the header. Otherwise you get multiple definition errors.

{% endmethod %}

