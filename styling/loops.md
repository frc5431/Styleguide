#Loops

{% method -%}

Put spaces in between mathmatical operators as if they are alone.

Put spaces after semicolons.

{% common -%}

EXAMPLE:
BAD:
```java
for(int i=0;i<100;i++){
  //code
}
```
GOOD:
```java
for(int i = 0; i < 100; ++i) {
  //code
}
```

{% endmethod %}

{% method -%}

In a `for` loop, instead of `i++`, try `++i`. The latter has one less operation.

**EXCEPTION:** Whether the `++` goes before or after the variable affects operator precedence. If the post fix version (`i++`) is required for order of operations purpose, use it.

Prefer `while` loops to `do...while`. The former is easier to understand at a glance.

{% common -%}

EXAMPLE:
BAD:
```java
for(int i = 0; i < 3; i++) {
  //code
}
```
GOOD:
```java
for(int i = 0; i < 3; ++i) {
  //code
}
```


{% endmethod %}