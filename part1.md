## Variables, Number Systems, and I/O

### Variables

**Variables** are what we store _values_ in. A value can be anything from a primitive value, all the way up to an object instance. They're declared like this:

``` java
// Creating an integer variable
int x = 5;

// Creating a String variable
String str = "I am a string";

// Instantiating a Scanner object and storing it in a variable
Scanner sinput = new Scanner(System.in);

// You can then call Scanner methods like so:
int a = sinput.nextInt();
```

### Number systems

#### Two's Complement

_Useful links: [source](https://www.cs.cornell.edu/~tomf/notes/cps104/twoscomp.html#:~:text=Two's%20complement%20is%20the%20way,add%20one%20to%20the%20result.&text=That%20is%20how%20one%20would%20write%20%2D28%20in%208%20bit%20binary.)_ _[conversion tool](https://www.rapidtables.com/convert/number/decimal-to-binary.html)_

Two's complement is the way in which computers represent integers. To get the two's complement negative notation of an integer, you perform the following steps:

1. Write out the number in binary
2. Invert the digits
3. Add one to the result

**It is a given** that if the leftmost bit is a `1`, then **this number is negative**.

For example, given 8 bits and the number -28:
##### Write out the binary form
`28 = 0 0 0 1 1 1 0 0`
##### Invert the digits
` 0 0 0 1 1 1 0 0 => 1 1 1 0 0 0 1 1 `
##### Add 1
``` 
1 1 1 0 0 0 1 1
              1 +
-----------------
1 1 1 0 0 1 0 0
```

#### Two's Complement: Converting to decimal
It is therefore also possible to convert _from_ Two's Complement; take the number `0xFFFFFFFF` as an example. This is the hex representation of `1111 1111 1111 1111 1111 1111 1111 1111`.

At first glance, we can tell that **this number is negative**, as it has a leading (leftmost) bit set to `1`.

If you want to see what this number is a negative _of_, then we follow a similar set of steps:

1. Invert all the bits
2. Add one

Therefore, inverting all the bits `0xFFFFFFFF` results in `0000 0000 0000 0000 0000`. Then, adding `1` leads to `0000 0000 0000 0001`, which is the number `1`. Therefore, the _negative_ of `0xFFFFFFFF` is 1, and hence the _value_ is `-1`.
