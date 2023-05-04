Download Link: https://assignmentchef.com/product/solved-csci1913-lab-5
<br>
A <em>prime number</em> is a positive integer with exactly two distinct divisors: 1 and itself. The <em>Sieve of Eratosthenes</em> (pronounced <em>Era-</em><em>TOSSthe-knees</em>) is an algorithm for finding prime numbers. It’s named after a Greek mathematician of the Third Century BCE. In this lab assignment, you will implement the Sieve as a Java class, and use an instance of that class to print a list of prime numbers.

<ol>

 <li></li>

</ol>

The Sieve algorithm finds prime numbers between 2 and some positive integer <em>n.</em> Unlike other prime number algorithms, it doesn’t need square roots, multiplication, or division. It works in the following way.

<ol>

 <li>Make an empty set.</li>

 <li>Add integers 2, 3, …, <em>n</em> to the set.</li>

 <li>Visit each integer in the set. After you visit an integer, remove all other integers from the set that are multiples of that integer. For example, after you visit the integer 2, you remove the integers 4, 6, 8, etc.</li>

 <li>The integers left in the set are primes.</li>

</ol>

For example, suppose you want to find the prime numbers between 2 and 25. You start with the following set of numbers.

<strong>2</strong>  <strong>3</strong>  <strong>4</strong>  <strong>5</strong>  <strong>6</strong>  <strong>7</strong>  <strong>8</strong>  <strong>9</strong>  <strong>10</strong>  <strong>11</strong>  <strong>12</strong>  <strong>13</strong>  <strong>14</strong>  <strong>15</strong>  <strong>16</strong>  <strong>17</strong>  <strong>18</strong>  <strong>19</strong>  <strong>20</strong>  <strong>21</strong>  <strong>22</strong>  <strong>23</strong>  <strong>24</strong>  <strong>25</strong>

When you visit the integer 2 (it’s underlined), you remove all other integers that are multiples of 2 (they turn gray), so the set looks like this.

<strong><u>2</u></strong>  <strong>3</strong>  <strong>4</strong>  <strong>5</strong>  <strong>6</strong>  <strong>7</strong>  <strong>8</strong>  <strong>9</strong>  <strong>10</strong>  <strong>11</strong>  <strong>12</strong>  <strong>13</strong>  <strong>14</strong>  <strong>15</strong>  <strong>16</strong>  <strong>17</strong>  <strong>18</strong>  <strong>19</strong>  <strong>20</strong>  <strong>21</strong>  <strong>22</strong>  <strong>23</strong>  <strong>24</strong>  <strong>25</strong>

Then you visit 3, removing integers that are multiples of 3.

<strong>2</strong>  <strong><u>3</u></strong>  <strong>4</strong>  <strong>5</strong>  <strong>6</strong>  <strong>7</strong>  <strong>8</strong>  <strong>9</strong>  <strong>10</strong>  <strong>11</strong>  <strong>12</strong>  <strong>13</strong>  <strong>14</strong>  <strong>15</strong>  <strong>16</strong>  <strong>17</strong>  <strong>18</strong>  <strong>19</strong>  <strong>20</strong>  <strong>21</strong>  <strong>22</strong>  <strong>23</strong>  <strong>24</strong>  <strong>25</strong>

And you visit 5, removing integers that are multiples of 5.

<strong>2</strong>  <strong>3</strong>  <strong>4</strong>  <strong><u>5</u></strong>  <strong>6</strong>  <strong>7</strong>  <strong>8</strong>  <strong>9</strong>  <strong>10</strong>  <strong>11</strong>  <strong>12</strong>  <strong>13</strong>  <strong>14</strong>  <strong>15</strong>  <strong>16</strong>  <strong>17</strong>  <strong>18</strong>  <strong>19</strong>  <strong>20</strong>  <strong>21</strong>  <strong>22</strong>  <strong>23</strong>  <strong>24</strong>  <strong>25</strong>

The Sieve algorithm continues in this way, visiting multiples of 7, 11, 13, etc., all the way up to 25. However, there are no more primes in this set after you visit 5, so you can stop the example here. The numbers that remain in the set are primes.

You can represent a set of integers that can range from 0 to <em>n</em>−1 as an array of <em>n</em> boolean values. Each boolean value is either true or false. An integer <em>k</em> is in the set if the element at index <em>k</em> is true. It is not in the set if the element at index <em>k</em> is false.

<ol start="2">

 <li></li>

</ol>

You must write a class called Sieve that has the following methods, with the same names that are shown here.

Sieve(int max)

This is the constructor. It must make an array called numbers. The array’s length must be max and its elements must be booleans. If max is less than 2, then throw an IllegalArgumentException. Set the elements at indexes 0 and 1 of numbers to false. Set all the other elements of numbers to true.

The array numbers represents a set of integers that will be tested for primality. Initially, 0 and 1 are not in the set, because you know they cannot be prime. However, all the other numbers, from 2 to max – 1, are still in the set, because you do not know yet if they are prime.

findPrimes()

Perform the Sieve algorithm described in the theory section. You must visit each boolean element of numbers. If you visit an element that is false, then you must do nothing. However, suppose that you visit an element that is true, at index i. Then you must visit all the other elements of numbers whose indexes are multiples of i, setting those elements to false.

toString()

Start with an empty string. Visit each boolean element in numbers. If the element is true, then add its index to the string, followed by a blank. If the element is false, then do nothing. The indexes in the string are the prime numbers found by the Sieve algorithm. Return the string.

As a matter of style, never write <em>B</em> == true or <em>B</em> == false where <em>B</em> is a boolean expression. The expression <em>B</em> == true always has the same value as <em>B</em>. The expression <em>B</em> == false can be written better as !<em>B</em>.

<ol start="3">

 <li><strong> Tests.</strong></li>

</ol>

The file <a href="https://html2pdf.com/files/9et8fluvkfcg4fh3/o_1e0djt4qt19s31u6bf461k5o1q28c/TossTheKnees.java"><strong>TossTheKnees.java</strong></a> contains Java source code for a driver class. The class contains a main method, which in turn contains code that tests your class Sieve. Put the Java code for your class Sieve in this file, and run it to obtain the results of the tests in main. If a test succeeds, then you will receive all the points for that test. If a test fails, then you will recieve no points for it. Your score for this lab will be the sum of the points you get on the tests.