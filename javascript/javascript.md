# Introduction

### JavaScript is a lighweight, cross-platform, object-oriented computer programming language.

JavaScript is one of the three core technologies of web development\(HTML5, CSS, and JavaScript.\)

Left-associativity \(left-to-right\) means that it is processed as`(a OP b) OP c`, while right-associativity \(right-to-left\) means it is interpreted as`a OP (b OP c)`. Assignment operators are right-associative, so you can write:

```
a = b = 5;
```

with the expected result that`a`and`b`get the value 5. This is because the assignment operator returns the value that is assigned. First,`b`is set to 5. Then the`a`is also set to 5, the return value of`b = 5`, aka right operand of the assignment.

