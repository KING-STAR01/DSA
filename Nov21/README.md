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

	let num=11011000 after inverting 00100111 this has no bit same in ith place i.e., and is zero if we add one to inverting number it will make first unset bit to set.  
	this unset bit which is set now is our lowest set bit.
	that's it  
	ex: 11011000 inverting 00100111 adding one 00101111  
	anding will give 00001000  

## getting most significant bit  

we nee to find the left most set bit

log2(num) will be give right most set bit position.

ro can use a for loop to check most significant bit position.


## computing xor from 1 to n

| number | binary-repr | xor from 1 to n |
|:---|:---:| ---:|
|1|00001|00001|   ---> `xor is one`  
|2|00010|00011|   ----> `xor is num +1 `  
|3|00011|00000|   ---> *xor becomes zero*  
|4|00100|00100|    ----> xor same as num  
|5|00101|00001|  ---> `xor is one`  
|6|00110|00111|    ----> `xor is num +1 `  
|7|00111|00000| ---> *xor becomes zero*  
|8|01000|01000|   ---> xor same as num  
|9|01001|00001|  ---> `xor becomes one`  
|10|01010|01011|   ---> `xor is num+1`  
|11|01011|00000|  ---> *xor becomes zero*    
|12|01100|01100|  ----> xor same as num   

	we can see that when num divided by if    
	rem is 0 then xor from 1 to num is n.   
	rem is 1 then xor from 1 to num is 1.   
	rem is 2 then xor from 1 to num is n+1.  
	rem is 3 then xor from 1 to num is 0.  



## checking if a number is a power of 2  

every two power has only one set bit in it.  
\_\_builtin\_popcount(num) will give us no of sets bits in num  

if we subtract one from number that is power of 2 then all bits before set bit becomes 1  

anding with original number will give us 0 this means that number is a power of 2.  


##  some useful gcc bit functions.   

builtin\_clz(num)  returns no of leading zeros  
builtin\_ctz(num) returns no of trailing zeros   
\_\_builtin\_popcount(num( returns no of set bits in num    

## clearing all bits from LSB to ith bit

to clear all bits form LSB to ith bit we should and with mask such that mask should have 0 form LSB to ith bit.
preparing mask
	mask = (1<<(i+1)-1);
	mask=~mask
	x&=mask
explanation:
1<<(i+1) creates a set bit in i+1 th location if we subtact one from it then it enables i bits after i+1 location and turnoff i+1th bit.  
simple inverting bits means set ith bit to zeroth bit 0 and remaining 1.

this is our required mask.


## clearing all bits form MST to ith bit.  
means need to clear first i bits from left. so we need to prepare a mask such that left to ith bit as 0 and remaining one's.
	mask = (1<<i)-1;  ---> this is having ones from i-1th bit to zeroth bit(i to right zero bit)
	num&=mask;   ---> anding with original number gives required result.
	






