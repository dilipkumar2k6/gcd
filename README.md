# Greatest Common Divisor 
- The greatest common divisor (GCD), also called the greatest common factor, of two numbers is the largest number that divides them both. 
- For instance, the greatest common factor of 20 and 15 is 5, since 5 divides both 20 and 15 and no larger number has this property. 
- The concept is easily extended to sets of more than two numbers: the GCD of a set of numbers is the largest number dividing each of them.
- The GCD is used for a variety of applications in number theory, particularly in modular arithmetic and thus encryption algorithms such as RSA. 
- It is also used for simpler applications, such as simplifying fractions. 
- This makes the GCD a rather fundamental concept to number theory, and as such a number of algorithms have been discovered to efficiently compute it.
- The GCD is traditionally notated as gcd(a,b), or when the context is clear, simply (a,b).

# Computing the greatest common divisor
- The GCD of several numbers may be computed by simply listing the factors of each number and determining the largest common one. 
- While in practice this is terribly inefficient, for particularly small cases it is doable by hand. 
- The process may be split up using the method of factor pairs: once one determines a factor a of a number n, the quotient n/a is necessarily a factor as well. For instance, since 2 is a factor of 24, 22/2 =12 is a factor as well.
- While the prime factorization method is often the most practical to do by hand, occasionally determining the prime factorization is very difficult, in which case an alternate approach becomes necessary. Generally, in these cases, algorithms are used as in the next section.

# Euclidean algorithm and more
- Because large numbers are difficult to work with by hand, there are a number of algorithms used to simplify the problem down to a manageable level. Since the GCD has the property that
gcd(a,b,c)=gcd(gcd(a,b),c)

- The Euclidean algorithm is based on the following key observation: if d divides a and d divides b, then d also divides a - b
-  This means that the GCD of a and b is the same as the GCD of a - b and b, which is progress since this makes the numbers smaller.
- As a result, we can repeat this process to form an algorithm:
1. If a = b, stop -- the GCD of a and a is, of course, a. Otherwise, go to step 2.
2. If a > b, replace a with a - b, and go back to step 1.
3. If b > a, replace b with b - a, and go back to step 1.
```
public static int gcd(int a, int b) { 
    if (a == b) 
        return b; 
    if (a > b) {
        return gcd(a - b, b); 
    }  
    return return gcd(a, b - a); 
} 
```

# Extended Euclidean Algorithm for GCD
- Now instead of subtraction, if we divide smaller number, the algorithm stops when we find remainder 0.
```
public static int gcd(int a, int b) { 
    if (a == 0) {
        return b; 
    }
        
    return gcd(b%a, a); 
} 
```
# Problems
https://www.lintcode.com/problem/greatest-common-divisor/description
https://leetcode.com/problems/greatest-common-divisor-of-strings/
https://leetcode.com/problems/x-of-a-kind-in-a-deck-of-cards/

# Reference 
https://brilliant.org/wiki/greatest-common-divisor/#
