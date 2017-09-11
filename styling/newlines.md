{% method -%}

Always use the language-specific alternative to a pure newline.

*REASONING:*
Some platforms use `\n`, some use `\r\n`. Hardcoding these values into your program could cause some compatibility issues with other platforms.

{% sample lang="java" -%}
Use `System.lineSeperator()`

BAD:
```java
System.out.println("Hello!\n");
```

GOOD:
```java
System.out.println("Hello!" + System.lineSeparator());
```

{% sample lang="cpp" -%}
Use `std::endl` or `\n`. `std::cout` will correctly format `\n` to the correct platform newline character. It is recommended to still use `std::endl`. HOWEVER, `std::endl` will flush the `ostream`, so if you want to avoid that, use a plain `\n` (not `\r\n`)

{% endmethod %}