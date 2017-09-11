{% method -%}

A constant is defined as a variable that can't be changed.

Constants are in ALL\_UPPERCASE\_WITH\_UNDERSCORES



{% sample lang="java" -%}

Constants always have `static final`

```java
public static final String THIS_IS_A_CONSTANT = "Constantly following the rules!";
```

{% sample lang="c++" %}

Constants can be macros or `const` variables. It is highly recommended to make constants `constexpr` and `inline` as well.

```c++

#define CONSTANT_INOPLE 3.45921321 

const constexpr int SPECIAL_NUMBER = 342131;

```

Functional macros meet the same naming requirements as a normal function

{% endmethod %}

