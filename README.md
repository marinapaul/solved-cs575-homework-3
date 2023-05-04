Download Link: https://assignmentchef.com/product/solved-cs575-homework-3
<br>
<h1>Written Part</h1>

<ol>

 <li>Sort the array of numbers 10, 7, 3, 8, 1, 9, 0 in ascending order using the <strong>insertion sort algorithm</strong>. Show the state of the array after each iteration of the algorithm.</li>

 <li>Use diagrams similar to the one shown in the slides and in your textbook to show the various stages of the <strong>merge sort algorithm</strong> for the following array of numbers: 13, 57, 39, 85, 70, 22, 64, 48</li>

 <li>Use Strassen’s method to compute the product of the following two matrices</li>

</ol>

A = 2, 3                 B =      5, 6

4, 5                             1, 3

<ol start="4">

 <li>Illustrate all the steps of the partition function in quicksort on the array A =[13, 9, 5, 7, 3, 1, 10, 6, 11, 2]<strong> </strong></li>

 <li>Given a sorted list of distinct integers A[1], A[2],…,A[n], you want to find out whether there is an index i for which A[i] = i. Give an algorithm that runs in time O(log n).</li>

</ol>




For example, A = [-1, -2, 3, 5, 6, 7] does have such an index, i.e., A[3] = 3. But A =[0, 1, 2, 5, 6, 7] doesn’t have such an index.




You need to write the pseudocode, prove correctness and analyze the running time.

<strong> </strong>

<ol start="6">

 <li>You are given a loaded die. The probability of obtaining a particular face of the die is inversely proportional to the number on that face. What is the probability that you will get a number greater than 3 if you roll the die?</li>

</ol>




<strong>Programming Part  What to hand in? </strong>

<ol>

 <li>Submit code with in-line documentation. <strong>You can write in the assignment in C, C++ or Java. </strong></li>

 <li>Run your code on your local machine as well as on ‘remote’. A readme file outlining how your code should be run.</li>

</ol>

<strong> </strong>

<h1>Problem 1.</h1>

In the first part of the problem you will implement the simple selection sort algorithm. You can use an array to store the elements. <strong> </strong>

<ol>

 <li>As you are aware the selection sort algorithm runs in O(n<sup>2</sup>) time. Implement your algorithm in a separate function called SelectionSort().</li>

</ol>

<strong> </strong>

<h1>Sample Test Cases</h1>

<strong>Input: </strong>4, 6, 8, 15, 20, 22, 10, 3, 9, 2

<strong>Output:</strong> 2, 3, 4, 6, 8, 9, 10, 15, 20, 22




<ol>

 <li>In the second part of the assignment you will modify the selection sort algorithm to obtain the first k smallest elements of the array in sorted order (the value of k will be entered by the user). Your algorithm must run in O(nk) time.</li>

</ol>

<h1>Sample Test Case 1</h1>

<strong>Input: </strong>4, 6, 8, 15, 20, 22, 10, 3, 9, 2 k = 4

<strong>Output:</strong> 2, 3, 4, 6




<h1>Sample Test Case 2</h1>

<strong>Input: </strong>4, 6, 8, 15, 20, 22, 10, 3, 9, 2

k = 6

<strong>Output:</strong> 2, 3, 4, 6, 8, 9




<ol>

 <li>Use the implementation in part 2 to determine the median value of the input array. You can assume that the values in the array are distinct. If the array is of even size, then the median is the average of the two middle values is the array.</li>

</ol>

<h1>Problem 2.</h1>

In this problem you will implement a sorting algorithm, which has not been covered in class. We will call this sorting algorithm CoolSort(). We will take advantage of insertion sort for designing this sorting algorithm. The description of the sorting algorithm is as follows.

We will first choose a decreasing sequence of numbers that ends at 1. For example, let us consider the sequence of step sizes H = 5, 3, 1. You can choose any decreasing sequence. Note that the first element of the sequence is less than the number of elements in the array.

For each H, sort sub-arrays that start at arbitrary element and include every H<sup>th</sup> element using insertion sort. For example, consider the following array a = [ 62 83 18 53 07 17 95 86 47 69 25 28].

An example run of CoolSort with gaps 5, 3 and 1 is shown below.

a1  a2  a3  a4 a5  a6 a7  a8  a9 a10 a11 a12

Input    62 83 18 53 07 17 95 86 47 69 25 28

H = 5   17 28 18 47 07 25 83 86 53 69 62 95

H = 3   17 07 18 47 28 25 69 62 53 83 86 95

H = 1   07 17 18 25 28 47 53 62 69 83 86 95

The first pass, 5-sorting, performs insertion sort on separate subarrays (<em>a</em><sub>1</sub>, <em>a</em><sub>6</sub>, <em>a</em><sub>11</sub>), (<em>a</em><sub>2</sub>, <em>a</em><sub>7</sub>, <em>a</em><sub>12</sub>), (<em>a</em><sub>3</sub>, <em>a</em><sub>8</sub>), (<em>a</em><sub>4</sub>, <em>a</em><sub>9</sub>), (<em>a</em><sub>5</sub>, <em>a</em><sub>10</sub>). For instance, it changes the subarray (<em>a</em><sub>1</sub>, <em>a</em><sub>6</sub>, <em>a</em><sub>11</sub>) from (62, 17, 25) to (17, 25, 62). The next pass, 3-sorting, performs insertion sort on the subarrays (<em>a</em><sub>1</sub>, <em>a</em><sub>4</sub>, <em>a</em><sub>7</sub>, <em>a</em><sub>10</sub>), (<em>a</em><sub>2</sub>, <em>a</em><sub>5</sub>, <em>a</em><sub>8</sub>, <em>a</em><sub>11</sub>), (<em>a</em><sub>3</sub>, <em>a</em><sub>6</sub>, <em>a</em><sub>9</sub>, <em>a</em><sub>12</sub>). The last pass, 1-sorting, is an ordinary insertion sort of the entire array (<em>a</em><sub>1</sub>,…, <em>a</em><sub>12</sub>).

As the example illustrates, the subarrays that CoolSort operates on are initially short; later they are longer but almost ordered.

<strong>Though unintuitive, it can be shown that the above algorithm has a runtime of O(N<sup>3/2</sup>) in comparison to selection sort which has a runtime of O(N<sup>2</sup>). That is why this algorithm is cool! </strong>

<strong> </strong>

<h1>Sample Test Case 1</h1>

<strong>Input</strong> = [2, 5, 6, 4, 10, 9, 8, 1, 10, 5] and <strong>H</strong> = [5, 3,1]

<strong>Output</strong> = [1, 2, 4, 5, 5, 6, 8, 9, 10, 10]




<h1>Sample Test Case 2</h1>

<strong>Input</strong> = [2, 5, 9, 4, 10, 7, 8, 1, 11, 5] and <strong>H</strong> = [5, 2,1]

<strong>Output</strong> = [1, 2, 4, 5, 5, 7, 8, 9, 10, 11]

<strong> </strong>

<h1>Problem 3.</h1>




Implement the algorithm you devised in Question 5 and show that it works


