# bitwise operators

## as name tells thats these operators operats on bits

1). & (bitwise and)
2). | (bitwise or)
3). ^ (bitwise xor)
4). << (bitwise leftshift)
5). >> (bitwise rightshift)

## & (bitwise and)

its a binary operator it convert two number into their binary representation and performs operations.
if two same bit locations in both numbers are 1 then it yield 1 and in any other it yeilds 0.

ex: 2&3
   10 & 11 ===> 10

## | (bitwise or)

it's also a binary operator if any of the one bit is 1 it yields 1 other wise 0

ex: 2 | 4
    10 | 100 ===> 110

## ^ (bitwise xor)
it's also a binary operator if both bits are 1 or 0 then it yields 0 otherwise it yields 1

ex: 2 ^ 4
    
    10 ^ 100 ==> 110


## << and >> (shift operators)

it will shift one left or right based on which shift operator used.
it is simply left shift is multiply with 2 and right shift is dividing by 2.

ex: 2<<1
   10 << 1 ==> 100 ==> 4
    
   4>>1
   100 >> 1 ==> 10 ==> 2


## ~ (bitwise not)

it's a uniary operators means it takes single argument.
it simply flips all the bits in it.

ex: ~4
	two's compliment ==> inverting bits and adding 1	
	100 ==> 011 ==> 100
    ~0000....100 ==> 111...011 ==> -5 
	formula ~n = -(n+1)



