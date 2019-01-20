# Простые Множители: Решето Эратосфена

## Введение
В этом задании мы проведем рефакторинг рабочего решения *[algorithm-drill-prime-factors-challenge][]*,  которые мы ранее выполнили. Рабочий код предоставлен. Мы собираемся изменить код так, чтобы использовать определенный алгоритм для нахождения возможного разложения числа на простые множители.

### Решето Эратосфена
Мы собираемся изменить предоставленный код, чтобы использовать один из самых старых алгоритмов, [Решето Эратосфена][]

В коде, с которым мы будем работать, чтобы найти простой множитель данного числа, мы пробегаем через все числа от 1 до данного, пока не найдем простой множитель. Проверяем 1, потом 2, потом 3, 4, 5, 6 и так далее.

При таком подходе мы совершаем много ненужной работы. Например, проверим, делится ли данное число на 2. А потом мы проверим, делится ли оно на 4, 6, 8 и так далее со всеми четными числами. Но мы знаем, что если число делится на 4, 6, 8 и вообще любое четное число, то оно точно делится на 2. Другими словами, если число не делится на 2, то оно не делится ни на одно четное число.

И далее проведем тоже самое с 3 - то есть проверим 6, 9, 12 и так далее. Аналогично для 5 - 10, 15, 20, и т.д.

![Sieve of Eratosthenes](http://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)

*рис 1*.  Использование Решета Эратосфена для того, чтобы найти простые числа менее 121.

Решето Эратосфена помогает нам, создавая набор простых чисел, по которому мы можем проходить, чтобы избегать ненужной работы. Википедия предоставляет [алгоритм][РЭ алгоритм] того, как создать такой набор, который представлен в следующих шагах. Рис1 описывает этот процесс визуально.

1. Создайте список последовательных целых чисел от 2 до *n*:  2, 3, 4, ... * n *.
2. Возьмите первое число в списке (например, 2) и удалите все, кратные ему (4, 6, 8, 10 и т.д.)
3. Возьмите следующее оставшееся число из списка (например, 3) и удалите все, кратные ему.
4. Повторяйте шаг 3 до тех пор, пока все числа в списке не будут проверены.


## Releases
### Release 0: Implement the Sieve of Eratosthenes
```ruby
sieve_of_eratosthenes(10)
# => [2, 3, 5, 7]
```
*Figure 2*.  Example usage of the `sieve_of_eratosthenes` method.

After we understand how the Sieve of Eratosthenes works, let's write a method `sieve_of_eratosthenes` which takes as its input an integer and returns all prime numbers less than that number (see Figure 2).  As always, we'll want to test that our method is working as we expect.  

Remember that our tests should describe the behavior of our method: given a specific number as input, the method returns a specific value.  The tests won't reflect our implementation, but the challenge here is not just to return prime numbers less than a given number.  The challenge is to do so using the Sieve of Eratosthenes algorithm.

*Note:* In trying to understand how the sieve works, use pencil and paper, a whiteboard, whatever we need to help ourselves understand.


### Release 1: Refactor How We Find Prime Factors
We have a working codebase that will find the prime factors of a given number.  We want to refactor the code base to make use of our `sieve_of_eratosthenes` method.

We're free to change any of the provided code, but the behavior of the `prime_factors` method should not change.  Tests have been provided for this method.  They pass given the provided codebase, and they should continue to pass after our refactoring.


## Conclusion
In this challenge we were given a specific algorithm to implement in code.  We were also given a working codebase that we needed to understand before we could refactor.  Did we struggle with either or both of these?  Was it hard to understand the algorithm?  Was it hard to translate it into code?  Was it hard to understand how the methods in the codebase worked together?  If we struggled with any aspects of this challenge, do we understand where and why we faced these struggles?  And, how can we improve our abilities now that we've identified these areas?


[algorithm-drill-prime-factors-challenge]: ../../../algorithm-drill-prime-factors-challenge
[Решето Эратосфена]: https://ru.wikipedia.org/wiki/%D0%A0%D0%B5%D1%88%D0%B5%D1%82%D0%BE_%D0%AD%D1%80%D0%B0%D1%82%D0%BE%D1%81%D1%84%D0%B5%D0%BD%D0%B0
[РЭ алгоритм]: https://ru.wikipedia.org/wiki/%D0%A0%D0%B5%D1%88%D0%B5%D1%82%D0%BE_%D0%AD%D1%80%D0%B0%D1%82%D0%BE%D1%81%D1%84%D0%B5%D0%BD%D0%B0#%D0%90%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC
