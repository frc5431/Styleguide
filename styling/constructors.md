#Constructors

{% method -%}

Always try to provide a default constructor if possible.

Always try to initialize variables with their declaration.

{% sample lang="cpp" -%}

Delegating constructors is much faster than using assignment.

```cpp
Foo(const unsigned int f, const bool b) : foo(f), bar(b) {}
```

Always follow the rule of three: if you include one of the following, you have to include all of them.

* Constructor
* Destructor
* Copy constructor

In `virtual` classes, always declare the destructor `virtual`.

Aggregate initialization for `struct`s is great. Use them.



{% endmethod %}