# poly_hello_world
An obfuscated Hello World in C. 

## Building

Compile poly_hello_world.c with your beloved C compiler :3.

```
gcc -o poly poly_hello_word.c
poly
Hello World!
```

## Why

Its fun and cool :3, also for nostalgia reasons (archiving old highschool projects)

## How

I had the brilliant idea during a Programming course in Highschool. I fit a 12th degree polynomial to the set of ascii values for "Hello World!". The x values of the dataset are the indicies in the string, and the y values are the ascii values of the character at the x value.

The first few points in the dataset look like: (0, 72), (1, 101), (2, 108), (3, 108), ....

To my memory I used Python and SciPy to fit the polynomial and got the resulting polynomial in all its glory:

$f(x) = $
$-4.1657663778969315E-05x^{12} - 4.1657663778969315E-05x^{11} - 0.0395582867074462x^{10} + 0.27468768736782573x^9 + 1.7034169200272369x^8$
$- 49.73502612517271x^7 + 448.666923422801x^6 - 2241.1199584494157x^5 + 6693.445775491866x^4$
$- 11703.19460402312x^3 + 10817.679691395751x^2 - 3938.6833935636064x + 72.00000000000003$

beautiful

$f(i)$ gives the ith character (in ASCII) of "Hello World!", where $0 \le i \lt 12$

So what does "Hello World!" look like as a graph?????

![]()

## In C

In C the polynomial was implemented as:

```C
#include <stdio.h>
#include <math.h>
int main(void){for (int x = 0; x <= 11; ++x){
    putchar((72.00000000000003 * pow(x,0))+
    (-3938.6833935636064 * pow(x,1))+
    (10817.679691395751 * pow(x,2))+
    (-11703.194604023123 * pow(x,3))+
    (6693.445775491866 * pow(x,4))+
    (-2241.1199584494157 * pow(x,5))+
    (448.6669234228012 * pow(x,6))+
    (-49.73502612517271 * pow(x,7))+
    (1.7034169200272369 * pow(x,8))+
    (0.27468768736782573 * pow(x,9))+
    (-0.0395582867074462 * pow(x,10))+
    (0.0020873286887065 * pow(x,11))+
    (-4.1657663778969315e-05 * pow(x,12)));
    }
}
```



