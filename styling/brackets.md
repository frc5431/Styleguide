{% method -%}
When typing anything that requires curly brackets (conditionals, loops, functions, classes, etc), the first bracket goes on the same line as the definition. There is a space between the curly bracket and the end of the definition

{% sample lang="java" -%}

BAD:
```java
public void eatWombats()
{

public void eatWombats()




{

void eatWombats(){//needs a space between bracket and eatWombats()
```
GOOD:
```java
public void eatWombats() {
```

{% sample lang="cpp" -%}

BAD:
```cpp
void eatWombats()
{

void eatWombats()




{

void eatWombats(){//needs a space between bracket and eatWombats()
```
GOOD:
```cpp
void eatWombats() {
```
{% endmethod %}

{% method -%}

The second curly bracket will have its own line after the last line of the function

{% common -%}
BAD:
```java
void eatWombats(){foo();}
void eatWombats(){
foo();}
```
GOOD:
```java
void eatWombats() {
  foo();
}

{% endmethod %}

{% method -%}

**EXCEPTION:** If a function is empty, it is okay to use `{}` syntax on the same line. Remember to put the space!

{% common -%}
```cpp
void doNothing() {}
```
{% endmethod %}

{% method -%}
Each time an opening curly bracket is encountered, indent by an extra tab.

{% common -%}
```java
int eatWombat(){
  if(descriptiveBooleanName){
      for(int i = 0; i < 100; ++i){
        bar();
      }
      return foo();
  }
  return 1;
}
```

{% endmethod %}