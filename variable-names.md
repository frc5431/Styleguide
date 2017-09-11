{% method -%}

You will use camelCase for names of functions and variables, which means no underscores, and every word but the first is capitalized.

{% sample lang="java" -%}
BAD:
```java
int ThisIsAVariable
int this_is_a_variable
int thisisavariable
int thIsiSaVariABLE
```
GOOD:
```java
int thisIsAVariable
```

{% sample lang="c++" -%}

BAD:
```c++
int ThisIsAVariable
int this_is_a_variable
int thisisavariable
int thIsiSaVariABLE
```
GOOD:
```c++
int thisIsAVariable
```

{% endmethod %}

{% method -%}

Names should be descriptive, and explain their purpose.

{% sample lang="java" -%}
BAD:
```java
int foo
int blah
int poop
int woawver
```
GOOD:
```java
int pidControllerState
int currentTime
int keyIterator
```
{% sample lang="c++" -%}
BAD:
```java
int foo
int blah
int poop
int woawver
```
GOOD:
```java
int pidControllerState
int currentTime
int keyIterator
```

{% endmethod %}