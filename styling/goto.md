#Goto

![](https://imgs.xkcd.com/comics/goto.png)

No. Do not use `goto`. If you absolutely have to use a `goto` statement, use a `switch case` instead or restructure your code.

*REASONING:* `goto`'s lead to spaghetti code and unsafe practices. If you have to use `goto` and not `continue`, `return`, or `break`, then your code is not structured correctly.