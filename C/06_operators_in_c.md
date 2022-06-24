## Operators in C
### Types of operators (based on operands)
1. Unary - require only 1 operarnd
2. Binary - require 2 operarnds
3. Ternary - requires 3 operands

#### Unary
- `-` (unary minus)
- `++` , `--` (increment , decrement)
- `!` (logical not)
- `&` (address of)
- `size of`

#### Binary
- Arithmatic (`+`  `-` `/` `*` `%`)  
- Reletimal (`<` `>` `<=` `>=`)
- Logical (`&&` `||`)
- Bitwise (`&` `|` `<<` `>>` `^` `~`)
- Equality operator (`==` `!=`)
- Comma operator (`,`)
- Assignment operator (`=`)

#### Ternery
- `condition ? value_if_true : value_if_false`
	- eg 
```c
int a = 10, b = 20, c;

c = (a < b) ? a : b;

printf("%d", c);

```
