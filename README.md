Download Link: https://assignmentchef.com/product/solved-ee5111-project-1-estimation-theory
<br>
Problem

Consider the following OFDM-like system model:

<strong>y </strong>= <strong>XFh </strong>+ <strong>n</strong><em>,                                                                                </em>(1)

where <strong>y </strong>∈ C<sup>512 </sup>are the set of observations, <strong>X </strong>is a 512 dimensional diagonal matrix with known symbols, <strong>h </strong>is the <em>L </em>tap time domain channel vector, <strong>F </strong>is the 512×<em>L </em>matrix performing IDFT<sup>1 </sup>and <strong>n </strong>is complex Gaussian noise with variance <em>σ</em><sup>2</sup>.

For the following set of experiments, generate a set of random bits and modulate them as QPSK symbols to generate<sup>2 </sup><strong>X</strong>. <strong>h </strong>is a multipath Rayleigh fading channel vector with an exponentially decaying power-delay profile <strong>p </strong>where <em>p</em>[<em>k</em>] = <em>e</em><sup>−<em>λ</em>(<em>k</em>−1)</sup><em>,k </em>= 1<em>,</em>2<em>…L </em>. That is, each component of <strong>h </strong>will be], where. Here, <em>λ</em>

is the decay factor (and choose <em>λ </em>= 0<em>.</em>2 for your simulations). Now, perform the following experiments on the described problem set up.

<ol>

 <li>Estimate <strong>h </strong>using least squares method of estimation with <em>L </em>= 32.<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a></li>

 <li>Now, suppose that <strong>h </strong>is sparse with just 6 non zero taps. Assuming that you know the non zero locations, estimate <strong>h </strong>using Least squares with the sparsity information.</li>

 <li>Next, introduce guard band of 180 symbols on either side<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a>, i.e. now we have reduced number of observations. For this case:

  <ul>

   <li>Repeat (1),(2) for the above set up.</li>

   <li>Apply regularization and redo least squares. Use various values of <em>α </em>for regularization with <em>α</em><strong>I </strong>and compare the estimation results.</li>

  </ul></li>

 <li>Perform least squares estimation on <strong>h </strong>with the following linear constraints :</li>

</ol>

<em>h</em>[1] = <em>h</em>[2] <em>h</em>[3] = <em>h</em>[4] <em>h</em>[5] = <em>h</em>[6]

For each of the above experiments, you have to compare E[<strong>hˆ</strong>] and <strong>h</strong>, theoretical and simulated MSE of estimation, all averaged over 10000 random trials. (Generate different instances of <strong>X </strong>and <strong>n </strong>for each trial.) Repeat the experiments for <em>σ</em><sup>2 </sup>= {0<em>.</em>1<em>,</em>0<em>.</em>01} for each case. Plot <strong>hˆ </strong>and <strong>h </strong>for one trial in each of the above cases.

<ol start="5">

 <li>Next, for the scenarios in question 2 and 3, compare the results with the estimates you get from the following steps :</li>

</ol>

<strong>– </strong>Step 1 :

<strong>Algorithm 1: </strong>To find the non-zero locations of the sparse vector <strong>h </strong>(support estimate).

<strong>Input: </strong>Observation <strong>y</strong>, matrix <strong>A </strong>= <strong>XF</strong>, sparsity <em>k<sub>o </sub></em>= 6

Initialize<strong> y for </strong><em>k </em>← 1 <em>to k</em><sub>0 </sub><strong>do</strong>

Identify the next column as <em>t<sub>k </sub></em>= argmax|<strong>A</strong><em><sup>H</sup><sub>j </sub></em><strong>r</strong><em><sup>k</sup></em><sup>−1</sup>|

<em>j</em>

Expand the current support as

Update residual: <strong>r</strong><em><sup>k </sup></em>= [<strong>I</strong><sub>512 </sub>− <strong>P</strong><em><sub>k</sub></em>]<strong>y </strong>where <strong>P</strong>.

Increment <em>k </em>→ <em>k </em>+ 1 <strong>end</strong>

<strong>Output: </strong>Support estimate S<sup>ˆ </sup>= <sup>S</sup><em><sub>omp</sub><sup>k</sup></em>

<strong>– </strong>Step 2 : Now that you know the non-zero locations of <strong>h</strong>, estimate <strong>h </strong>using least squares.

<em>*In the algorithm </em><strong>A</strong><em><sub>j </sub>is the j<sup>th </sup>column of matrix </em><strong>A</strong><em>, </em><strong>A</strong><sub>S </sub><em>denotes the sub-matrix of </em><strong>A </strong><em>formed using the columns indexed by </em>S <em>and </em><strong>A</strong><sup>† </sup>= (<strong>A</strong><em><sup>H</sup></em><strong>A</strong>)<sup>−1</sup><strong>A</strong><em><sup>H </sup>is the Moore-Penrose pseudo inverse of </em><strong>A</strong><em>. Also, </em><strong>I</strong><em><sub>N </sub>is the N dimensional identity matrix.</em>

<h1>2           Submission guidelines</h1>

You need to submit the solutions for this problem no later than March 1, 2021 (11:59 pm). Upload a compressed file containing the program/programs your team has written for the mini project in Moodle. The viva for each team will be conducted jointly on a date and time convenient for all the members.

2

<a href="#_ftnref1" name="_ftn1">[1]</a> Note that you are dealing with complex data now and hence the least squares estimate for the model <strong>y </strong>= <strong>Xb </strong>shall now be <strong>b</strong><sup>ˆ </sup>= (<strong>X</strong><em><sup>H</sup></em><strong>X</strong>)<sup>−1</sup><strong>X</strong><em><sup>H</sup></em><strong>y</strong>

<a href="#_ftnref2" name="_ftn2">[2]</a> Suppress to zero the first and last 180 symbols in <strong>X</strong>

1