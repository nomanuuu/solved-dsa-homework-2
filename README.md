Download Link: https://assignmentchef.com/product/solved-dsa-homework-2
<br>
<h1>Problem 1 – Sort</h1>

Suppose there are <em>n </em>pancakes <em>P</em><sub>1</sub><em>,…,P<sub>n </sub></em>with unknown tastiness <em>t</em><sub>1</sub><em>,…,t<sub>n </sub></em>respectively. Arvin, as a pancake lover, wants to “sort” the pancakes according to their tastiness. However, he is prohibited to try the pancakes on his own. Luckily, he can pray to the Pancake-God for help. In each round of praying, Arvin specifies three different pancakes, and the Pancake-God indicates the pancake with the <strong>median </strong>tastiness. With the help of the Pancake-God, Arvin wants to find the order of the <em>n </em>pancakes. Notice that by knowing only median-of-three’s, it is impossible to distinguish the order of any list from its reverse, since the median query results in the same answer for any three pancakes in both cases. Therefore, we call a list of pancakes to be “sorted” as long as their tastiness is totally increasing or totally decreasing.

Formally, suppose there is a query model that involves Pancake-God-Oracle(P<em>,i,j,k</em>), a black-box function that compares the pancakes <em>P<sub>i</sub>,P<sub>j</sub>,P<sub>k </sub></em>and returns the pancake with the median tastiness. In the following subproblems, we start by checking the query complexity of the algorithm, i.e., the number of Pancake-God-Oracle queries required for the algorithm. That is, we assume that all the implementation details, such as control, data movement, etc. does <em>not </em>take any efforts. We just focus on whether we have the necessary information from querying the Pancake-God to complete the task.

<ol>

 <li>(10 pts) Given <em>n </em>pancakes, design an algorithm with <em>O</em>(<em>n</em>) query complexity that returns two “boundary” pancakes, one of them being of the maximum tastiness, and the other of the minimum tastiness.</li>

 <li>(20 pts) Using the <em>O</em>(<em>n</em>) query complexity algorithm above to get two “boundary” pancakes on hand (if you cannot solve the previous problem, you can also assume to have the algorithm above as a black box), design an divide-and-conquer algorithm to “sort” the <em>n </em>pancakes with query complexity <em>O</em>(<em>n</em>log<em>n</em>). <em>(Hint: There are more than one approaches. Concepts of Merge Sort or Quick Sort may help.)</em></li>

 <li>(10 pts) Arvin wants to avoid unnecessary calls to Pancake-God-Oracle, otherwise the Pancake-God might get angry. Suppose there is a list <em>L </em>of <em>m </em>pancakes that is already “sorted.” Given another pancake, design an algorithm with <em>O</em>(log<em>n</em>) query complexity to insert this pancake into <em>L </em>such that the new list of pancakes is still “sorted.”</li>

 <li>(5 pts) Using the <em>O</em>(log<em>n</em>) query complexity algorithm above to “insert” the pancake to the right place (if you cannot solve the previous problem, you can also assume to have the algorithm above as a black box), design an algorithm to sort <em>n </em>pancakes with query complexity <em>O</em>(<em>n</em>log<em>n</em>) without first locating the boundary pancakes. <em>(Hint: Concepts of Insertion Sort may help.)</em></li>

 <li>(Bonus 20 pts) Argue that it is impossible to find an algorithm with <em>o</em>(<em>n</em>log<em>n</em>) query complexity to “sort” all pancakes. Therefore, the result above is asymptotically optimal! <em>(Hint: Please check the textbook for the formal definition of the little-oh notation, if needed. You will get all bonus credits only if your proof is fully rigorous, while the TAs can choose to give partial credits.)</em></li>

</ol>

After a few rounds of answering Arvin’s calls, the Pancake-God is tired. The Pancake-God then asks Arvin to go find the Pancake-Elf, who would directly not just “sort” all pancakes, but also order them from the smallest to the largest tastiness and return the sorted result to

Arvin. The sorting algorithm that the Pancake-Elf uses is as follows.

<strong>Algorithm 1: </strong>The fancy algorithm of the Pancake-Elf

<strong>Function </strong>Elf-Sort(pancake array P, <em>l</em>, <em>r</em>): // with <em>r </em>≥ <em>l</em>

<ol start="6">

 <li>(15 pts) Prove that the Elf-Sort algorithm can correctly sort a pancake array P in ascending order by calling Elf-Sort(P<em>,</em>1<em>,</em>n). <em>(Hint: You may need to prove by induction on </em><em>n.)</em></li>

 <li>(5 pts) Let <em>T</em>(<em>n</em>) denote the worst-case running time of Elf-Sort(P<em>,l,r</em>), where <em>n </em>= <em>r </em>− <em>l </em>+1 is a positive number denoting the problem size. Explain the recurrence relation of <em>T</em>(<em>n</em>), which should be expressed as a form similar to <em>T</em>(<em>n</em>) = <em>aT</em>(<em>bn</em>)+Θ(<em>f</em>(<em>n</em>)).</li>

 <li>(15 pts) Prove by definition that <em>T</em>(<em>n</em>) = <em>O</em>(<em>n</em><sup>3</sup>). That is, you need to prove that there exists positive constants <em>n</em><sub>0</sub><em>,c </em>such that <em>T</em>(<em>n</em>) ≤ <em>cn</em><sup>3 </sup>for all <em>n </em>≥ <em>n</em><sub>0</sub>. (In fact, <em>T</em>(<em>n</em>) = Θ(<em>n</em><sup>log</sup><sup>1<em>.</em>5</sup><sup>3</sup>), which implies its worst-case running time complexity is far worse than the usual sorting algorithms that we have discussed!)</li>

</ol>

<h1>Problem 2 – Tree</h1>

HowHow is a very diligent student. Recently, he started to explore the stock market by himself. He learned that the Brownian Motion model for financial markets can be very useful. He wanted to be an expert on the model with the hope of being the next Warren Buffett. One use of the Brownian Motion model is in estimating stock prices. Those who are interested in the details can go check the popular Black-Scholes model. But we will keep the story short here. Assume that at each of the time step <em>t<sub>k</sub></em>, where <em>k </em>∈ {1<em>,</em>2<em>,…,n</em>} and <em>t</em><sub>1 </sub><em>&lt; t</em><sub>2 </sub><em>&lt; … &lt; t<sub>n</sub></em>, a piece of market information data <em>X<sub>t</sub></em><em><sub>k </sub></em>is recorded. Based on the models and the so-called efficient market hypothesis that HowHow will rely on, at any time stamp <em>t<sub>k</sub></em>, HowHow only needs the information data <em>X<sub>t</sub></em><em><sub>k</sub></em>−<sub>1 </sub>recorded at the previous time stamp <em>t<sub>k</sub></em>−1 to predict the stock price at <em>t<sub>k</sub></em>.

Given that the market that HowHow studied has a long history, the data set is super big. HowHow thus decided to organize the data set with a binary search tree <em>T </em>using <em>t<sub>k </sub></em>as the key and <em>X<sub>t</sub></em><em><sub>k </sub></em>as the data of every node. For the binary search tree <em>T</em>, we will assume that every sub-tree of <em>T </em>is a binary search tree with its left (right) sub-sub-tree containing data earlier (later) than the sub-tree root data in time.

<ol>

 <li>(10 pts) After constructing such a giant tree, HowHow was exhausted and could not think of how to get the node that he needed. Please help him by designing an algorithm that takes a node with key <em>t<sub>k </sub></em>as the input, and returns the “previous” node, which has key <em>t<sub>k</sub></em>−1. You can assume each node of the tree to contain three links: left, right, and parent. The algorithm should return nil when taking the earliest node <em>t</em><sub>1 </sub>as the input.</li>

 <li>(15 pts) Prove the correctness of the algorithm that you have designed.</li>

</ol>

After getting the node needed, HowHow applied his model, which predicted that the price will go up by 15%. HowHow then decided to throw all his money in, and guess what, a black swan came and HowHow lost all his money. He learned that the market is not as easy as he imagined.

Suddenly, VP Junior appeared and told HowHow that he is a Fuerdai—son of the VP of Crypto Arsenal, which is a crypto currency behemoth. VP Junior told HowHow his little secret of being wealthy in modern ages—mining crypto currency. If HowHow can help VP Junior solve some algorithm problems that have been bothering VP Junior recently, he can give HowHow a new RTX 3090 to help HowHow make a fresh start.

<ol start="3">

 <li>(10 pts) VP Junior asked HowHow to warm up with a concrete task. Given two sequences of traversal from a binary tree, reconstruct the original binary tree.</li>

</ol>

inorder[] = {43, 86, 21, 57, 15, 60, 38, 74} preorder[] = {86, 43, 57, 21, 60, 74, 38, 15}

<ol start="4">

 <li>(15 pts) Then, a more difficult task came from VP Junior. If all nodes are of distinct key values, are there two binary trees that result in the same (inorder, preorder) pair? Prove or disprove this statement.</li>

</ol>

After years of blood, sweat, and tears, HowHow finally solved the second task. The brand new life is right here under his nose. VP Junior asked HowHow to construct any binary tree (among many of them, in case there are more than one) from a pair of very long (inorder, preorder) sequences.

<ol start="5">

 <li>(15 pts) Design an algorithm that returns a binary tree from the (inorder, preorder) traversal sequences. Your algorithm should be time-wise as efficient as possible.</li>

</ol>

<h1>Problem 3 – Heap</h1>

First, consider a normal binary min-heap h, which is implemented with a complete binary tree, that supports following operations. Let |<em>h</em>| be the size of heap h.

<ul>

 <li>insert(x): inserts an element x to h in <em>O</em>(lg|<em>h</em>|)-time</li>

 <li>extractMin(): remove the minimum element from heap h in <em>O</em>(lg|<em>h</em>|)-time</li>

 <li>modify(x, v): modify the value of an element x to v in <em>O</em>(lg|<em>h</em>|)-time</li>

 <li>delete(x): delete an element x in h in <em>O</em>(lg|<em>h</em>|)-time</li>

</ul>

<ol>

 <li>(15 pts) We basically taught how to do h.insert(x) and h.extractMin() in class. Now, please design the corresponding algorithm for h.modify(x, v), and prove why it meets the time complexity requirement. (Technically, h.delete(x) can be implemented by generalizing h.extractMin(), or by combining h.modify(x, −∞) with h.extractMin()).</li>

</ol>

After finishing the task above, you are now a heap master! Now, we will work on a more challenging task. Consider an initially empty 2D array <em>A<sub>N M</sub></em>, with indices {(0<em>,</em>0)<em>,…,</em>(<em>N </em>− ×

1<em>,M </em>− 1)}. There is a data structure D that supports following operations on <em>A</em>. You can assume all the operations to be valid: only adding to empty locations and extracting/deleting from non-empty ones.

<ul>

 <li>add(i, j, v): add an element v to <em>A<sub>i,j </sub></em>in <em>O</em>(lg(<em>NM</em>))-time.</li>

 <li>extractMinRow(i): remove the minimum element in <em>i<sup>th </sup></em>row of <em>A </em>in <em>O</em>(lg(<em>NM</em>))-time.</li>

 <li>extractMinCol(j): remove the minimum element in <em>j<sup>th </sup></em>column of <em>A </em>in <em>O</em>(lg(<em>NM</em>))time.</li>

 <li>delete(i, j): delete the element at <em>A<sub>i,j </sub></em>in <em>O</em>(lg(<em>NM</em>))-time.</li>

</ul>

<ol start="2">

 <li>(10 pts) The following operations are called sequentially. The ShowState() command shows the contents of <em>A</em><sub>4</sub>×<sub>4</sub>. Please illustrate the output of each ShowState()

  <ul>

   <li>add(2, 3, 1); D.add(3, 3, 2); D.add(3, 0, 4); ShowState();</li>

   <li>extractMinRow(3) ; ShowState();</li>

   <li>add(1, 3, 3); ShowState();</li>

   <li>delete(2, 3); ShowState();</li>

   <li>extractMinCol(3 ); ShowState();</li>

  </ul></li>

 <li>(10 pts) Briefly explain the design of your data structure D. Your design should be reasonable and detailed enough to get full points. <em>(Hint: Did we say Heap in this problem?)</em></li>

 <li>(20 pts) Describe the design of the four operations and explain why they meet the time complexity requirements.</li>

</ol>

<strong> Programming Part </strong>

<h1>Problem 4 – Fake Binary Search Tree</h1>

Time Limit            :    1 s

Memory Limit       :    1024 MB

<h2>Problem Description</h2>

Giver, just like you, is a diligent student of the DSA class. He just learned a new data structure: <em>Binary Search Tree</em>. Let us recap Binary Search Tree (BST) a bit. A BST is a rooted binary tree that can help you find elements fast. Formally, if a binary tree satisfies the following constraints, then it is a BST.

<ul>

 <li>Every node of the tree has its own key.</li>

 <li>The key in each node is greater than or equal to any keys stored in its left sub-tree.</li>

 <li>The key in each node is less than or equal to any keys stored in its right sub-tree.</li>

</ul>

Then, the following algorithm, “binary search”, checks whether an element <em>x </em>is in the BST.

<strong>Algorithm 2: </strong>Lookup of a key in a BST.

<strong>Input: </strong>A BST rooted at <em>tree_node </em>and a <em>key </em>to look for

<strong>Output: True </strong>if the <em>key </em>is found, <strong>False </strong>otherwise <strong>Function </strong>Search<em>(tree_node, key):</em>

After studying this simple algorithm, Giver is super excited. He tries to apply it on general binary trees to see understand more about the algorithm. To his dismay, the algorithm does not work for general binary trees. Giver is curious about the number of keys that are in the general binary tree which can be found by applying the algorithm. Please help Giver locate those keys and compute the number!

<h2>Input</h2>

The first line of the input contains only one integer <em>N </em>(1 ≤ <em>N </em>≤ 10<sup>6</sup>), indicating the number of nodes in the given binary tree. The nodes are indexed from 1 to <em>N</em>. In the following <em>N </em>lines, the <em>i</em>th line contains the content of node <em>i</em>, which is represented by three integers <em>w,l,r </em>(1 ≤ <em>w </em>≤ 10<sup>9</sup><em>,l,r </em>∈ {−1} ∪ {1<em>,</em>2<em>,…,N</em>}), representing the key, the id of left child, and the id of right child. An index of −1 is used to indicate nil—that is, when there is no child. The keys in each node are unique. It is guaranteed that the input forms a valid binary tree rooted at 1.

<h2>Output</h2>

Print an integer representing the number of keys (within the binary tree) that can be found by the algorithm (returns <strong>True</strong>).

<strong>Subtask 1 (30 pts) </strong>• <em>N </em>≤ 1000.

<strong>Subtask 2 (70 pts)</strong>

<ul>

 <li>No other constraints.</li>

</ul>

<h2>Sample Input 1                                           Sample Output 1</h2>

5                                3

<ul>

 <li>2 4</li>

 <li>-1 3</li>

 <li>-1 -1</li>

 <li>-1 5</li>

 <li>-1 -1</li>

</ul>

<h2>Sample Input 2                                           Sample Output 2</h2>

6                                2

2 2 -1

1 -1 3

<ul>

 <li>4 6</li>

 <li>5 -1</li>

 <li>-1 -1</li>

</ul>

9 -1 -1

<h2>Sample Input 3                                           Sample Output 3</h2>

7                                4

10 2 7

3 3 4

1 -1 -1

7 5 -1 9 -1 6

5 -1 -1

4 -1 -1

<h1>Problem 5 – Intersecting Triangles (100 pts)</h1>

Time Limit            :    3 s

Memory Limit       :    1024 MB

<h2>Problem Description</h2>

There are <em>N </em>ants who live on a 2D plan. The <em>i</em>-th ant rests on a point <em>p<sub>i </sub></em>in the line of <em>y </em>= 1 during the night. Then, at some starting time, the ant first walks by a straight line to another point <em>q<sub>i </sub></em>in the line of <em>y </em>= 0 to start working. After going to <em>q<sub>i</sub></em>, the ant starts working by going straight from point <em>q<sub>i </sub></em>to <em>r<sub>i</sub></em>, both in the line of <em>y </em>= 0. Then, at some ending time, the ant walks back to <em>p<sub>i </sub></em>from <em>r<sub>i </sub></em>by a straight line. That is, the path of each ant follows a triangle (<em>p<sub>i</sub>,q<sub>i</sub>,r<sub>i</sub></em>). Each different ant can have a different walking speed, a different starting time, and/or a different end time.

The Queen Ant recently received some complaints from the ants, saying that some ants bump into each other in their daily triangular path. To understand how serious the situation is, the Queen Ant asks the Scientist Ant to list, from the paths of all ants, which ants may bump into each other—at the vertex of the triangular path, at one other point of the path, on a segment of the path. Please help the scientist determine the number of <strong>pairs </strong>of ants that may bump into each other on their triangular paths.

<h2>Input</h2>

The input can be read through the provided header file generator.h. Please first call generator.init() to initialize the generator, then calling generator.getT() will return the number of test cases <em>T</em>. For each test case, calling generator.getData(&amp;N, &amp;P, &amp;Q, &amp;R) will let you get the number of triangles <em>N</em>, and their vertices. Note that the type of N should be int, and the type of P, Q, R should be int*. After calling, P[0..N-1] would store {<em>p</em><sub>1</sub><em>,p</em><sub>2</sub><em>,…,p<sub>N</sub></em>}, and Q[0..N-1], R[0..N-1] will store the other points, respectively. Below is an example usage, the program will run and get the data correctly; however, you will get WA if you submit it directly:

#include &lt;stdio.h&gt; #include “generator.h” int main() { generator.init(); int t = generator.getT(); while (t–) { int n, *p, *q, *r; generator.getData(&amp;n, &amp;p, &amp;q, &amp;r);

/* do something int ans = 0; for (int i = 0; i &lt; n; i++) ans += p[i] * q[i] * r[i]; printf(“%d
”, ans);

*/

}

}

<strong>Note that you should not read anything from standard input in your program; otherwise, the behavior is undefined.</strong>

You can download the generator header “generator.h” <a href="https://www.csie.ntu.edu.tw/~giver/DSA/hw2/generator.h">here</a>.

<strong>Output</strong>

For each test case, print the number of pairs of intersecting triangles.

<h2>Subtasks</h2>

In all subtasks, −2<sup>20 </sup>≤ <em>p<sub>i</sub>,q<sub>i</sub>,r<sub>i </sub></em>≤ 2<sup>20 </sup>− 1 holds for each 1 ≤ <em>i </em>≤ <em>N</em>.

<strong>Subtask 1 (20 pts)</strong>

<ul>

 <li>1 ≤ <em>N </em>≤ 3000, 1 ≤ <em>T </em>≤ 10</li>

</ul>

<strong>Subtask 2 (20 pts)</strong>

<ul>

 <li>1 ≤ <em>N </em>≤ 10<sup>5</sup>, 1 ≤ <em>T </em>≤ 10</li>

 <li>all <em>p<sub>i </sub></em>are distinct.</li>

 <li>all <em>q<sub>i </sub></em>and <em>r<sub>i </sub></em>are distinct.</li>

</ul>

<strong>Subtask 3 (10 pts)</strong>

<ul>

 <li>1 ≤ <em>N </em>≤ 10<sup>5</sup>, 1 ≤ <em>T </em>≤ 10</li>

 <li>all <em>p<sub>i </sub></em>are distinct.</li>

</ul>

<strong>Subtask 4 (10 pts)</strong>

<ul>

 <li>1 ≤ <em>N </em>≤ 10<sup>5</sup>, 1 ≤ <em>T </em>≤ 10</li>

</ul>

<strong>Subtask 5 (40 pts)</strong>

<ul>

 <li>1 ≤ <em>N </em>≤ 3 × 10<sup>6</sup>, <em>T </em>= 1</li>

</ul>

<h1>Sample Cases</h1>

<h2>Sample Input 1</h2>

1 1 5 16

538724387836423741 325591348600219474 187178394057222755 353408734984306357

<h2>Actual Sample Input 1</h2>

T = 1

N = 5

<ul>

 <li>= {12, 7, -10, 12, 9}</li>

 <li>= {11, 5, 5, -16, 5}</li>

 <li>= {-2, -13, -8, 8, 10}</li>

</ul>

<strong>Sample Output 1</strong>

10

<h2>Sample Input 2</h2>

2 1 5 16

51414933668525662 550301789874357166 622479167726386043 650347521267739593

<h2>Actual Sample Input 2</h2>

T = 1

N = 5

<ul>

 <li>= {2, -3, 6, -16, 0}</li>

 <li>= {-7, -14, -5, 1, 6}</li>

 <li>= {-12, 5, 9, 13, -8}</li>

</ul>

<strong>Sample Output 2</strong>

9

<h2>Sample Input 3</h2>

3 1 5 16

203739077647024131 805985539835675567 140205801930598907 908190957489194415

<h2>Actual Sample Input 3</h2>

T = 1

N = 5

<ul>

 <li>= {2, 14, -16, -7, 13}</li>

 <li>= {7, 14, 0, 7, -5}</li>

 <li>= {11, -12, 8, -12, -1}</li>

</ul>

<strong>Sample Output 3</strong>

10

<h2>Sample Input 4</h2>

1 2 10 16

869534322540300934 837268419296844257 456729939812480767 541019751318820673

<h2>Actual Sample Input 4</h2>

T = 2

N = 10

P = {-5, 15, 15, -8, -11, -5, -13, -14, 15, 10} Q = {-7, -12, -4, -13, 5, 1, 14, -16, -16, -14}

R = {2, -13, 1, 9, 9, 1, 1, 12, -15, 6}

N = 10

<ul>

 <li>= {7, -4, -7, 12, 9, -13, -11, 5, 3, 8}</li>

 <li>= {8, 5, 3, -4, -10, -10, 2, 2, -7, -9}</li>

 <li>= {-11, -1, -1, -12, 4, 13, -16, -3, -7, 4}</li>

</ul>

<h2>Sample Output 4</h2>

45

44

<h1>Problem 6 – Package Arrangement</h1>

Time Limit            :    3 s

Memory Limit       :    1024 MB

<h2>Problem Description</h2>

Ling is a worker in a factory. Each day, a sequence of packages, each of a different height, are “pushed” to several production lines. Each production line can be viewed as a queue where the packages that are “pushed” into the line earlier are in its front.

Ling’s job, on the other hand, is to “pop” a package from some production line. The popped package will then be moved to a target line. The control panel that Ling uses has three buttons for each production line: popping the (1) first / (2) last / (3) highest package from the production line, and moving it to the target line.

Occasionally, some production line may be closed for maintenance. When it happens, all the packages on the closed production line will be dequeued and pushed to another running production line in order. We call this operation to be “merging” the closed production line and the running production line. In other words, the sequence of packages in the closed production line is concatenated to the end of the running production line after the merge operation. The closed production line then becomes empty and will not be used again.

The pushing and merging operations are factory-controlled, and Ling cannot do anything about them. What Ling can do is to decide whether to execute the popping action of the first / last / highest package from one of the production lines after each operation. The decision of the popping executions from Ling forms a particular height sequence of the target line. After Ling’s executions every day, he writes down the height sequence of the target line on the daily log of the factory.

Nevertheless, Ling is not the most careful person in the world, and hence sometimes makes mistakes in his writing. An obvious mistake is that the line in the record is not possible from any combination of the popping actions. Ling hopes to capture this kind of mistake before sending the daily log to the factory. Can you help him do that?

<h2>Input</h2>

The first line contains an integer <em>T</em>, which indicates the number of test cases. The following lines contain <em>T </em>test cases and each test case is formatted as follows:

<ul>

 <li>The first line of the test case contains three integers <em>N</em>, <em>O</em>, and <em>L</em>. <em>N </em>indicates the number of packages. <em>O </em>indicates the total number of “push” and “merge” operations. <em>L </em>indicates the number of production lines.</li>

 <li>The next <em>O </em>lines are the “push” and “merge” operations, one in each line. The line with push comes with two numbers, a package height 1 ≤ <em>h </em>≤ <em>N </em>and a production line number 0 ≤ <em>ℓ &lt; L </em>to push the package to; the line with merge comes with two numbers, a broken production line number 0 ≤ <em>ℓ<sub>b </sub>&lt; L </em>and a different running production line number 0 ≤ <em>ℓ<sub>r </sub>&lt; L</em>.</li>

 <li>The last line contains the record from Ling, which is a permutation of {1<em>,</em>2<em>,…,N</em>} indicating the heights of the packages on the target line.</li>

</ul>

<h2>Output</h2>

If it is possible to arrange the packages to the given order by any combinations of the popping actions, please print possible in a single line; otherwise please print impossible in a single




line.

<h2>Constraints</h2>

<ul>

 <li>1 ≤ <em>T </em>≤ 10</li>

 <li>1 ≤ <em>N,L </em>≤ 10<sup>5</sup></li>

 <li><em>N </em>≤ <em>O &lt; N </em>+ <em>L</em></li>

</ul>

<strong>Subtask 1 (15 pts)</strong>

<ul>

 <li>1 ≤ <em>N,L </em>≤ 1000</li>

</ul>

<strong>Subtask 2 (25 pts)</strong>

<ul>

 <li><em>L </em>= 1, which also means no “merge” operations</li>

</ul>

<strong>Subtask 3 (10 pts)</strong>

<ul>

 <li>No “merge” operations</li>

</ul>

<strong>Subtask 4 (50 pts)</strong>

<ul>

 <li>No other constraints.</li>

</ul>




<h2>Sample Input 1</h2>

2

5 5 1

push 2 0 push 1 0 push 3 0 push 4 0 push 5 0

2 1 5 3 4

5 5 1

push 1 0 push 4 0 push 2 0 push 5 0 push 3 0

5 1 3 2 4

<h2>Sample Output 1</h2>

possible possible

<h2>Sample Input 2</h2>

2

10 13 5 push 10 3 merge 3 4 push 2 1 push 7 4 push 8 4 push 9 4 push 5 4 merge 1 4

push 4 0 merge 4 2 push 1 2 push 6 2 push 3 2

10 4 8 7 9 1 3 5 6 2

10 13 5 push 7 1 push 5 1 push 1 1 merge 1 4

push 9 4 push 4 0 push 2 4 push 6 0 push 8 4 merge 4 3 push 3 0 merge 2 3

push 10 3

4 6 9 7 8 3 2 10 5 1

<h2>Sample Output 2</h2>

impossible possible

<h2>Sample Input 3</h2>

2

10 19 10 push 3 3 push 1 7 push 10 3 merge 6 2 push 4 8 merge 1 3 push 8 3 merge 9 7 merge 7 3 push 7 3 merge 8 3 merge 5 3

push 6 3 push 9 3 merge 4 0 push 2 2 merge 3 0 push 5 0

merge 0 2

10 3 6 8 2 7 9 1 5 4

10 19 10 push 7 6 merge 3 2

merge 6 2

push 6 4 merge 7 8 merge 4 5 push 9 5 merge 0 1 push 8 1 push 5 5 push 2 8 push 3 2 merge 8 5 push 1 2 merge 9 1 push 10 2 merge 2 1 push 4 1

merge 1 5

6 9 7 5 3 1 2 10 4 8

<h2>Sample Output 3</h2>

impossible possible