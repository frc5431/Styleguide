{% method -%}
`if` statements always have curly brackets on seperate lines. Even if they are one line statements.

{% sample lang="cpp" -%}

C++17 adds `if` initalizers. Similar to `for` loops, there should be a space in between the initializer and condition.

```cpp
if(int foo = 5; foo != 4) {
    //code
}
```

{% sample lang="java" -%}

You can configure your Eclipse to apply this formatting whenever you press `Ctrl` `Shift` `R`

{% common -%}
BAD:
```java
if(condition) code();

if(condition) { code(); }
```
GOOD:
```java
if(condition) {//don't forget the space!
  code();
}
```



{% endmethod %}

*REASONING:*
There is a very important reason for this seemingly petty rule. It clarifies a lot of confusion.

For example, this code is very confusing at first glance:
```java
if(condition) foo(); bar(); //WARNING: bar() is NOT part of the if statement!
```

With this style guide, the above code will become much clearer:
```java
if(condition) {
  foo();
}
bar();
```

Another example of why this rule is absolutely important is because of what happend to OSX developers. They had some code which checked the signature of an SSL certificate. For those who don't know what that is, the function checked if an encryption was valid. Here was the code (in C:)
```c
hashOut.data = hashes + SSL_MD5_DIGEST_LEN;
hashOut.length = SSL_SHA1_DIGEST_LEN;
if ((err = SSLFreeBuffer(&hashCtx)) != 0)
    goto fail;
if ((err = ReadyHash(&SSLHashSHA1, &hashCtx)) != 0)
    goto fail;
if ((err = SSLHashSHA1.update(&hashCtx, &clientRandom)) != 0)
    goto fail;
if ((err = SSLHashSHA1.update(&hashCtx, &serverRandom)) != 0)
    goto fail;
if ((err = SSLHashSHA1.update(&hashCtx, &signedParams)) != 0)
    goto fail;
    goto fail;  /* MISTAKE! THIS LINE SHOULD NOT BE HERE */
if ((err = SSLHashSHA1.final(&hashCtx, &hashOut)) != 0)
    goto fail;

err = sslRawVerify(...);
```

Notice that the second `goto fail` always ran. This was a typo by OSX developers that actually opened up a HUGE security vulnerability. By always putting curly brackets, you prevent very hard-to-find errors such as this.

## Logical Operators

{% method -%}

When using logical operators such as `&&` and `||` always put a space in between the operands. Single operand operators such as `!`, `-`, or `~` don't have a space.

See more details in the [operators](/styling/operators.md) section.

Also, the same rules specified on the [Line Length](/styling/line-length.md) page apply to `if` statements.

{% common -%}
```java
if(condition1 && !condition2 || (condition3() && ~condition4)) {
    //code
}
```

{% endmethod %}

{% method -%}

## Else

![](https://imgs.xkcd.com/comics/code_quality.png)

If you have an else-if the closing bracket and the else goes on the same line. Spaces go after the brackets.

{% common -%}

BAD:
```java
}
else{

}else
if(){

}
else
if()
{
```
GOOD:
```java
} else if() {

} else{
```

{% endmethod %}