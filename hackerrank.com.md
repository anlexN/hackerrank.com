chime.aws
amazonaws.com
grammarly.io
trafficmanager.net
cloudfront.net
msftconnecttest.com
msecnd.net
sourcegraph.com
microsoft.com
visualstudio.com
vsassets.io
grammarly.com
amazon.com
media-amazon.com
ssl-images-amazon.com
live.com
programs.programmingoneonone.com
www.bing.com
x1.c.lencr.org
crl4.digicert.com
config.edge.skype.com
assets.msn.com
odinvzc.azureedge.net
fp.msedge.net
data.osdknw.com
windows.com
office.com
maxcdn.bootstrapcdn.com
api.pofu.io
static.hotjar.com
sentry.io
crl.verisign.com
jetbrains.com
bing.net
deepl.com
kirelabs.org
https://d3js.org/
figma.com
mozilla.org
exp-tas.com

default.exp-tas.com
aa127576154809ce5b198836aeea2fab.nrb.footprintdns.com
deff.nelreports.net
1.bp.blogspot.com
apps.identrust.com
secure.gravatar.com
edgedl.me.gvt1.com

Array String Math Number Object

做题目是先把所有情况列举，先累加可以吗？

We can use memset() to set all values as 0 or -1 for integral data types also. It will not work if we use it to set as other values (include 1). The reason is simple, memset works byte by byte.

```cpp
int main()
{
    int a[5];

    // all elements of A are zero
    memset(a, 0, sizeof(a));
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
    cout << endl;

    // all elements of A are -1
    memset(a, -1, sizeof(a));
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
    cout << endl;

    // Would not work
    memset(a, 5, sizeof(a)); // WRONG
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
    cout << endl;
    // Would not work
    memset(a, 1, sizeof(a)); // WRONG
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
}
```

C++ 数组声明问题

```cpp
int a[1111]; // A is declared here, all elements of A are zero

int main()
{
    int a[1111]; // A is declared here, all elements of A are random; unless memset(a, 0, sizeof(a));
    for (int i = 0; i < 1111; i++)
        cout << a[i] << " ";
    cout << endl;

}
```

### [How do I convert a float number to a whole number in JavaScript?](https://stackoverflow.com/questions/596467/how-do-i-convert-a-float-number-to-a-whole-number-in-javascript)

As mentioned in another answer, a negative-safe truncate can be done using var intValue = ~~floatValue;. If the notation is too obscure for your tastes, just hide it in a function: function toInt(value) { return ~~value; }. (This also converts strings to integers, if you care to do so.)

Regarding the comment ~~ limits the value to 32 bit signed integers, while Math.floor/ceil/round can handle up to 53-bit (Number.MAX_SAFE_INTEGER 9007199254740991). This is mentioned in the answer below, but it is worth repeating here for those reading these comments.

```
// value=x        //  x=5          5<x<5.5      5.5<=x<6

Math.floor(value) //  5            5            5
Math.ceil(value)  //  5            6            6
Math.round(value) //  5            5            6
Math.trunc(value) //  5            5            5
parseInt(value)   //  5            5            5
~~value           //  5            5            5
value | 0         //  5            5            5
value >> 0        //  5            5            5
value >>> 0       //  5            5            5
value - value % 1 //  5            5            5

// value=x        // x=-5         -5>x>=-5.5   -5.5>x>-6

Math.floor(value) // -5           -6           -6
Math.ceil(value)  // -5           -5           -5
Math.round(value) // -5           -5           -6
Math.trunc(value) // -5           -5           -5
parseInt(value)   // -5           -5           -5
value | 0         // -5           -5           -5
~~value           // -5           -5           -5
value >> 0        // -5           -5           -5
value >>> 0       // 4294967291   4294967291   4294967291
value - value % 1 // -5           -5           -5

// x = Number.MAX_SAFE_INTEGER/10 // =900719925474099.1

// value=x            x=900719925474099    x=900719925474099.4  x=900719925474099.5

Math.floor(value) //  900719925474099      900719925474099      900719925474099
Math.ceil(value)  //  900719925474099      900719925474100      900719925474100
Math.round(value) //  900719925474099      900719925474099      900719925474100
Math.trunc(value) //  900719925474099      900719925474099      900719925474099
parseInt(value)   //  900719925474099      900719925474099      900719925474099
value | 0         //  858993459            858993459            858993459
~~value           //  858993459            858993459            858993459
value >> 0        //  858993459            858993459            858993459
value >>> 0       //  858993459            858993459            858993459
value - value % 1 //  900719925474099      900719925474099      900719925474099

// x = Number.MAX_SAFE_INTEGER/10 * -1 // -900719925474099.1

// value = x      // x=-900719925474099   x=-900719925474099.5 x=-900719925474099.6

Math.floor(value) // -900719925474099     -900719925474100     -900719925474100
Math.ceil(value)  // -900719925474099     -900719925474099     -900719925474099
Math.round(value) // -900719925474099     -900719925474099     -900719925474100
Math.trunc(value) // -900719925474099     -900719925474099     -900719925474099
parseInt(value)   // -900719925474099     -900719925474099     -900719925474099
value | 0         // -858993459           -858993459           -858993459
~~value           // -858993459           -858993459           -858993459
value >> 0        // -858993459           -858993459           -858993459
value >>> 0       //  3435973837           3435973837           3435973837
value - value % 1 // -900719925474099     -900719925474099     -900719925474099
```

https://zh.wikipedia.org/wiki/%E8%B4%A8%E6%95%B0
质数（Prime number），又称素数，指在大于 1 的自然数中，除了 1 和该数自身外，无法被其他自然数整除的数（也可定义为只有 1 与该数本身两个正因数的数）。大于 1 的自然数若不是素数，则称之为合数（也称为合成数）。例如，5 是个素数，因为其正约数只有 1 与 5。7 是个素数，因为其正约数只有 1 与 7。而 4 则是个合数，因为除了 1 与 4 外，2 也是其正约数。6 也是个合数，因为除了 1 与 6 外，2 与 3 也是其正约数。算术基本定理确立了素数于数论里的核心地位：任何大于 1 的整数均可被表示成一串唯一素数之乘积。为了确保该定理的唯一性，1 被定义为不是素数，因为在因式分解中可以有任意多个 1（如 3、1×3、1×1×3 等都是 3 的有效约数分解）

前 168 个素数（所有小于 1000 的素数）为 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97, 101, 103, 107, 109, 113, 127, 131, 137, 139, 149, 151, 157, 163, 167, 173, 179, 181, 191, 193, 197, 199, 211, 223, 227, 229, 233, 239, 241, 251, 257, 263, 269, 271, 277, 281, 283, 293, 307, 311, 313, 317, 331, 337, 347, 349, 353, 359, 367, 373, 379, 383, 389, 397, 401, 409, 419, 421, 431, 433, 439, 443, 449, 457, 461, 463, 467, 479, 487, 491, 499, 503, 509, 521, 523, 541, 547, 557, 563, 569, 571, 577, 587, 593, 599, 601, 607, 613, 617, 619, 631, 641, 643, 647, 653, 659, 661, 673, 677, 683, 691, 701, 709, 719, 727, 733, 739, 743, 751, 757, 761, 769, 773, 787, 797, 809, 811, 821, 823, 827, 829, 839, 853, 857, 859, 863, 877, 881, 883, 887, 907, 911, 919, 929, 937, 941, 947, 953, 967, 971, 977, 983, 991, 997,...（OEIS 数列 A000040）。

### [2 arrays of Same value are not equal in JS.](https://dev.to/shubhamtiwari909/2-arrays-of-same-value-are-not-equal-in-js-518c)

```js
let array1 = [1, 5, 9, 14, 17];
let array2 = [1, 5, 9, 14, 17];

console.log(array1 == array2); // false
console.log(array1 === array2); // false

let array1 = [1, 5, 9, 14, 17];
let array2 = [1, 5, 9, 14, 17];
let array3 = array1;
console.log(array3 === array1);
true;
console.log(array3 === array2);
false;

let array1 = [1, 5, 9, 14, 17];
let array2 = [1, 5, 9, 14, 17];
console.log(array1.toString() === array2.toString()); //true
```

some code like below logic is right (find the total of zero). however hackerrank javascript(nodejs) timeout, but C++, python do not.

```js
function sumXor(n) {
  // Write your code here
  let found = 1,
    zero = 0;

  while (n) {
    zero = n & 1;
    n >>>= 1;

    if (!zero) found *= 2;
  }

  return found;
}
```

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec

- If you only care whether the regex matches a string, but not what is actually being matched, use RegExp.prototype.test() instead.
- If you are finding all occurrences of a global regex and you don't care about information like capturing groups, use String.prototype.match() instead.
  In addition, String.prototype.matchAll() helps to simplify matching multiple parts of a string (with capture groups) by allowing you to iterate over the matches.
- If you are executing a match to find its index position in the string, use the String.prototype.search() method instead.

Use test() whenever you want to know whether a pattern is found in a string. test() returns a boolean, unlike the String.prototype.search() method (which returns the index of a match, or -1 if not found).

To get more information (but with slower execution), use the exec() method. (This is similar to the String.prototype.match() method.)

As with exec() (or in combination with it), test() called multiple times on the same global regular expression instance will advance past the previous match.

十进制转二进制 x.toString(2)
二进制转十进制 parseInt(x, 2)

n & n - 1 === 0 is power of 2

n & 1 可以判断末尾是否为零

```
2的1次方：2
2的2次方：4
2的3次方：8
2的4次方：16
2的5次方：32
2的6次方：64
2的7次方：128
2的8次方：256
2的9次方：512
2的10次方：1024
2的11次方：2048
2的12次方：4096
2的13次方：8192
2的14次方：16384
2的15次方：32768
2的16次方：65536
2的17次方：131072
2的18次方：262144
2的19次方：524288
2的20次方：1048576
2的21次方：2097152
2的22次方：4194304
2的23次方：8388608
2的24次方：16777216
2的25次方：33554432
2的26次方：67108864
2的27次方：134217728
2的28次方：268435456
2的29次方：536870912
2的30次方：1073741824
2的31次方：2147483648
2的32次方：4294967296
2的33次方：8589934592
2的34次方：17179869184
2的35次方：34359738368
2的36次方：68719476736
2的37次方：137438953472
2的38次方：274877906944
2的39次方：549755813888
2的40次方：1099511627776
2的41次方：2199023255552
2的42次方：4398046511104
2的43次方：8796093022208
2的44次方：17592186044416
2的45次方：35184372088832
2的46次方：70368744177664
2的47次方：140737488355328
2的48次方：281474976710656
2的49次方：562949953421312
2的50次方：1125899906842624
2的51次方：2251799813685248
2的52次方：4503599627370496
2的53次方：9007199254740992
2的54次方：18014398509481984
2的55次方：36028797018963968
2的56次方：72057594037927936
2的57次方：144115188075855872
2的58次方：288230376151711744
2的59次方：576460752303423488
2的60次方：1152921504606846976
2的61次方：2305843009213693952
2的62次方：4611686018427387904
2的63次方：9223372036854775808
2的64次方：18446744073709551616
————————————————
版权声明：本文为CSDN博主「Rand Tsui」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/for_cxc/article/details/85229922
```

```js
let arr = new Array(2).fill([]); //now arr is: [ [ ], [ ] ];

arr[0].push(5); // [ [ 5 ], [ 5 ] ] it will set all arr elements is [ 5 ], because fill cause array share point, The push() method is a mutating method. It changes the length and the content of this.

// you need to do below method,  the value of this to be the same
arr[0] = [...arr[0], 5];
arr[0] = arr[0].concat(5);
```

The range of uppercase characters is from 65 ('A') to 90 ('Z'). The range of lowercase characters is from 97 ('a') to 122 ('z').
48 ('0' 零) 79 ('O' 大写 O) 111 ('o' 小写 o);

```
"31": "",      "32": " ",     "33": "!",     "34": "\"",    "35": "#",
"36": "$",     "37": "%",     "38": "&",     "39": "'",     "40": "(",
"41": ")",     "42": "*",     "43": "+",     "44": ",",     "45": "-",
"46": ".",     "47": "/",     "48": "0",     "49": "1",     "50": "2",
"51": "3",     "52": "4",     "53": "5",     "54": "6",     "55": "7",
"56": "8",     "57": "9",     "58": ":",     "59": ";",     "60": "<",
"61": "=",     "62": ">",     "63": "?",     "64": "@",     "65": "A",
"66": "B",     "67": "C",     "68": "D",     "69": "E",     "70": "F",
"71": "G",     "72": "H",     "73": "I",     "74": "J",     "75": "K",
"76": "L",     "77": "M",     "78": "N",     "79": "O",     "80": "P",
"81": "Q",     "82": "R",     "83": "S",     "84": "T",     "85": "U",
"86": "V",     "87": "W",     "88": "X",     "89": "Y",     "90": "Z",
"91": "[",     "92": "\\",    "93": "]",     "94": "^",     "95": "_",
"96": "`",     "97": "a",     "98": "b",     "99": "c",     "100": "d",
"101": "e",    "102": "f",    "103": "g",    "104": "h",    "105": "i",
"106": "j",    "107": "k",    "108": "l",    "109": "m",    "110": "n",
"111": "o",    "112": "p",    "113": "q",    "114": "r",    "115": "s",
"116": "t",    "117": "u",    "118": "v",    "119": "w",    "120": "x",
"121": "y",    "122": "z",    "123": "{",    "124": "|",    "125": "}",
"126": "~",    "127": ""
```

[Sparse arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays)
These methods treat empty slots as if they are undefined:

entries()
fill()
find()
findIndex()
findLast()
findLastIndex()
group()
groupToMap()
includes()
join()
keys() (array, not true object)
toLocaleString()
values() (array, not true object)

also arr[i] and [...arr], for of iteration;

```js
const arrayLike = {
  0: "a",
  1: "b",
  length: 2,
};
console.log(Array.prototype.join.call(arrayLike, "+")); // 'a+b'

Array.prototype.flat.call({}); // []

const a = { length: 0.7 };
Array.prototype.push.call(a);
console.log(a.length); // 0
```

Array.prototype.values() is the default implementation of Array.prototype[@@iterator]().

```js
Array.prototype.values === Array.prototype[Symbol.iterator]; // true
```

2^32 = 2147483648

Math.ceil(x) = -Math.floor(-x)

MAX_VALUE = 1.7976931348623157e308 = 9007199254740992e102 = 2^1024-1

Number.MAX_SAFE_INTEGER = 2^53 – 1 = 9007199254740991

The safe integers consist of all integers from -(2^53 - 1) to 2^53 - 1, inclusive (±9,007,199,254,740,991).

Number.EPSILON = 2^-52

when you do bitwise algorithm, the first step is list truth table
The truth table for the AND operation is:
| a | b | a AND b |
| - | - | ------- |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

The truth table for the NOT operation is:
| a | NOT a |
| - | ----- |
| 0 | 1 |
| 1 | 0 |

The truth table for the OR operation is:
| a | b | a OR b |
| - | - | ------- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

The truth table for the XOR operation is:
| a | b | a XOR b |
| - | - | ------- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

1. The bitwise AND operator (&) returns a 1 in each bit position for which the corresponding bits of both operands are 1s.
   1. Bitwise ANDing any number x with 0 yields 0.
2. The bitwise AND assignment operator (&=) uses the binary representation of both operands, does a bitwise AND operation on them and assigns the result to the variable.
3. The bitwise NOT operator (~) inverts the bits of its operand. Like other bitwise operators, it converts the operand to a 32-bit signed integer
   1. The 32-bit signed integer operand is inverted according to two's complement. That is, the presence of the most significant bit is used to express negative integers.
   2. Bitwise NOTing any number x yields -(x + 1). For example, ~-5 yields 4
4. The bitwise OR operator (|) returns a 1 in each bit position for which the corresponding bits of either or both operands are 1s.
   1. Bitwise ORing any number x with 0 yields x converted to a 32-bit integer.
5. The bitwise OR assignment operator (|=) uses the binary representation of both operands, does a bitwise OR operation on them and assigns the result to the variable.
6. The bitwise XOR operator (^) returns a 1 in each bit position for which the corresponding bits of either but not both operands are 1s.
   1. Bitwise XORing any number x with 0 yields x.
   2. 不能进位 只能保持原位
7. The bitwise XOR assignment operator (^=) uses the binary representation of both operands, does a bitwise XOR operation on them and assigns the result to the variable.
8. The left shift operator (<<) shifts the first operand the specified number of bits, modulo 32, to the left. Excess bits shifted off to the left are discarded. Zero bits are shifted in from the right.
   1. Bitwise shifting any number x to the left by y bits yields x \* 2 \*\* y
   2. The right operand will be converted to an unsigned 32-bit integer and then taken modulo 32, so the actual shift offset will always be a positive integer between 0 and 31, inclusive. For example, 100 << 32 is the same as 100 << 0 (and produces 100) because 32 modulo 32 is 0.
9. The left shift assignment operator (<<=) moves the specified amount of bits to the left and assigns the result to the variable.
10. The logical AND assignment (x &&= y) operator only assigns if x is truthy.
11. The logical nullish assignment (x ??= y) operator only assigns if x is nullish (null or undefined).
12. The logical OR assignment (x ||= y) operator only assigns if x is falsy.
13. The right shift operator (>>) returns the signed number represented by the result of performing a sign-extending shift of the binary representation of the first operand (evaluated as a two's complement bit string) to the right by the number of bits, modulo 32, specified in the second operand. Excess bits shifted off to the right are discarded, and copies of the leftmost bit are shifted in from the left.
    1. The left operand will be converted to a 32-bit integer, which means floating point numbers will be truncated, and number not within the 32-bit bounds will over-/underflow.
    2. The right operand will be converted to an unsigned 32-bit integer and then taken modulo 32, so the actual shift offset will always be a positive integer between 0 and 31, inclusive. For example, 100 >> 32 is the same as 100 >> 0 (and produces 100) because 32 modulo 32 is 0.
14. The right shift assignment operator (>>=) moves the specified amount of bits to the right and assigns the result to the variable.
15. The unsigned right shift operator (>>>) (zero-fill right shift) evaluates the left-hand operand as an unsigned number, and shifts the binary representation of that number by the number of bits, modulo 32, specified by the right-hand operand. Excess bits shifted off to the right are discarded, and zero bits are shifted in from the left. The sign bit becomes 0, so the result is always non-negative. Unlike the other bitwise operators, zero-fill right shift returns an unsigned 32-bit integer.
16. The unsigned right shift assignment operator (>>>=) moves the specified amount of bits to the right and assigns the result to the variable.

17. The exponentiation operator (\*\*) returns the result of raising the first operand to the power of the second operand. It is equivalent to Math.pow, except it also accepts BigInts as operands.
    1. 2 ** -2 = (1 / 2) ** 2 = 0.25
18. The exponentiation assignment operator (\*\*=) raises the value of a variable to the power of the right operand.

The operands are converted to 32-bit integers and expressed by a series of bits (zeroes and ones). Numbers with more than 32 bits get their most significant bits discarded. For example, the following integer with more than 32 bits will be converted to a 32-bit integer:

```js
Before: 11100110111110100000000000000110000000000001;
After: 10100000000000000110000000000001;
```

如果最低位为 1，那么令计数器加一: ret += s & 1;

十进制负数转换为二进制的方法为：

1. 将十进制转换为二进制数。
2. 对该二进制数求反。
3. 再将该二进制数加 1.
   总之就是将十进制数转换为二进制数求补码即为结果。比如：
   -32
   第一步：32（10）=00100000（2）
   第二步：求反：11011111
   第三步：加 1:11100000
   所以-32（10）=11100000（2）
4. [十进制互转二进制](https://zhuanlan.zhihu.com/p/75291280)

```js
function isInt(n) {
  return Number(n) === n && n % 1 === 0;
}

function isFloat(n) {
  return Number(n) === n && n % 1 !== 0;
}
```

| 12-hour clock | 24-hour clock |
| ------------- | ------------- |
| 1am           | 01:00         |
| 2am           | 02:00         |
| 3am           | 03:00         |
| 4am           | 04:00         |
| 5am           | 05:00         |
| 6am           | 06:00         |
| 7am           | 07:00         |
| 8am           | 08:00         |
| 9am           | 09:00         |
| 10am          | 10:00         |
| 11am          | 11:00         |
| 12pm          | 12:00         |
| 1pm           | 13:00         |
| 2pm           | 14:00         |
| 3pm           | 15:00         |
| 4pm           | 16:00         |
| 5pm           | 17:00         |
| 6pm           | 18:00         |
| 7pm           | 19:00         |
| 8pm           | 20:00         |
| 9pm           | 21:00         |
| 10pm          | 22:00         |
| 11pm          | 23:00         |
| 12am          | 00:00         |

### [Plus Minus](https://www.hackerrank.com/challenges/one-month-preparation-kit-plus-minus/problem?h_l=interview&isFullScreen=true&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

need to check solution

optimize according to constraints

```js
"use strict";

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'plusMinus' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function plusMinus(arr) {
  // Write your code here
  let positive = 0,
    negative = 0,
    zero = 0,
    len = arr.length || 0;

  if (len > 0 && len <= 100) {
    for (const value of arr) {
      if (value > 0) {
        positive++;
      } else if (value < 0) {
        negative++;
      } else {
        zero++;
      }
    }
  }

  console.log(
    `${(positive / len).toFixed(6)}\n${(negative / len).toFixed(6)}\n${(
      zero / len
    ).toFixed(6)}`
  );
}

function main() {
  const n = parseInt(readLine().trim(), 10);

  const arr = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((arrTemp) => parseInt(arrTemp, 10));

  plusMinus(arr);
}
```

### [Min-Max Sum](https://www.hackerrank.com/challenges/one-month-preparation-kit-mini-max-sum/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'miniMaxSum' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function miniMaxSum(arr) {
  // // Write your code here
  let sum = 0,
    min = 1000000000,
    max = 1;

  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];

    if (min > arr[i]) {
      min = arr[i];
    }

    if (max < arr[i]) {
      max = arr[i];
    }
  }

  console.log(`${sum - max} ${sum - min}`);
}

function main() {
  const arr = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((arrTemp) => parseInt(arrTemp, 10));

  miniMaxSum(arr);
}
```

### [Sparse Array](https://www.hackerrank.com/challenges/one-month-preparation-kit-sparse-arrays/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'matchingStrings' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. STRING_ARRAY strings
 *  2. STRING_ARRAY queries
 */

function matchingStrings(strings, queries) {
  return queries.map((query) =>
    strings.reduce((sum, str) => (str === query ? sum + 1 : sum), 0)
  );
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const stringsCount = parseInt(readLine().trim(), 10);

  let strings = [];

  for (let i = 0; i < stringsCount; i++) {
    const stringsItem = readLine();
    strings.push(stringsItem);
  }

  const queriesCount = parseInt(readLine().trim(), 10);

  let queries = [];

  for (let i = 0; i < queriesCount; i++) {
    const queriesItem = readLine();
    queries.push(queriesItem);
  }

  const res = matchingStrings(strings, queries);

  ws.write(res.join("\n") + "\n");

  ws.end();
}
```

### [Lonely Integer](https://www.hackerrank.com/challenges/one-month-preparation-kit-lonely-integer/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'lonelyinteger' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts INTEGER_ARRAY a as parameter.
 */

function lonelyinteger(a) {
  // Write your code here
  let poped = a.pop();

  while (a.includes(poped)) {
    a = a.filter((value) => value !== poped);
    poped = a.pop();
  }

  return poped;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const a = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((aTemp) => parseInt(aTemp, 10));

  const result = lonelyinteger(a);

  ws.write(result + "\n");

  ws.end();
}
```

### [Flipping bits](https://www.hackerrank.com/challenges/one-month-preparation-kit-flipping-bits/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'flippingBits' function below.
 *
 * The function is expected to return a LONG_INTEGER.
 * The function accepts LONG_INTEGER n as parameter.
 */

function flippingBits(n) {
  // Write your code here
  return ~n >>> 0;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const q = parseInt(readLine().trim(), 10);

  for (let qItr = 0; qItr < q; qItr++) {
    const n = parseInt(readLine().trim(), 10);

    const result = flippingBits(n);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Diagonal Difference](https://www.hackerrank.com/challenges/one-month-preparation-kit-diagonal-difference/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'diagonalDifference' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts 2D_INTEGER_ARRAY arr as parameter.
 */

function diagonalDifference(arr) {
  // Write your code here
  let length = arr.length,
    difference = 0;

  for (let i = 0; i < length; i++) {
    difference += arr[i][i] - arr[i][length - 1 - i];
  }

  return Math.abs(difference);
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  let arr = Array(n);

  for (let i = 0; i < n; i++) {
    arr[i] = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((arrTemp) => parseInt(arrTemp, 10));
  }

  const result = diagonalDifference(arr);

  ws.write(result + "\n");

  ws.end();
}
```

### [Counting Sort 1](https://www.hackerrank.com/challenges/one-month-preparation-kit-countingsort1/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'countingSort' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function countingSort(arr) {
  // Write your code here
  let length = arr.length,
    result = new Array(100).fill(0);

  for (let i = 0; i < length; i++) {
    result[arr[i]]++;
  }

  return result;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const arr = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((arrTemp) => parseInt(arrTemp, 10));

  const result = countingSort(arr);

  ws.write(result.join(" ") + "\n");

  ws.end();
}
```

### [Pangrams](https://www.hackerrank.com/challenges/one-month-preparation-kit-pangrams/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'pangrams' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING s as parameter.
 */

function pangrams(s) {
  if (new Set(s.toLowerCase()).size === 27) {
    return "pangram";
  } else {
    return "not pangram";
  }
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const s = readLine();

  const result = pangrams(s);

  ws.write(result + "\n");

  ws.end();
}
```

### [Permuting Two Arrays](https://www.hackerrank.com/challenges/one-month-preparation-kit-two-arrays/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'twoArrays' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts following parameters:
 *  1. INTEGER k
 *  2. INTEGER_ARRAY A
 *  3. INTEGER_ARRAY B
 */

function twoArrays(k, A, B) {
  // Write your code here
  let length = A.length,
    exist = 0;

  A.sort((a, b) => a - b);
  B.sort((a, b) => b - a);

  for (let i = 0; i < length; i++) {
    if (A[i] + B[i] < k) {
      exist = 1;
      break;
    }
  }

  return exist ? "NO" : "YES";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const q = parseInt(readLine().trim(), 10);

  for (let qItr = 0; qItr < q; qItr++) {
    const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

    const n = parseInt(firstMultipleInput[0], 10);

    const k = parseInt(firstMultipleInput[1], 10);

    const A = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((ATemp) => parseInt(ATemp, 10));

    const B = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((BTemp) => parseInt(BTemp, 10));

    const result = twoArrays(k, A, B);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Subarray Division 1](https://www.hackerrank.com/challenges/one-month-preparation-kit-the-birthday-bar/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-one)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'birthday' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY s
 *  2. INTEGER d
 *  3. INTEGER m
 */

function birthday(s, d, m) {
  // Write your code here
  let length = s.length,
    ways = 0;

  if (m > length) {
    return 0;
  }

  for (let i = 0; i + m <= length; i++) {
    if (s.slice(i, i + m).reduce((a, b) => a + b, 0) === d) {
      ways++;
    }
  }

  return ways;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const s = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((sTemp) => parseInt(sTemp, 10));

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const d = parseInt(firstMultipleInput[0], 10);

  const m = parseInt(firstMultipleInput[1], 10);

  const result = birthday(s, d, m);

  ws.write(result + "\n");

  ws.end();
}
```

### [Sales by Match](https://www.hackerrank.com/challenges/one-month-preparation-kit-sock-merchant/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'sockMerchant' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER n
 *  2. INTEGER_ARRAY ar
 */

function sockMerchant(n, ar) {
  // Write your code here
  // let lastIndex = 0, pairs = 0;
  // ar.sort((a, b) =>  a - b);

  // for(let i = 0; i < n; ) {
  //     lastIndex = ar.findLastIndex(element => element === ar[i]);
  //     if (i === lastIndex) {
  //         i++;
  //     } else {
  //         pairs += Math.floor((lastIndex + 1 - i) / 2);
  //         i = lastIndex + 1;
  //     }
  // }

  // return pairs;

  let frequency = {};

  for (let i = 0; i < n; i++) {
    frequency[ar[i]] = (frequency[ar[i]] || 0) + 1;
  }

  return Object.values(frequency)
    .map((element) => Math.floor(element / 2))
    .reduce((a, b) => a + b, 0);
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const ar = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((arTemp) => parseInt(arTemp, 10));

  const result = sockMerchant(n, ar);

  ws.write(result + "\n");

  ws.end();
}
```

### [Zig Zag Sequence](https://www.hackerrank.com/challenges/one-month-preparation-kit-zig-zag-sequence/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```c++
#include <bits/stdc++.h>
using namespace std;

void findZigZagSequence(vector < int > a, int n){
    sort(a.begin(), a.end());
    int mid = (n + 1)/2 - 1;
    swap(a[mid], a[n-1]);

    int st = mid + 1;
    int ed = n - 2;
    while(st <= ed){
        swap(a[st], a[ed]);
        st = st + 1;
        ed = ed - 1;
    }
    for(int i = 0; i < n; i++){
        if(i > 0) cout << " ";
        cout << a[i];
    }
    cout << endl;
}

int main() {
    int n, x;
    int test_cases;
    cin >> test_cases;

    for(int cs = 1; cs <= test_cases; cs++){
        cin >> n;
        vector < int > a;
        for(int i = 0; i < n; i++){
            cin >> x;
            a.push_back(x);
        }
        findZigZagSequence(a, n);
    }
}
```

### [Drawing Book](https://www.hackerrank.com/challenges/one-month-preparation-kit-drawing-book/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'pageCount' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER n
 *  2. INTEGER p
 */

function pageCount(n, p) {
  // Write your code here
  let leftTurn = Math.floor(p / 2),
    rightTurn = Math.floor(n / 2) - leftTurn;

  return leftTurn < rightTurn ? leftTurn : rightTurn;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const p = parseInt(readLine().trim(), 10);

  const result = pageCount(n, p);

  ws.write(result + "\n");

  ws.end();
}
```

### [Tower Breakers](https://www.hackerrank.com/challenges/one-month-preparation-kit-tower-breakers-1/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'towerBreakers' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER n
 *  2. INTEGER m
 */

function towerBreakers(n, m) {
  // Write your code here
  return m === 1 || n % 2 === 0 ? 2 : 1;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

    const n = parseInt(firstMultipleInput[0], 10);

    const m = parseInt(firstMultipleInput[1], 10);

    const result = towerBreakers(n, m);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Caesar Cipher](https://www.hackerrank.com/challenges/one-month-preparation-kit-caesar-cipher-1/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'caesarCipher' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts following parameters:
 *  1. STRING s
 *  2. INTEGER k
 */

function caesarCipher(s, k) {
  let encrypted = "";

  k %= 26;

  for (let i = 0; i < s.length; i++) {
    let charCode = s[i].charCodeAt(0);

    if (charCode >= 65 && charCode <= 90) {
      charCode = charCode + (charCode + k > 90 ? k - 26 : k);
    } else if (charCode >= 97 && charCode <= 122) {
      charCode = charCode + (charCode + k > 122 ? k - 26 : k);
    }

    encrypted += String.fromCharCode(charCode);
  }

  return encrypted;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const s = readLine();

  const k = parseInt(readLine().trim(), 10);

  const result = caesarCipher(s, k);

  ws.write(result + "\n");

  ws.end();
}
```

### [Max Min](https://www.hackerrank.com/challenges/one-month-preparation-kit-angry-children/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'maxMin' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER k
 *  2. INTEGER_ARRAY arr
 */

function maxMin(k, arr) {
  // Write your code here
  let result = 0,
    length = arr.length;

  arr.sort((a, b) => a - b);
  result = arr[k - 1] - arr[0];

  for (let i = k; i < length; i++) {
    result = Math.min(result, arr[i] - arr[i - k + 1]);
  }

  return result;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const k = parseInt(readLine().trim(), 10);

  let arr = [];

  for (let i = 0; i < n; i++) {
    const arrItem = parseInt(readLine().trim(), 10);
    arr.push(arrItem);
  }

  const result = maxMin(k, arr);

  ws.write(result + "\n");

  ws.end();
}
```

### [Dynamic Array](https://www.hackerrank.com/challenges/one-month-preparation-kit-dynamic-array/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'dynamicArray' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER n
 *  2. 2D_INTEGER_ARRAY queries
 */

function dynamicArray(n, queries) {
  // Write your code here
  let arr = new Array(n).fill([]),
    lastAnswer = 0,
    length = queries.length,
    idx = 0,
    answers = [];

  for (let i = 0; i < length; i++) {
    let [number, x, y] = queries[i];
    idx = (x ^ lastAnswer) % n;

    if (number === 1) {
      arr[idx] = [...arr[idx], y];
    } else {
      lastAnswer = arr[idx][y % arr[idx].length];
      answers.push(lastAnswer);
    }
  }

  return answers;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const n = parseInt(firstMultipleInput[0], 10);

  const q = parseInt(firstMultipleInput[1], 10);

  let queries = Array(q);

  for (let i = 0; i < q; i++) {
    queries[i] = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((queriesTemp) => parseInt(queriesTemp, 10));
  }

  const result = dynamicArray(n, queries);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

### [Grid Challenge](https://www.hackerrank.com/challenges/one-month-preparation-kit-grid-challenge/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'gridChallenge' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING_ARRAY grid as parameter.
 */

function gridChallenge(grid) {
  // Write your code here
  let length = grid.length;

  for (let i = 0; i < length; i++) {
    grid[i] = [...grid[i]].sort().join("");

    if (i > 0) {
      for (let j = 0; j < length; j++) {
        if (grid[i - 1][j] > grid[i][j]) {
          return "NO";
        }
      }
    }
  }

  return "YES";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    let grid = [];

    for (let i = 0; i < n; i++) {
      const gridItem = readLine();
      grid.push(gridItem);
    }

    const result = gridChallenge(grid);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Prime Dates](https://www.hackerrank.com/challenges/one-month-preparation-kit-prime-date/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```
#include <bits/stdc++.h>
using namespace std;

int month[15];

void updateLeapYear(int year) {

// ((year % 4 == 0) && (year % 100 != 0)) || (year % 400 == 0);
//(year % 100 === 0) ? (year % 400 === 0) : (year % 4 === 0);
    if(year % 400 == 0) {
        month[2] = 29;
    } else if(year % 100 == 0) {
        month[2] = 28;
    } else if(year % 4 == 0) {
        month[2] = 29;
    } else {
        month[2] = 28;
    }
}

void storeMonth() {
    month[1] = 31;
    month[2] = 28;
    month[3] = 31;
    month[4] = 30;
    month[5] = 31;
    month[6] = 30;
    month[7] = 31;
    month[8] = 31;
    month[9] = 30;
    month[10] = 31;
    month[11] = 30;
    month[12] = 31;
}

int findLuckyDates(int d1, int m1, int y1, int d2, int m2, int y2) {
    storeMonth();

    int result = 0;

    while(true) {
        int x = d1;
        x = x * 100 + m1;
        x = x * 10000 + y1;
        if(x % 4 == 0 || x % 7 == 0) {
            result = result + 1;
        }
        if(d1 == d2 && m1 == m2 && y1 == y2) {
            break;
        }
        updateLeapYear(y1);
        d1 = d1 + 1;
        if(d1 > month[m1]) {
            m1 = m1 + 1;
            d1 = 1;
            if(m1 > 12) {
                y1 =  y1 + 1;
                m1 = 1;
            }
        }
    }
    return result;
}

int main() {
    string str;
    int d1, m1, y1, d2, m2, y2;
    getline(cin, str);
    for(int i = 0; i < str.size(); i++) {
        if(str[i] == '-') {
            str[i] = ' ';
        }
    }
    stringstream ss;
    ss << str;
    ss >> d1 >> m1 >> y1 >> d2 >> m2 >> y2;

    int result = findLuckyDates(d1, m1, y1, d2, m2, y2);
    cout << result << endl;
}
```

### [Sherlock and Array](https://www.hackerrank.com/challenges/one-month-preparation-kit-sherlock-and-array/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'balancedSums' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function balancedSums(arr) {
  // Write your code here
  // let length = arr.length;

  // if (arr.length === 1) {
  //     return 'YES';
  // }

  // let filtered = arr.filter(element => element !== 0),
  //     length = filtered.length;

  // if (length === 1) {
  //     return 'YES';
  // }

  // for (let i = 0; i < length; i++) {
  //     let left = 0, right = 0, j = 0, k = i + 1;

  //     for (let j = 0; j < i; j++) {
  //         left += arr[j];
  //     }

  //     for (let k = i + 1; k < length; k++) {
  //         right += arr[k];
  //     }

  //     if (left === right) {
  //         return 'YES';
  //     }

  //     // while(j < i || k < length) {
  //     //     console.log(i, j, k);
  //     //     if (j < i) {
  //     //         left += filtered[j];
  //     //         j++;
  //     //     }

  //     //     if (k < length) {
  //     //         right += filtered[k];
  //     //         k++;
  //     //     }

  //     //     if (left === right) {
  //     //         return 'YES';
  //     //     }
  //     // }

  // }

  let allSum = arr.reduce((a, b) => a + b, 0),
    leftSum = 0,
    length = arr.length;

  for (let i = 0; i < length; i++) {
    allSum -= arr[i];

    if (leftSum === allSum) {
      return "YES";
    }

    leftSum += arr[i];
  }

  return "NO";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const T = parseInt(readLine().trim(), 10);

  for (let TItr = 0; TItr < T; TItr++) {
    const n = parseInt(readLine().trim(), 10);

    const arr = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((arrTemp) => parseInt(arrTemp, 10));

    const result = balancedSums(arr);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Recursive Digit Sum](https://www.hackerrank.com/challenges/one-month-preparation-kit-recursive-digit-sum/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'superDigit' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. STRING n
 *  2. INTEGER k
 */

function superDigit(n, k) {
  // Write your code here

  if (n < 10 && k === 1) return +n;

  let sum = n.split("").reduce((a, b) => +a + +b) * k;

  return superDigit(sum + "", 1);
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const n = firstMultipleInput[0];

  const k = parseInt(firstMultipleInput[1], 10);

  const result = superDigit(n, k);

  ws.write(result + "\n");

  ws.end();
}
```

### [Counter game](https://www.hackerrank.com/challenges/one-month-preparation-kit-counter-game/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'counterGame' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts LONG_INTEGER n as parameter.
 */

function counterGame(n) {
  let Louise = false;

  while (n > 1) {
    let power = [];

    for (let i = 1; 2 ** i <= n; i++) {
      power.push(2 ** i);
    }

    if (power[power.length - 1] !== n) {
      n -= power[power.length - 1];
    } else {
      n /= 2;
    }

    Louise = !Louise;
  }

  return Louise ? "Louise" : "Richard";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const result = counterGame(n);

    ws.write(result + "\n");
  }

  ws.end();
}
```

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'counterGame' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts LONG_INTEGER n as parameter.
 */

function counterGame(n) {
  let Louise = (n - 1).toString(2).match(/1/g).length;

  return Louise % 2 ? "Louise" : "Richard";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const result = counterGame(n);

    ws.write(result + "\n");
  }

  ws.end();
}
```

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'counterGame' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts LONG_INTEGER n as parameter.
 */

function counterGame(n) {
  let Louise = false;

  while (n > 1) {
    let m = Math.floor(Math.log2(n));

    2 ** m === n ? (n /= 2) : (n -= 2 ** m);

    Louise = !Louise;
  }

  return Louise ? "Louise" : "Richard";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const result = counterGame(n);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Sum vs XOR](https://www.hackerrank.com/challenges/one-month-preparation-kit-sum-vs-xor/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-two)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'sumXor' function below.
 *
 * The function is expected to return a LONG_INTEGER.
 * The function accepts LONG_INTEGER n as parameter.
 */

function sumXor(n) {
  // Write your code here

  if (n > 1) {
    return 2 ** n.toString(2).match(/0/g).length;
  } else {
    return 1;
  }
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const n = parseInt(readLine().trim(), 10);

  const result = sumXor(n);

  ws.write(result + "\n");

  ws.end();
}
```

### [The Bomberman Game](https://www.hackerrank.com/challenges/one-month-preparation-kit-bomber-man/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

#### timeout

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'bomberMan' function below.
 *
 * The function is expected to return a STRING_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER n
 *  2. STRING_ARRAY grid
 */

function bomberMan(n, grid) {
  // Write your code here
  if (n === 1) return;

  let r = grid.length,
    c = grid[0].length,
    track = [];

  for (let i = 0; i < r; i++) {
    grid[i] = grid[i].split("");
  }

  for (let time = 1; time <= n; time++) {
    if (time % 2 === 0) {
      for (let i = 0; i < r; i++) {
        for (let j = 0; j < c; j++) {
          if (grid[i][j] === "O") {
            track.push([i, j]);
          }
        }
      }

      // grid = new Array(r).fill(new Array(c).fill("O")); this one step is wrong
      grid = new Array(r);

      for (let i = 0; i < r; i++) {
        grid[i] = new Array(c).fill("O");
      }
    } else {
      for (let k = 0; k < track.length; k++) {
        let [i, j] = track[k];

        if (i + 1 < r) {
          grid[i + 1][j] = ".";
        }

        if (i - 1 >= 0) {
          grid[i - 1][j] = ".";
        }

        if (j + 1 < c) {
          grid[i][j + 1] = ".";
        }

        if (j - 1 >= 0) {
          grid[i][j - 1] = ".";
        }

        grid[i][j] = ".";
      }

      track = [];
    }
  }

  for (let i = 0; i < r; i++) {
    grid[i] = grid[i].join("");
  }

  return grid;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const r = parseInt(firstMultipleInput[0], 10);

  const c = parseInt(firstMultipleInput[1], 10);

  const n = parseInt(firstMultipleInput[2], 10);

  let grid = [];

  for (let i = 0; i < r; i++) {
    const gridItem = readLine();
    grid.push(gridItem);
  }

  const result = bomberMan(n, grid);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

#### official

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'bomberMan' function below.
 *
 * The function is expected to return a STRING_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER n
 *  2. STRING_ARRAY grid
 */

function bomberMan(n, grid) {
  // Write your code here
  let r = grid.length,
    c = grid[0].length,
    temp = new Array(r).fill([]).map((_) => []);

  for (let i = 0; i < r; i++) {
    grid[i] = grid[i].split("");
  }

  if (n % 2 === 0) {
    //   grid = new Array(r).fill([]).map(_ => new Array(c).fill('O'));
    return new Array(r).fill("O".repeat(c));
  } else {
    n = Math.floor(n / 2);

    for (let it = 0; it < Math.min(n, ((n + 1) % 2) + 1); it++) {
      let ngrid = new Array(r).fill([]).map((_) => new Array(c).fill("O"));

      function setGrid(i, j, ch) {
        if (0 <= i && i < r && 0 <= j && j < c) {
          ngrid[i][j] = ch;
        }
      }

      for (let i = 0; i < r; i++) {
        for (let j = 0; j < c; j++) {
          if (grid[i][j] === "O") {
            setGrid(i, j, ".");
            setGrid(i + 1, j, ".");
            setGrid(i - 1, j, ".");
            setGrid(i, j + 1, ".");
            setGrid(i, j - 1, ".");
          }
        }
      }

      grid = ngrid;
    }
  }

  for (let i = 0; i < r; i++) {
    grid[i] = grid[i].join("");
  }

  return grid;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const r = parseInt(firstMultipleInput[0], 10);

  const c = parseInt(firstMultipleInput[1], 10);

  const n = parseInt(firstMultipleInput[2], 10);

  let grid = [];

  for (let i = 0; i < r; i++) {
    const gridItem = readLine();
    grid.push(gridItem);
  }

  const result = bomberMan(n, grid);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

### [New Year Chaos](https://www.hackerrank.com/challenges/one-month-preparation-kit-new-year-chaos/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'minimumBribes' function below.
 *
 * The function accepts INTEGER_ARRAY q as parameter.
 */

function minimumBribes(q) {
  // Write your code here
  let length = q.length,
    success = true,
    expected = [],
    bribes = {},
    temp = 0;

  for (let i = 0; i < length; i++) {
    expected[i] = i + 1;
  }

  while (success) {
    if (q.toString() === expected.toString()) {
      break;
    } else {
      for (let i = 0; i < length - 1; i++) {
        if (q[i] > q[i + 1]) {
          bribes[q[i]] = bribes[q[i]] ? bribes[q[i]] + 1 : 1;

          if (bribes[q[i]] > 2) {
            success = false;
            break;
          }

          temp = q[i];
          q[i] = q[i + 1];
          q[i + 1] = temp;
        }
      }
    }
  }

  console.log(
    success ? Object.values(bribes).reduce((a, b) => a + b, 0) : "Too chaotic"
  );
}

function main() {
  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const q = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((qTemp) => parseInt(qTemp, 10));

    minimumBribes(q);
  }
}
```

### official

```js
"use strict";

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'minimumBribes' function below.
 *
 * The function accepts INTEGER_ARRAY q as parameter.
 */

function minimumBribes(q) {
  let n = q.length,
    bribes = 0;

  for (let i = n - 1; 0 <= i; i--) {
    if (q[i] !== i + 1) {
      if (i - 1 >= 0 && q[i - 1] === i + 1) {
        bribes++;
        q[i - 1] = q[i];
        q[i] = i + 1;
      } else if (i - 2 >= 0 && q[i - 2] === i + 1) {
        bribes += 2;
        q[i - 2] = q[i - 1];
        q[i - 1] = q[i];
        q[i] = i + 1;
      } else {
        console.log("Too chaotic");
        return;
      }
    }
  }

  console.log(bribes);
  return;
}

function main() {
  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const q = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((qTemp) => parseInt(qTemp, 10));

    minimumBribes(q);
  }
}
```

### [Sherlock and the Valid String](https://www.hackerrank.com/challenges/one-month-preparation-kit-sherlock-and-valid-string/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'isValid' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING s as parameter.
 */

function isValid(s) {
  // Write your code here
  let length = s.length,
    remove = 1,
    frequencies = {};

  for (let i = 0; i < length; i++) {
    frequencies[s[i]] = frequencies[s[i]] ? frequencies[s[i]] + 1 : 1;
  }

  let values = Object.values(frequencies),
    set = new Set(values),
    size = set.size;

  console.log(values);

  if (size === 1) {
    return "YES";
  } else if (size === 2) {
    console.log("hit");
    set = [...set];

    set.sort((a, b) => a - b);

    console.log("set: ", set);

    let length0 = values.filter((value) => value === set[0]).length,
      length1 = values.filter((value) => value === set[1]).length;

    console.log("length0 ", length0, "length1 ", length1);

    if (set[0] === 1 || set[1] - set[0] === 1) {
      if (length0 === 1 || (set[0] !== 1 && length1 === 1)) {
        return "YES";
      } else {
        return "NO";
      }
    } else {
      return "NO";
    }
  } else {
    return "NO";
  }
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const s = readLine();

  const result = isValid(s);

  ws.write(result + "\n");

  ws.end();
}
```

better

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'isValid' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING s as parameter.
 */

function isValid(s) {
  // Write your code here
  let length = s.length,
    frequencies = {},
    anwser = "NO";

  for (let i = 0; i < length; i++) {
    frequencies[s[i]] = frequencies[s[i]] ? frequencies[s[i]] + 1 : 1;
  }

  let values = Object.values(frequencies),
    set = new Set(values),
    size = set.size;

  if (size === 1) {
    anwser = "YES";
  }

  if (size === 2) {
    set = [...set];

    if (values.filter((value) => value === 1).length === 1) {
      anwser = "YES";
    } else {
      let sum = values.reduce((a, b) => a + b, 0) - 1,
        vLength = values.length;

      if (sum === set[0] * vLength || sum === set[1] * vLength) {
        anwser = "YES";
      }
    }
  }

  return anwser;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const s = readLine();

  const result = isValid(s);

  ws.write(result + "\n");

  ws.end();
}
```

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'climbingLeaderboard' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY ranked
 *  2. INTEGER_ARRAY player
 */

function climbingLeaderboard(ranked, player) {
  // Write your code here
  let denseRanked = [1],
    rankedLength = ranked.length,
    playerLength = player.length;

  for (let i = 1; i < rankedLength; i++) {
    if (ranked[i] === ranked[i - 1]) {
      denseRanked.push(denseRanked[denseRanked.length - 1]);
    } else {
      denseRanked.push(denseRanked[denseRanked.length - 1] + 1);
    }
  }

  for (let j = 0; j < playerLength; j++) {
    for (let i = ranked.length - 1; i >= 0; i--) {
      if (player[j] < ranked[i]) {
        player[j] = denseRanked[i] + 1;
        break;
      }

      if (player[j] === ranked[i]) {
        player[j] = denseRanked[i];
        break;
      }

      if (i === 0) {
        player[j] = 1;
      }
    }
  }

  return player;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const rankedCount = parseInt(readLine().trim(), 10);

  const ranked = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((rankedTemp) => parseInt(rankedTemp, 10));

  const playerCount = parseInt(readLine().trim(), 10);

  const player = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((playerTemp) => parseInt(playerTemp, 10));

  const result = climbingLeaderboard(ranked, player);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

### [Climbing the Leaderboard](https://www.hackerrank.com/challenges/one-month-preparation-kit-climbing-the-leaderboard/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three#!)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'climbingLeaderboard' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY ranked
 *  2. INTEGER_ARRAY player
 */

function climbingLeaderboard(ranked, player) {
  // Write your code here
  let denseRanked = [1],
    rankedLength = ranked.length,
    playerLength = player.length,
    k = rankedLength - 1;

  for (let i = 1; i < rankedLength; i++) {
    if (ranked[i] === ranked[i - 1]) {
      denseRanked.push(denseRanked[denseRanked.length - 1]);
    } else {
      denseRanked.push(denseRanked[denseRanked.length - 1] + 1);
    }
  }

  for (let j = 0; j < playerLength; j++) {
    while (k >= 0) {
      if (player[j] < ranked[k]) {
        player[j] = denseRanked[k] + 1;
        break;
      } else if (player[j] === ranked[k]) {
        player[j] = denseRanked[k];
        break;
      } else {
        k--;
      }
    }

    if (k === -1) {
      player[j] = 1;
    }
  }

  return player;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const rankedCount = parseInt(readLine().trim(), 10);

  const ranked = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((rankedTemp) => parseInt(rankedTemp, 10));

  const playerCount = parseInt(readLine().trim(), 10);

  const player = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((playerTemp) => parseInt(playerTemp, 10));

  const result = climbingLeaderboard(ranked, player);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'climbingLeaderboard' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY ranked
 *  2. INTEGER_ARRAY player
 */

function climbingLeaderboard(ranked, player) {
  // Write your code here
  let denseRanked = [1],
    rankedLength = ranked.length,
    playerLength = player.length,
    k = rankedLength - 1;

  for (let i = 1; i < rankedLength; i++) {
    if (ranked[i] === ranked[i - 1]) {
      denseRanked.push(denseRanked[denseRanked.length - 1]);
    } else {
      denseRanked.push(denseRanked[denseRanked.length - 1] + 1);
    }
  }

  for (let j = 0; j < playerLength; j++) {
    while (k >= 0 && player[j] > ranked[k]) {
      k--;
    }

    if (player[j] < ranked[k]) {
      player[j] = denseRanked[k] + 1;
    } else if (player[j] === ranked[k]) {
      player[j] = denseRanked[k];
    } else if (k === -1) {
      player[j] = 1;
    }
  }

  return player;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const rankedCount = parseInt(readLine().trim(), 10);

  const ranked = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((rankedTemp) => parseInt(rankedTemp, 10));

  const playerCount = parseInt(readLine().trim(), 10);

  const player = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((playerTemp) => parseInt(playerTemp, 10));

  const result = climbingLeaderboard(ranked, player);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

### [Reverse a linked list](https://www.hackerrank.com/challenges/one-month-preparation-kit-reverse-a-linked-list/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", (inputStdin) => {
  inputString += inputStdin;
});

process.stdin.on("end", (_) => {
  inputString = inputString
    .replace(/\s*$/, "")
    .split("\n")
    .map((str) => str.replace(/\s*$/, ""));

  main();
});

function readLine() {
  return inputString[currentLine++];
}

const SinglyLinkedListNode = class {
  constructor(nodeData) {
    this.data = nodeData;
    this.next = null;
  }
};

const SinglyLinkedList = class {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insertNode(nodeData) {
    const node = new SinglyLinkedListNode(nodeData);

    if (this.head == null) {
      this.head = node;
    } else {
      this.tail.next = node;
    }

    this.tail = node;
  }
};

function printSinglyLinkedList(node, sep, ws) {
  while (node != null) {
    ws.write(String(node.data));

    node = node.next;

    if (node != null) {
      ws.write(sep);
    }
  }
}

/*
 * Complete the 'reverse' function below.
 *
 * The function is expected to return an INTEGER_SINGLY_LINKED_LIST.
 * The function accepts INTEGER_SINGLY_LINKED_LIST llist as parameter.
 */

/*
 * For your reference:
 *
 * SinglyLinkedListNode {
 *     int data;
 *     SinglyLinkedListNode next;
 * }
 *
 */

function reverse(llist) {
  // Write your code here
  let store = [];
  while (llist.next) {
    store.push(llist);
    llist = llist.next;
  }

  let reversed = new SinglyLinkedList();

  reversed.insertNode(llist.data);

  for (let i = store.length - 1; i >= 0; i--) {
    reversed.insertNode(store[i].data);
  }

  return reversed.head;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const tests = parseInt(readLine(), 10);

  for (let testsItr = 0; testsItr < tests; testsItr++) {
    const llistCount = parseInt(readLine(), 10);

    let llist = new SinglyLinkedList();

    for (let i = 0; i < llistCount; i++) {
      const llistItem = parseInt(readLine(), 10);
      llist.insertNode(llistItem);
    }

    let llist1 = reverse(llist.head);

    printSinglyLinkedList(llist1, " ", ws);
    ws.write("\n");
  }

  ws.end();
}
```

official

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", (inputStdin) => {
  inputString += inputStdin;
});

process.stdin.on("end", (_) => {
  inputString = inputString
    .replace(/\s*$/, "")
    .split("\n")
    .map((str) => str.replace(/\s*$/, ""));

  main();
});

function readLine() {
  return inputString[currentLine++];
}

const SinglyLinkedListNode = class {
  constructor(nodeData) {
    this.data = nodeData;
    this.next = null;
  }
};

const SinglyLinkedList = class {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insertNode(nodeData) {
    const node = new SinglyLinkedListNode(nodeData);

    if (this.head == null) {
      this.head = node;
    } else {
      this.tail.next = node;
    }

    this.tail = node;
  }
};

function printSinglyLinkedList(node, sep, ws) {
  while (node != null) {
    ws.write(String(node.data));

    node = node.next;

    if (node != null) {
      ws.write(sep);
    }
  }
}

/*
 * Complete the 'reverse' function below.
 *
 * The function is expected to return an INTEGER_SINGLY_LINKED_LIST.
 * The function accepts INTEGER_SINGLY_LINKED_LIST llist as parameter.
 */

/*
 * For your reference:
 *
 * SinglyLinkedListNode {
 *     int data;
 *     SinglyLinkedListNode next;
 * }
 *
 */

function reverse(llist) {
  // Write your code here
  let nxt = null,
    tmp = null;

  while (llist) {
    tmp = llist.next;
    llist.next = nxt;
    nxt = llist;
    llist = tmp;
  }

  return nxt;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const tests = parseInt(readLine(), 10);

  for (let testsItr = 0; testsItr < tests; testsItr++) {
    const llistCount = parseInt(readLine(), 10);

    let llist = new SinglyLinkedList();

    for (let i = 0; i < llistCount; i++) {
      const llistItem = parseInt(readLine(), 10);
      llist.insertNode(llistItem);
    }

    let llist1 = reverse(llist.head);

    printSinglyLinkedList(llist1, " ", ws);
    ws.write("\n");
  }

  ws.end();
}
```

### [Reverse a doubly linked list](https://www.hackerrank.com/challenges/one-month-preparation-kit-reverse-a-doubly-linked-list/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", (inputStdin) => {
  inputString += inputStdin;
});

process.stdin.on("end", (_) => {
  inputString = inputString
    .replace(/\s*$/, "")
    .split("\n")
    .map((str) => str.replace(/\s*$/, ""));

  main();
});

function readLine() {
  return inputString[currentLine++];
}

const DoublyLinkedListNode = class {
  constructor(nodeData) {
    this.data = nodeData;
    this.next = null;
    this.prev = null;
  }
};

const DoublyLinkedList = class {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insertNode(nodeData) {
    let node = new DoublyLinkedListNode(nodeData);

    if (this.head == null) {
      this.head = node;
    } else {
      this.tail.next = node;
      node.prev = this.tail;
    }

    this.tail = node;
  }
};

function printDoublyLinkedList(node, sep, ws) {
  while (node != null) {
    ws.write(String(node.data));

    node = node.next;

    if (node != null) {
      ws.write(sep);
    }
  }
}

/*
 * Complete the 'reverse' function below.
 *
 * The function is expected to return an INTEGER_DOUBLY_LINKED_LIST.
 * The function accepts INTEGER_DOUBLY_LINKED_LIST llist as parameter.
 */

/*
 * For your reference:
 *
 * DoublyLinkedListNode {
 *     int data;
 *     DoublyLinkedListNode next;
 *     DoublyLinkedListNode prev;
 * }
 *
 */

function reverse(llist) {
  // Write your code here
  let nxt = null,
    tmp = null;

  while (llist) {
    tmp = llist.next;
    llist.next = nxt;
    llist.prev = tmp;
    nxt = llist;
    llist = tmp;
  }

  return nxt;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const llistCount = parseInt(readLine(), 10);

    let llist = new DoublyLinkedList();

    for (let i = 0; i < llistCount; i++) {
      const llistItem = parseInt(readLine(), 10);
      llist.insertNode(llistItem);
    }

    let llist1 = reverse(llist.head);

    printDoublyLinkedList(llist1, " ", ws);
    ws.write("\n");
  }

  ws.end();
}
```

### [Insert a node at a specific position in a linked list](https://www.hackerrank.com/challenges/one-month-preparation-kit-insert-a-node-at-a-specific-position-in-a-linked-list/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", (inputStdin) => {
  inputString += inputStdin;
});

process.stdin.on("end", (_) => {
  inputString = inputString
    .replace(/\s*$/, "")
    .split("\n")
    .map((str) => str.replace(/\s*$/, ""));

  main();
});

function readLine() {
  return inputString[currentLine++];
}

const SinglyLinkedListNode = class {
  constructor(nodeData) {
    this.data = nodeData;
    this.next = null;
  }
};

const SinglyLinkedList = class {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insertNode(nodeData) {
    const node = new SinglyLinkedListNode(nodeData);

    if (this.head == null) {
      this.head = node;
    } else {
      this.tail.next = node;
    }

    this.tail = node;
  }
};

function printSinglyLinkedList(node, sep, ws) {
  while (node != null) {
    ws.write(String(node.data));

    node = node.next;

    if (node != null) {
      ws.write(sep);
    }
  }
}

/*
 * Complete the 'insertNodeAtPosition' function below.
 *
 * The function is expected to return an INTEGER_SINGLY_LINKED_LIST.
 * The function accepts following parameters:
 *  1. INTEGER_SINGLY_LINKED_LIST llist
 *  2. INTEGER data
 *  3. INTEGER position
 */

/*
 * For your reference:
 *
 * SinglyLinkedListNode {
 *     int data;
 *     SinglyLinkedListNode next;
 * }
 *
 */

function insertNodeAtPosition(llist, data, position) {
  // Write your code here
  let head = llist,
    node = new SinglyLinkedListNode(data);

  if (position === 0) {
    node.next = llist;
    return node;
  }

  while (position-- > 1) {
    llist = llist.next;
  }

  node.next = llist.next;
  llist.next = node;

  return head;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const llistCount = parseInt(readLine(), 10);

  let llist = new SinglyLinkedList();

  for (let i = 0; i < llistCount; i++) {
    const llistItem = parseInt(readLine(), 10);
    llist.insertNode(llistItem);
  }

  const data = parseInt(readLine(), 10);

  const position = parseInt(readLine(), 10);

  let llist_head = insertNodeAtPosition(llist.head, data, position);

  printSinglyLinkedList(llist_head, " ", ws);
  ws.write("\n");

  ws.end();
}
```

### [Merge two sorted linked lists](https://www.hackerrank.com/challenges/one-month-preparation-kit-merge-two-sorted-linked-lists/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", (inputStdin) => {
  inputString += inputStdin;
});

process.stdin.on("end", (_) => {
  inputString = inputString
    .replace(/\s*$/, "")
    .split("\n")
    .map((str) => str.replace(/\s*$/, ""));

  main();
});

function readLine() {
  return inputString[currentLine++];
}

const SinglyLinkedListNode = class {
  constructor(nodeData) {
    this.data = nodeData;
    this.next = null;
  }
};

const SinglyLinkedList = class {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insertNode(nodeData) {
    const node = new SinglyLinkedListNode(nodeData);

    if (this.head == null) {
      this.head = node;
    } else {
      this.tail.next = node;
    }

    this.tail = node;
  }
};

function printSinglyLinkedList(node, sep, ws) {
  while (node != null) {
    ws.write(String(node.data));

    node = node.next;

    if (node != null) {
      ws.write(sep);
    }
  }
}

// Complete the mergeLists function below.

/*
 * For your reference:
 *
 * SinglyLinkedListNode {
 *     int data;
 *     SinglyLinkedListNode next;
 * }
 *
 */
function mergeLists(head1, head2) {
  let merged = new SinglyLinkedList(),
    data = [];
  while (head1) {
    data.push(head1.data);
    head1 = head1.next;
  }

  while (head2) {
    data.push(head2.data);
    head2 = head2.next;
  }

  data.sort((a, b) => a - b);

  for (let i = 0; i < data.length; i++) {
    merged.insertNode(data[i]);
  }

  return merged.head;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const tests = parseInt(readLine(), 10);

  for (let testsItr = 0; testsItr < tests; testsItr++) {
    const llist1Count = parseInt(readLine(), 10);

    let llist1 = new SinglyLinkedList();

    for (let i = 0; i < llist1Count; i++) {
      const llist1Item = parseInt(readLine(), 10);
      llist1.insertNode(llist1Item);
    }

    const llist2Count = parseInt(readLine(), 10);

    let llist2 = new SinglyLinkedList();

    for (let i = 0; i < llist2Count; i++) {
      const llist2Item = parseInt(readLine(), 10);
      llist2.insertNode(llist2Item);
    }

    let llist3 = mergeLists(llist1.head, llist2.head);

    printSinglyLinkedList(llist3, " ", ws);
    ws.write("\n");
  }

  ws.end();
}
```

official

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", (inputStdin) => {
  inputString += inputStdin;
});

process.stdin.on("end", (_) => {
  inputString = inputString
    .replace(/\s*$/, "")
    .split("\n")
    .map((str) => str.replace(/\s*$/, ""));

  main();
});

function readLine() {
  return inputString[currentLine++];
}

const SinglyLinkedListNode = class {
  constructor(nodeData) {
    this.data = nodeData;
    this.next = null;
  }
};

const SinglyLinkedList = class {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  insertNode(nodeData) {
    const node = new SinglyLinkedListNode(nodeData);

    if (this.head == null) {
      this.head = node;
    } else {
      this.tail.next = node;
    }

    this.tail = node;
  }
};

function printSinglyLinkedList(node, sep, ws) {
  while (node != null) {
    ws.write(String(node.data));

    node = node.next;

    if (node != null) {
      ws.write(sep);
    }
  }
}

// Complete the mergeLists function below.

/*
 * For your reference:
 *
 * SinglyLinkedListNode {
 *     int data;
 *     SinglyLinkedListNode next;
 * }
 *
 */
function mergeLists(head1, head2) {
  let head = null,
    current = null;

  if (head1.data < head2.data) {
    head = head1;
    head1 = head1.next;
  } else {
    head = head2;
    head2 = head2.next;
  }

  current = head;

  while (head1 && head2) {
    if (head1.data < head2.data) {
      current.next = head1;
      head1 = head1.next;
    } else {
      current.next = head2;
      head2 = head2.next;
    }

    current = current.next;
  }

  if (head1) {
    current.next = head1;
  } else if (head2) {
    current.next = head2;
  }

  return head;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const tests = parseInt(readLine(), 10);

  for (let testsItr = 0; testsItr < tests; testsItr++) {
    const llist1Count = parseInt(readLine(), 10);

    let llist1 = new SinglyLinkedList();

    for (let i = 0; i < llist1Count; i++) {
      const llist1Item = parseInt(readLine(), 10);
      llist1.insertNode(llist1Item);
    }

    const llist2Count = parseInt(readLine(), 10);

    let llist2 = new SinglyLinkedList();

    for (let i = 0; i < llist2Count; i++) {
      const llist2Item = parseInt(readLine(), 10);
      llist2.insertNode(llist2Item);
    }

    let llist3 = mergeLists(llist1.head, llist2.head);

    printSinglyLinkedList(llist3, " ", ws);
    ws.write("\n");
  }

  ws.end();
}
```

### [Ice Cream Parlor](https://www.hackerrank.com/challenges/one-month-preparation-kit-icecream-parlor/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'icecreamParlor' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER m
 *  2. INTEGER_ARRAY arr
 */

function icecreamParlor(m, arr) {
  // Write your code here
  let length = arr.length,
    j = 0;

  for (let i = 0; i < length; i++) {
    j = i + 1;
    while (j < length) {
      if (m === arr[i] + arr[j]) {
        return [i + 1, j + 1];
      }

      j++;
    }
  }

  return [];
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const m = parseInt(readLine().trim(), 10);

    const n = parseInt(readLine().trim(), 10);

    const arr = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((arrTemp) => parseInt(arrTemp, 10));

    const result = icecreamParlor(m, arr);

    ws.write(result.join(" ") + "\n");
  }

  ws.end();
}
```

official

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'icecreamParlor' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER m
 *  2. INTEGER_ARRAY arr
 */

function icecreamParlor(m, arr) {
  // Write your code here
  let frequency = {},
    cost_j = 0,
    index_i = 0,
    index_j = 0;

  for (let i = 0; i < arr.length; i++) {
    frequency[arr[i]] = frequency[arr[i]] ? frequency[arr[i]] + 1 : 1;
  }

  for (let i = 0; i < arr.length; i++) {
    frequency[arr[i]]--;
    cost_j = m - arr[i];

    if (frequency[cost_j] > 0) {
      index_i = i;
      break;
    }
  }

  for (let j = index_i + 1; j < arr.length; j++) {
    if (cost_j === arr[j]) {
      index_j = j;
    }
  }

  return [index_i + 1, index_j + 1];
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const m = parseInt(readLine().trim(), 10);

    const n = parseInt(readLine().trim(), 10);

    const arr = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((arrTemp) => parseInt(arrTemp, 10));

    const result = icecreamParlor(m, arr);

    ws.write(result.join(" ") + "\n");
  }

  ws.end();
}
```

### [Queue using Two Stacks](https://www.hackerrank.com/challenges/one-month-preparation-kit-queue-using-two-stacks/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
function processData(input) {
  //Enter your code here
  let query = [],
    queue = [];

  input = input.split("\n");

  for (let i = 1; i <= input[0]; i++) {
    query = input[i].split(" ");

    if (query.length === 2) {
      queue.push(query[1]);
    } else {
      if (query[0] === "2") {
        queue.shift();
      } else {
        console.log(queue[0]);
      }
    }
  }
}

process.stdin.resume();
process.stdin.setEncoding("ascii");
_input = "";
process.stdin.on("data", function (input) {
  _input += input;
});

process.stdin.on("end", function () {
  processData(_input);
});
```

```js
function processData(input) {
  //Enter your code here
  let query = [],
    s1 = [],
    s2 = [];

  input = input.split("\n");

  for (let i = 1; i <= input[0]; i++) {
    query = input[i].split(" ");

    if (query.length === 2) {
      s1.push(query[1]);
    } else {
      if (s2.length === 0) {
        while (s1.length) {
          s2.push(s1.pop());
        }
      }

      if (query[0] === "2") {
        s2.pop();
      } else {
        console.log(s2[s2.length - 1]);
      }
    }
  }
}

process.stdin.resume();
process.stdin.setEncoding("ascii");
_input = "";
process.stdin.on("data", function (input) {
  _input += input;
});

process.stdin.on("end", function () {
  processData(_input);
});
```

### [Balanced Brackets](https://www.hackerrank.com/challenges/one-month-preparation-kit-balanced-brackets/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'isBalanced' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING s as parameter.
 */

function isBalanced(s) {
  // Write your code here

  let brackets = {
    "{": "}",
    "[": "]",
    "(": ")",
  };

  s = s.split("");

  for (let i = 0; i < s.length - 1; i++) {
    if (brackets[s[i]] === s[i + 1]) {
      s.splice(i, 2);

      i = -1;
    } else if (["}", ")", "]"].includes(s[i])) {
      return "NO";
    }
  }

  if (s.length === 0) {
    return "YES";
  } else {
    return "NO";
  }
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const s = readLine();

    const result = isBalanced(s);

    ws.write(result + "\n");
  }

  ws.end();
}
```

official

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'isBalanced' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING s as parameter.
 */

function isBalanced(s) {
  // Write your code here
  let stack = [],
    left = ["{", "(", "["],
    right = {
      "}": "{",
      ")": "(",
      "]": "[",
    };

  for (const c of s) {
    if (left.includes(c)) {
      stack.push(c);
    } else {
      if (stack.length > 0 && stack.at(-1) === right[c]) {
        stack.pop();
      } else {
        return "NO";
      }
    }
  }

  if (stack.length > 0) {
    return "NO";
  }

  return "YES";
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const s = readLine();

    const result = isBalanced(s);

    ws.write(result + "\n");
  }

  ws.end();
}
```

### [Waiter](https://www.hackerrank.com/challenges/one-month-preparation-kit-waiter/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'waiter' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY number
 *  2. INTEGER q
 */

function waiter(number, q) {
  // Write your code here
  function generatePrimes(q) {
    let arr = [],
      i = 2;

    function isPrime(n) {
      let boundary = Math.floor(Math.sqrt(n));

      for (let i = 2; i <= boundary; i++) if (n % i === 0) return false;

      return n >= 2;
    }

    while (arr.length !== q) {
      if (isPrime(i)) arr.push(i);

      i++;
    }

    return arr;
  }

  let primes = generatePrimes(q),
    A = [],
    B = [],
    answer = [];

  for (let i = 0; i < primes.length; i++) {
    for (let j = number.length - 1; j >= 0; j--) {
      if (number[j] % primes[i] === 0) {
        B.push(number.pop());
      } else {
        A.push(number.pop());
      }
    }

    answer.push(...B.reverse());
    number = A;
    A = [];
    B = [];
  }

  answer.push(...number.reverse());

  return answer;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const n = parseInt(firstMultipleInput[0], 10);

  const q = parseInt(firstMultipleInput[1], 10);

  const number = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((numberTemp) => parseInt(numberTemp, 10));

  const result = waiter(number, q);

  ws.write(result.join("\n") + "\n");

  ws.end();
}
```

### [Simple Text Editor](https://www.hackerrank.com/challenges/one-month-preparation-kit-simple-text-editor/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-three)

```js
function processData(input) {
  //Enter your code here
  let S = "",
    undo = [];
  input = input.split("\n");

  for (let i = 1; i < input.length; i++) {
    let [type, op] = input[i].split(" ");

    if (type === "1") {
      undo.push(S);
      S += op;
    } else if (type === "2") {
      undo.push(S);
      S = S.slice(0, S.length - op);
    } else if (type === "3") {
      console.log(S[op - 1]);
    } else if (type === "4") {
      S = undo.pop();
    }
  }
}

process.stdin.resume();
process.stdin.setEncoding("ascii");
_input = "";
process.stdin.on("data", function (input) {
  _input += input;
});

process.stdin.on("end", function () {
  processData(_input);
});
```

### [Equal three Stacks](https://www.hackerrank.com/challenges/one-month-preparation-kit-equal-stacks/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-four)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'equalStacks' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY h1
 *  2. INTEGER_ARRAY h2
 *  3. INTEGER_ARRAY h3
 */

function equalStacks(h1, h2, h3) {
  let sum1 = 0,
    sum2 = 0,
    sum3 = 0,
    possible = [],
    pick = 1,
    bick = 1;

  sum1 += h1.pop();
  sum2 += h2.pop();
  sum3 += h3.pop();

  while (pick) {
    if (sum1 > sum2) {
      if (h2.length) {
        sum2 += h2.pop();
      } else {
        break;
      }
    }

    if (sum1 < sum2) {
      if (h1.length) {
        sum1 += h1.pop();
      } else {
        break;
      }
    }

    while (sum1 === sum2 && bick) {
      while (bick) {
        if (sum1 > sum3) {
          if (h3.length) {
            sum3 += h3.pop();
          } else {
            pick = false;
            bick = false;
            break;
          }
        }

        if (sum1 < sum3) {
          if (h1.length && h2.length) {
            sum1 += h1.pop();
            sum2 += h2.pop();
            break;
          } else {
            pick = false;
            bick = false;
            break;
          }
        }

        if (sum1 === sum3) {
          possible.push(sum1);

          if (h1.length && h2.length && h3.length) {
            sum1 += h1.pop();
            sum2 += h2.pop();
            sum3 += h3.pop();
            break;
          } else {
            pick = false;
            bick = false;
            break;
          }
        }
      }
    }
  }

  return possible.length === 0 ? 0 : possible[possible.length - 1];
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const n1 = parseInt(firstMultipleInput[0], 10);

  const n2 = parseInt(firstMultipleInput[1], 10);

  const n3 = parseInt(firstMultipleInput[2], 10);

  const h1 = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((h1Temp) => parseInt(h1Temp, 10));

  const h2 = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((h2Temp) => parseInt(h2Temp, 10));

  const h3 = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((h3Temp) => parseInt(h3Temp, 10));

  const result = equalStacks(h1, h2, h3);

  ws.write(result + "\n");

  ws.end();
}
```

official

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'equalStacks' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts following parameters:
 *  1. INTEGER_ARRAY h1
 *  2. INTEGER_ARRAY h2
 *  3. INTEGER_ARRAY h3
 */

function equalStacks(h1, h2, h3) {
  let sum1 = h1.reduce((a, b) => a + b, 0),
    sum2 = h2.reduce((a, b) => a + b, 0),
    sum3 = h3.reduce((a, b) => a + b, 0);

  while (!(sum1 === sum2 && sum1 === sum3)) {
    if (sum1 > sum2 || sum1 > sum3) {
      sum1 -= h1.shift();
    }

    if (sum2 > sum1 || sum2 > sum3) {
      sum2 -= h2.shift();
    }

    if (sum3 > sum1 || sum3 > sum2) {
      sum3 -= h3.shift();
    }
  }

  return sum1;
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const firstMultipleInput = readLine().replace(/\s+$/g, "").split(" ");

  const n1 = parseInt(firstMultipleInput[0], 10);

  const n2 = parseInt(firstMultipleInput[1], 10);

  const n3 = parseInt(firstMultipleInput[2], 10);

  const h1 = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((h1Temp) => parseInt(h1Temp, 10));

  const h2 = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((h2Temp) => parseInt(h2Temp, 10));

  const h3 = readLine()
    .replace(/\s+$/g, "")
    .split(" ")
    .map((h3Temp) => parseInt(h3Temp, 10));

  const result = equalStacks(h1, h2, h3);

  ws.write(result + "\n");

  ws.end();
}
```

### [The Maximum Subarray](https://www.hackerrank.com/challenges/one-month-preparation-kit-maxsubarray/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-month-preparation-kit&playlist_slugs%5B%5D=one-month-week-four)

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'maxSubarray' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function maxSubarray(arr) {
  let sum = arr[0],
    subarray = arr[0],
    subsequence = Math.max(arr[0], 0),
    maxvalue = arr[0];

  for (let i = 1; i < arr.length; i++) {
    sum = Math.max(sum + arr[i], arr[i]);
    subarray = Math.max(subarray, sum);
    maxvalue = Math.max(maxvalue, arr[i]);
    subsequence += arr[i] > 0 ? arr[i] : 0;
  }

  return [subarray, subsequence || maxvalue];
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const arr = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((arrTemp) => parseInt(arrTemp, 10));

    const result = maxSubarray(arr);

    ws.write(result.join(" ") + "\n");
  }

  ws.end();
}
```

better

```js
"use strict";

const fs = require("fs");

process.stdin.resume();
process.stdin.setEncoding("utf-8");

let inputString = "";
let currentLine = 0;

process.stdin.on("data", function (inputStdin) {
  inputString += inputStdin;
});

process.stdin.on("end", function () {
  inputString = inputString.split("\n");

  main();
});

function readLine() {
  return inputString[currentLine++];
}

/*
 * Complete the 'maxSubarray' function below.
 *
 * The function is expected to return an INTEGER_ARRAY.
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function maxSubarray(arr) {
  let maxSum = -Infinity,
    sum = 0,
    maxValue = -Infinity,
    cSum = 0;

  arr.forEach((n, i) => {
    if (sum <= 0) {
      sum = n;
    } else {
      sum += n;
    }

    if (sum > maxSum) {
      maxSum = sum;
    }

    if (n > 0) {
      cSum += n;
    }

    if (n > maxValue) {
      maxValue = n;
    }
  });

  return [maxSum, cSum || maxValue];
}

function main() {
  const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

  const t = parseInt(readLine().trim(), 10);

  for (let tItr = 0; tItr < t; tItr++) {
    const n = parseInt(readLine().trim(), 10);

    const arr = readLine()
      .replace(/\s+$/g, "")
      .split(" ")
      .map((arrTemp) => parseInt(arrTemp, 10));

    const result = maxSubarray(arr);

    ws.write(result.join(" ") + "\n");
  }

  ws.end();
}
```

