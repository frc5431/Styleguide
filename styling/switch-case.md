{% method -%}
Do not put spaces in the parenthesis of the `switch` declaration.
{% endmethod %}

{% method -%}

The curly bracket goes on the same line with a space after the closing parenthesis.

{% common -%}

EXAMPLE:
BAD:
```java
switch ( variable ) {

switch(variable){//no space
```
GOOD:
```java
switch(variable) {
```

{% endmethod %}

{% method -%}

`case` is not indented.

Always put `break` unless you intend fallthrough. If you are falling through, put each case on seperate lines.

Always put a `default` case. `default` should always be the very last case, unless you are intentionally falling through with it.

Try to use `enum`'s whenever possible.

{% common -%}

EXAMPLE:
BAD:
```java
case A:
  case B: case C: 
  //code
  break;
default:
case D: 
  //code
  break;
```
GOOD:
```java
case A:
case B:
case C:
  //code
  break;
case D:
default:
  break;
```

{% sample lang="cpp" -%}

When using `C++17` always include the `[[fallthrough]]` attribute when falling to the next block 


{% endmethod %}