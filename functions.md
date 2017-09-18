#Functions

{% method -%}
Functions follow the same rules as variables, which is camelCase.

ALL functions follow this rule, even static functions or member functions.

{% sample lang="java" -%}
```java
public static void runsSomeWoawvering();
private int getHolesInWall();
```

{% sample lang="cpp" -%}
```cpp
class Foo {
public:
    void runNarwhal();
}

int getVersion();
```

Macros follow the same rules as a [constant](/constants.md)
{% endmethod %}

{% method -%}

Functions should ALWAYS be some sort of verb.

Use getters and setters effectively to achieve this.

{% endmethod %}