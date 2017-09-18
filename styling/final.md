#Final and Const

{% method -%}

Always declare your functions and variables read only whenever possible.

*REASONING:*
Sounds strange, but making as many things read only, no matter how small, has 2 purposes:
 * Clarifies confusion to other developers
 * Allows for a lot of optimization
 
Once you do it enough, it will become habit to make a variable read only. Of course, this only applies to variables you know you won't reassign

{% sample lang="java" -%}

Declare read only variables `final` whenever possible.

Always declare input variables to functions `final`. It is bad practice to reassign an input variable.

The name is a bit misleading, as a `final` variable can still have all of it's functions called on it. It simply can't be reassigned.

{% sample lang="cpp" -%}

Declare read only variables and functions `const` whenever possible.

Always make sure to mark as many things `const` including functions and input parameters. Think of `const` as a disease and you want to make sure that as many things have it.

Whenever possible, make something `constexpr` to allow for optimization.

NEVER use `const_cast`. If something is `const`, there is a reason for this. There are VERY LITTLE cases in which you HAVE to use `const_cast` legitimately.

{% endmethod %}