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

{% method -%}

## Global Constants

Try to avoid non-constant global variables.

*CLARIFICATION:*
Global constants are `static` variables.

{% common -%}
*REASONING:*
One of the biggest factors to spaghetti code are global variables. For example, look at this code:

{% sample lang="java" -%}
```java
void doSomething(){
  OtherClass.foo = "I like spaghetti";
}
...
woawver.doSomething();
```

{% sample lang="cpp" -%}
```cpp
void doSomething(){
  bar::foo = "I like spaghetti";
}
...
doSomething()
```

{% common -%}

This code is a prime example of how spaghetti code is formed. `doSomething()` now affects other classes and variables, so that can cause confusion to anyone using `doSomething()` as to why the global constant has changed it's value!

The better way to do the above code that isn't a delicious italian product is like this:

{% sample lang="java" -%}
```java
String doSomething(){
  return "I am still hungry":
}
...
OtherClass.foo = woawver.doSomething()
```

{% sample lang="cpp" -%}

```cpp
std::string doSomething(){
  return "I am still hungry";
}
...
bar::foo = doSomething();
```

{% common -%}
This new technique produces completely identical code, adds more versality as now `doSomething()` can be used anywhere, and reduces confusion. All because you got rid of global constants!

{% endmethod %}

{% method -%}

## Magic Constants

![](https://imgs.xkcd.com/comics/int_pi.png)

A magic constant is a literal in your code that doesn't have any meaning or explanation. 

Instead of embedding literals into code, create a constant at the top of the file to reduce spatghetti code and allow for more configurability.

{% sample lang="java" -%}

BAD:
```java
NetworkTable.get("roborio-frc-5431.local");//"roborio-frc-5431.local" is a magic constant
```

GOOD:
```java
private static final NETWORKTABLE_LOCATION "roborio-frc-5431.local"

...
NetworkTable.get(NETWORKTABLE_LOCATION);
```

{% sample lang="cpp" -%}

You can use `#define` or `const constexpr` constants.

BAD:
```cpp
NetworkTable::get("roborio-frc-5431.local");//"roborio-frc-5431.local" is a magic constant
```

GOOD:
```cpp
#define FRC5431_NETWORKTABLE_LOCATION "roborio-frc-5431.local"

...
NetworkTable::get(FRC5431_NETWORKTABLE_LOCATION);
```

{% endmethod %}
