# bitwise operators

### as name tells thats these operators operats on bits
**_
1). & (bitwise and)  
2). | (bitwise or)  
3). ^ (bitwise xor)  
4). << (bitwise leftshift)  
5). >> (bitwise rightshift)  
_**

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


## \<\< and \>\> (shift operators)  

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


# setting ith bit in a number  

to set a ith bit in a number we should make a mask that has 1 at ith bit and remaining all 0 this can be done as 1\<\<i then oring with original number will set ith bit in numer.  
ex: num=123  
let ith bit = 3  
mask=1<<3  
num|=mask  

## unsetting ith bit in a number   

to unset a bit in ith position in a number we make a mask it has 0 in ith and all reaming positions has 1.  

ex: num = 123  
let ith bit =3  
a=(1<<3) it has one in ith and all zeros in remaing positions. we can simpley invert it to make our mask  
mask = (~(1<<3))  
num&=mask  


## toggling the ith bit  

to toggle a bit using in number we can use ^(xor) operator with 1 if it has 1 in ith then it will become 0 if it has 0 then it has 1.  

ex: num=123
let ith bit = 3
mask = 1<<3  
num^=mask  

## checking ith bit is set or not   

to check we can simply and with suitable mask(have ith bit set)  

ex: num=123  
let ith bit =3  
mask = 1<<3  
num&(mask)?1:0  

## inverting every bit in number (also called one's complement)   

we can simply use not operator to toggle every bit  

ex: num=123  
~num  

## two's complement of a number  

we can simply find one's complement and add one to it.  
~num+1 is two's complement  
-num simply negative of num is two's complement  


## stripping off the lowest set bit  
meaning we simple need to remove the right most set bit  
let a num be 1100 right most set bit location is 2 from left to right.  
to turn off it.  

if we remove 1 from num then we invert all bits till right most set bit including right most
so 1100 - 1 will be 1011  
if we and with original number then its done we unset the rightmost set bit

num & (num-1)   

## getting the lowest set bit in a num  

we simple need to find right most set bit.  
to do this we need to create a suitable mask such that mask should a 1 at lowest set bit and remaining places are zero.   
this can be done easily.  
if we invert a number it means we flip all bits in a number  

< let num=11011000 after inverting 00100111 this has no bit same in ith place i.e., and is zero if we add one to inverting number it will make first unset bit to set.  
this unset bit which is set now is our lowest set bit.
that's it  
< ex: 11011000 inverting 00100111 adding one 00101111  
< anding will give 00001000  






