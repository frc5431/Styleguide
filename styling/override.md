#Override

{% method -%}

When using inheritance, always use the appropriate keyword to mark that a function is overriding another function.

{% sample lang="java" -%}

Use the `@Override` annotation when overriding a function.

Always make sure to call the `super` version of the function unless the documentation explicitly says otherwise.

{% sample lang="cpp" -%}

Mark functions you want overridden as `virtual`. Make sure the proper visibility is used IE `protected` or `public`.

When overriding functions, always include the `override` or `final` keyword so the compiler can raise errors if you use the wrong function signature.

If your class contains any `virtual` functions, make sure to declare the destructor `virtual` as well.

{% common -%}

If you don't want a function to be overridden, use the `final` keyword on the `class` or function.


{% endmethod %}