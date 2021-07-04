## Simple Multipliers. Eratosthenes' sieve

In this assignment, you need to refactor a working solution *[search for simple multipliers][]* that you previously completed. The working code is provided in the current repository. You need to modify that code so that you can use a specific algorithm to find a possible prime factorization of a number.

### Eratosthenes' Sieve

You'll need to use one of the oldest algorithms, [Eratosthenes' Sieve][https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes].

In the code you're going to search for the prime multiplier of a given number, running through all the numbers from 1 to the given number until you find the prime multiplier. You check first number 1, then number 2, then number 3, 4, 5, 6, and so on.

This approach does a lot of unnecessary work. For example, we check if a given number is divisible by 2, and then check if it is divisible by 4, 6, 8, and so on with all even numbers. But we know that if a number is divisible by 4, 6, 8, or any even number, then it is exactly divisible by 2. In other words, if a number is not divisible by 2, then it is not divisible by any even number.

And then you can perform the same operation with number 3 - that is, check the division by 6, 9, 12, and so on. Similarly for 5 - 10, 15, 20, etc.

![Sieve of Eratosthenes](http://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)

*Use the Eratosthenes' Sieve to find prime numbers less than 121

Eratosthenes' Sieve helps us by creating a set of prime numbers that we can walk through to avoid unnecessary work. Wikipedia provides [algorithm][RE algorithm] of how to create such a set, which is presented in the following steps. The figure above describes this process visually.

1. Create a list of consecutive integers from 2 to *n*:  2, 3, 4, ... *n*
2. Take the first number in the list (for example, 2) and remove all multiples of it (4, 6, 8, 10, etc.)
3. Take the next remaining number in the list (e.g. 3) and remove all multiples of it
4. Repeat step 3 until all the numbers in the list are checked.


### Release 0. The implementation of Eratosthenes' Sieve

```javascript.
sieveOfEratosthenes(10)
# => [2, 3, 5, 7]
```
*Example of using the `sieveOfEratosthenes(n)` method.

After you understand how the Eratosthenes Sieve works, let's implement the `sieveOfEratosthenes` method, which takes a number as input and returns all prime numbers that are less than a given number. As always, you need to test to make sure that your method works as it is supposed to.

Remember that your tests should describe the behaviour of the function: taking a certain number as input, the method returns a certain value. The tests don't reflect your implementation, but the goal here is not just to return prime numbers that are smaller than a given number. You need to do it using Eratosthenes' Sieve algorithm.

*Note:* To understand how the Sieve works, use a pen and paper, a blackboard, or anything else that will help you understand.

[search for simple multipliers]: .../.../algorithm-drill-prime-factors-challenge
[Решето Эратосфена]: https://ru.wikipedia.org/wiki/%D0%A0%D0%B5%D1%88%D0%B5%D1%82%D0%BE_%D0%AD%D1%80%D0%B0%D1%82%D0%BE%D1%81%D1%84%D0%B5%D0%BD%D0%B0
[РЭ алгоритм]: https://ru.wikipedia.org/wiki/%D0%A0%D0%B5%D1%88%D0%B5%D1%82%D0%BE_%D0%AD%D1%80%D0%B0%D1%82%D0%BE%D1%81%D1%84%D0%B5%D0%BD%D0%B0#%D0%90%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC
