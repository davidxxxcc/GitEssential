# Introduction

### JavaScript is a lighweight, cross-platform, object-oriented computer programming language.

JavaScript is one of the three core technologies of web development\(HTML5, CSS, and JavaScript.\)

Left-associativity \(left-to-right\) means that it is processed as`(a OP b) OP c`, while right-associativity \(right-to-left\) means it is interpreted as`a OP (b OP c)`. Assignment operators are right-associative, so you can write:

```
a = b = 5;
```

with the expected result that`a`and`b`get the value 5. This is because the assignment operator returns the value that is assigned. First,`b`is set to 5. Then the`a`is also set to 5, the return value of`b = 5`, aka right operand of the assignment.

### The following table is ordered from highest \(20\) to lowest \(1\) precedence.

| Precedence | Operator type | Associativity | Individual operators |
| :--- | :--- | :--- | :--- |
| 20 | [`Grouping`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Grouping) | n/a | `( … )` |
| 19 | [`Member Access`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors#Dot_notation) | left-to-right | `… . …` |
|  | [`Computed Member Access`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors#Bracket_notation) | left-to-right | `… [ … ]` |
|  | [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)\(with argument list\) | n/a | `new … ( … )` |
|  | [Function Call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) | left-to-right | `… ( … )` |
| 18 | [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) \(without argument list\) | right-to-left | `new …` |
| 17 | [`Postfix Increment`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment) | n/a | `… ++` |
|  |  | [`Postfix Decrement`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Decrement) | `… --` |
| 16 | [Logical NOT](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_NOT) | right-to-left | `! …` |
|  |  | [Bitwise NOT](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_NOT) | `~ …` |
|  |  | [Unary Plus](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus) | `+ …` |
|  |  | [Unary Negation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_negation) | `- …` |
|  |  | [Prefix Increment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment) | `++ …` |
|  |  | [Prefix Decrement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Decrement) | `-- …` |
|  |  | [typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) | `typeof …` |
|  |  | [void](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void) | `void …` |
|  |  | [delete](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete) | `delete …` |
|  |  | [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) | `await …` |
| 15 | [Exponentiation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Exponentiation) | right-to-left | `… ** …` |
| 14 | [Multiplication](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Multiplication) | left-to-right | `… * …` |
|  |  | [Division](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Division) | `… / …` |
|  |  | [Remainder](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Remainder) | `… % …` |
| 13 | [Addition](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Addition) | left-to-right | `… + …` |
|  |  | [Subtraction](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Subtraction) | `… - …` |
| 12 | [Bitwise Left Shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators) | left-to-right | `… << …` |
|  |  | [Bitwise Right Shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators) | `… >> …` |
|  |  | [Bitwise Unsigned Right Shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators) | `… >>> …` |
| 11 | [Less Than](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Less_than_operator) | left-to-right | `… < …` |
|  |  | [Less Than Or Equal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Less_than__or_equal_operator) | `… <= …` |
|  |  | [Greater Than](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Greater_than_operator) | `… > …` |
|  |  | [Greater Than Or Equal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Greater_than_or_equal_operator) | `… >= …` |
|  |  | [in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) | `… in …` |
|  |  | [instanceof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) | `… instanceof …` |
| 10 | [Equality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Equality) | left-to-right | `… == …` |
|  |  | [Inequality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Inequality) | `… != …` |
|  |  | [Strict Equality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Identity) | `… === …` |
|  |  | [Strict Inequality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Nonidentity) | `… !== …` |
| 9 | [Bitwise AND](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_AND) | left-to-right | `… & …` |
| 8 | [Bitwise XOR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_XOR) | left-to-right | `… ^ …` |
| 7 | [Bitwise OR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators#Bitwise_OR) | left-to-right | `… | …` |
| 6 | [Logical AND](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_AND) | left-to-right | `… && …` |
| 5 | [Logical OR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_OR) | left-to-right | `… || …` |
| 4 | [Conditional](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) | right-to-left | `… ? … : …` |
| 3 | [Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators) | right-to-left | `… = …` |
|  |  |  | `… += …` |
|  |  |  | `… -= …` |
|  |  |  | `… **= …` |
|  |  |  | `… *= …` |
|  |  |  | `… /= …` |
|  |  |  | `… %= …` |
|  |  |  | `… <<= …` |
|  |  |  | `… >>= …` |
|  |  |  | `… >>>= …` |
|  |  |  | `… &= …` |
|  |  |  | `… ^= …` |
|  |  |  | `… |= …` |
| 2 | [yield](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield) | right-to-left | `yield …` |
|  |  | [yield\*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield*) | `yield* …` |
| 1 | [Comma / Sequence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator) | left-to-right | `… , …` |



