Download Link: https://assignmentchef.com/product/solved-cse-6140-homework-3
<br>






<h1>Problem 1</h1>

To prove this problem, which we will call <em>FIBER</em>, is NP-Complete we will first show <em>FIBER </em>∈ NP, then we will show for some already known NP-Complete problem <em>Y </em>that <em>Y </em>≤<em><sub>p </sub>FIBER</em>.

<strong>Theorem 1. </strong><em>FIBER </em>∈ NP<em>.</em>

<em>Proof. </em>To show this, we must find a certificate <em>T </em>and a certifier <em>B </em>that runs in polynomial time. Let <em>T </em>be a subset of <em>C</em>. The certifier will then check that all cities are connected using the roads within <em>T </em>and that for each <em>t </em>∈ <em>T</em>, that 1 ≤ <em>d<sub>T</sub></em>(<em>t</em>) ≤ <em>k</em>. Both of these can be done in polynomial time, which completes the proof.

<strong>Theorem 2. </strong><em>FIBER is NP-Complete.</em>

<em>Proof. </em>Consider an arbitrary instance of the Hamiltonian Path problem with <em>k</em><sup>0 </sup>vertices. Our goal is to transform this instance into a single instance of <em>FIBER </em>with identical solutions. For each node in <em>HAM </em>−<em>PATH</em>, we make a city <em>c </em>∈ <em>C </em>for <em>FIBER</em>. From this, add the corresponding edges such that <em>k </em>= 2 for <em>FIBER</em>. With this construction, we will prove that the two problems have corresponding solutions.

First, consider some instance of <em>HAM </em>− <em>PATH</em>. By construction, every node in <em>HAM </em>− <em>PATH </em>becomes a city in <em>FIBER</em>, and as <em>HAM </em>− <em>PATH </em>is connected it follows that every city is present in <em>FIBER</em>. Additionally, by construction the connecting path of <em>HAM </em>− <em>PATH </em>are the roads in <em>FIBER</em>, so all the cities are connected with <em>d<sub>T</sub></em>(<em>u</em>) ≤ 2 ∀<em>u </em>∈ <em>C</em>. Thus when <em>HAM </em>− <em>PATH </em>is solved so too is <em>FIBER</em>.

Now consider an instance of <em>FIBER </em>with <em>k </em>= 2. For each city in the instance, we have a node for a graph. Additionally, for each road in <em>FIBER </em>we will have an edge between nodes in the graph. Since the cities in <em>FIBER </em>are connected, so too must all the nodes be in the graph by construction. Likewise, since <em>k </em>= 2 for <em>FIBER</em>, the resulting edges must create a path. Thus when <em>FIBER </em>is solved so too is <em>HAM </em>− <em>PATH</em>.

Thus, <em>HAM </em>− <em>PATH </em>≤<em><sub>p </sub>FIBER </em>and <em>FIBER </em>is NP-Complete. <strong>Problem 2</strong>

To show that <em>PY GMALION </em>is NP-Complete, we will first show that <em>PY GMALION </em>∈ NP.

<strong>Theorem 3. </strong><em>PY GMALION </em>∈ NP<em>.</em>

<em>Proof. </em>To show this, we must find a certificate <em>T </em>and a certifier <em>B </em>that runs in polynomial time. Let <em>T </em>be a subset of towns where the bunkers will be placed. The certifier will then check that there are at most <em>k </em>bunkers (i.e. |<em>T</em>| ≤ <em>k</em>) and that each <em>e </em>= (<em>u,v</em>) ∈ <em>E </em>satisfies <em>u </em>∈ <em>T </em>or <em>v </em>∈ <em>T</em>. Both of these can be done in polynomial time by simply counting the cardinality of <em>T </em>and checking if a node is in <em>T</em>, so the proof is complete.

<strong>Theorem 4. </strong><em>PY GMALION is NP-Complete.</em>

<em>Proof. </em>Consider an arbitrary instance of the Vertex Cover problem. Our goal is to transform this instance into a single instance of <em>PY GMALION </em>with identical solutions. For an instance of <em>V C</em>, anytime there is a node of degree

2 or more, duplicate it and make both the original node and its new copy into towns for <em>PY GMALION</em>. Turn each original edge into a road, then add an additional road connecting the original node to its duplicate. Additionally add roads that connect the duplicate node to all the nodes connected to the original node. With this construction, we will prove that the two problems have corresponding solutions.

Consider some instance of <em>V C </em>that is solved. That means we have some set <em>T </em>⊆ <em>V </em>that touch every edge in <em>E</em>. If any of the duplicated nodes in <em>PY GMALION </em>were nodes in <em>T</em>, we can pick either the newly created town or the original town to place a bunker on; otherwise we pick the same town to place a bunker on corresponding to the node in <em>T</em>. By our construction, since we duplicate any node of of degree 2 or more then add corresponding edges, all of the towns with bunkers will cover all of the towns not connected by bunkers, so when <em>V C </em>is solved so too is

<em>PY GMALION</em>.

Consider some instance of <em>PY GMALION </em>that is solved. Thus we have bunkers placed at towns in such a way that every town in either connected to a bunker or has a bunker. If there are two towns that have identical roads and are themselves connected, we can consolidate them by “deconstruction”. Because every town is adjacent to or on a bunker, all roads are connected to a bunker. This is by definition a vertex cover, so we are done.

Thus, <em>V C </em>≤<em><sub>p </sub>PY GMALION </em>and the proof is complete.

<h1>Problem 3</h1>

For this problem, I wrote both a divide &amp; conquer algorithm and a dynamic programming algorithm to find the maximum sum subset of given files. Below is the graph comparing the two methods:

My divide &amp; conquer algorithm was designed as follows. It takes in an array of values, a start index, and a start index. If the start index equals the stop, the algorithm returns the value of the array at said index. Otherwise it computes the midpoint of the two indices (rounding down) then recursively calls two instances of itself for the intervals (start, mid) and (mid + 1, stop). Additionally, a cross method is called that computes the largest sum within the middle of the set. Of these values, the maximum is returned along with the corresponding indices. The space complexity of this program is <em>O</em>(<em>n</em>), as there are several variables and an array of size <em>n</em>. The time complexity can be expressed by the recurrence relationship <em>T</em>(<em>n</em>) = 2<em>T</em>(<em>n/</em>2) + Θ(<em>n</em>), which by the Master theorem gives us complexity of Θ(<em>n</em>log<em>n</em>). This can be seen in the above figure, which matches this complexity well.

My dynamic programming algorithm was designed as follows. It takes in an array of values, then creates two arrays of size <em>n</em>. A for loop is then run that computes the following recurrence relation:



<sub></sub>0                                                   <em>j </em>= 0

<em>B</em>(<em>j</em>) =

<sub></sub>max{<em>B</em>(<em>j </em>− 1) + <em>a<sub>j</sub>,</em>0}            otherwise

It additionally computes the corresponding indices that give <em>B</em>(<em>n</em>). The space complexity of tis program is <em>O</em>(<em>n</em><sup>3</sup>), as there is the initial values array, then two arrays of same size are create to store <em>B</em>(<em>j</em>) values and start indices. The time complexity is <em>O</em>(<em>n</em>) as there is a single for loop that calls on precomputed values from an array. This complexity can be seen in the above figure.

By the above analysis, the dynamic programming algorithm should be faster than the divide &amp; conquer one by a significant amount for large <em>n</em>. This can be seen in the graph above, with the dynamic programming one consistently outperforming the divide &amp; conquer. Note that this comes as a trade off – if <em>n </em>becomes incredible large far more memory must be committed for DP, which could potentially change the results of the analysis.