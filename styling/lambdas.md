#Lambdas

{% method -%}

Use lambda expressions and interfaces to increase modularity in your code.

{% sample lang="java" -%}

When defining a functional interface, use the `@FunctionalInterface` annotation:
```java
@FunctionalInterface
public interface Footerface {
  public void doFoo();
}
```

{% sample lang="cpp" -%}

When using a function pointer, always put the `&` (dereference operator) to avoid any confusion.

BAD:
```cpp
foo(frc5431::myLambda);
```
GOOD:
```cpp
foo(&frc5431::myLambda);
```

{% endmethod %}
