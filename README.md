Download Link: https://assignmentchef.com/product/solved-cis450-computer-architecture-and-operations-homework-5
<br>
<ol>

 <li>(5 pts.) Consider the C program below. (For space reasons, we are not checking error return codes, so assume that all functions return normally.)</li>

</ol>

<strong>int main () {  if (fork() == 0) {      if (fork() == 0) { </strong>

<strong>           printf(“3”); fflush(stdout); </strong>

<strong>        } </strong>

<strong>        else { </strong>

<strong>           pid_t pid; int status; </strong>

<strong>    if ((pid = wait(&amp;status)) &gt; 0) {           printf(“4”); fflush(stdout); </strong>

<strong>           } </strong>

<strong>        } </strong>

<strong> } </strong>

<strong> else { </strong>

<strong>        printf(“2”); fflush(stdout); </strong>

<strong>        exit(0); </strong>

<strong> } </strong>

<strong> printf(“0”); fflush(stdout); </strong>

<strong> return 0; </strong>

<strong>}  </strong>

For each of the following strings, circle whether (Y = yes) or not (N = no) this string is a possible output:




<ol>

 <li><strong>32040</strong> Y  N</li>

 <li><strong>34002</strong> Y  N</li>

 <li><strong>30402</strong> Y  N</li>

 <li><strong>23040</strong> Y  N</li>

 <li><strong>40302</strong> Y  N</li>

</ol>




<ol start="2">

 <li>(10 pts.) Process creation questions:</li>

</ol>




<ol>

 <li>How many processes are created, including the parent process, when the following code is executed? ___.</li>

</ol>

<table width="348">

 <tbody>

  <tr>

   <td width="348"><strong>Process Model </strong></td>

  </tr>

 </tbody>

</table>

<strong>int main() { </strong>

<strong>  int i, p; </strong>

<strong> </strong>

<strong>  for(i=1; i&lt;=3; i++) </strong>

<strong>  {     p = fork();     if (p&gt;0)     {       printf(“i = %d
”, i);       exit(0);  // this one (*) </strong>

<strong>    } </strong>

<strong>    printf((“i = %d
”, i); </strong>

<strong>  }   exit(0); </strong>

<strong>} </strong>













<ol>

 <li>Draw the Process Model above for the processes created in part (a), including the parent process, in the process model, <strong><em>indicate the output generated by each process</em></strong>.</li>

 <li>If the first exit(0) statement in part (a) is removed, denoted with (*), how many processes would be created? ________. You don’t need to draw the process model for this part ;-).</li>

</ol>




<ol start="3">

 <li>(10 pts.) The following problem concerns basic cache lookups. You may assume that:</li>

</ol>

<ul>

 <li>The memory is byte addressable. Memory accesses are to 1-byte words, not 4-byte words.</li>

 <li><strong>Physical addresses are 13 bits wide. </strong></li>

 <li>The cache is a 2-way set associative cache with a 4-byte line size and 16 total lines as shown below.</li>

</ul>

Note that all numbers are given in <strong>hexadecimal</strong> format.







<ul>

 <li>The box below shows the format of a physical address. Indicate, by labeling the rest of the fields in the diagram, the bits that are used to determine the following:</li>

</ul>




<strong>CT = Cache Tag (done), CI = Cache Index, and CO = Cache Offset </strong>

<strong>               </strong>

12  11  10  9   8   7  6   5  4   3   2   1   0

<table width="317">

 <tbody>

  <tr>

   <td width="24"> CT</td>

   <td width="24">  CT</td>

   <td width="24">  CT</td>

   <td width="24">  CT</td>

   <td width="24">  CT</td>

   <td width="24">   CT</td>

   <td width="24">   CT</td>

   <td width="24">   CT</td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="29"> </td>

  </tr>

 </tbody>

</table>




<ul>

 <li>For each physical address given below, if a cache hit occurs, indicate the cache entry accessed and the cache byte value returned in hex. If a cache miss occurs, just write ‘N’ next to “Cache Hit?” and leave the cache byte returned blank.</li>

</ul>




<h1> Physical Address: 0x1E1F</h1>

12  11  10  9   8   7  6   5  4   3   2   1   0

<table width="312">

 <tbody>

  <tr>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

  </tr>

 </tbody>

</table>










<table width="379">

 <tbody>

  <tr>

   <td width="241"><strong>Parameter </strong></td>

   <td width="138"><strong>Value </strong></td>

  </tr>

  <tr>

   <td width="241">Byte Offset</td>

   <td width="138">0x</td>

  </tr>

  <tr>

   <td width="241">Cache Index</td>

   <td width="138">0x</td>

  </tr>

  <tr>

   <td width="241">Cache Tag</td>

   <td width="138">0x</td>

  </tr>

  <tr>

   <td width="241">Cache Hit (Y/N)?</td>

   <td width="138"> </td>

  </tr>

  <tr>

   <td width="241">If Hit, Cache Byte Returned</td>

   <td width="138">0x</td>

  </tr>

 </tbody>

</table>




<h1>Physical Address: 0x00B2</h1>

12  11  10  9   8   7  6   5  4   3   2   1   0

<table width="312">

 <tbody>

  <tr>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

   <td width="24"> </td>

  </tr>

 </tbody>

</table>










<table width="379">

 <tbody>

  <tr>

   <td width="241"><strong>Parameter </strong></td>

   <td width="138"><strong>Value </strong></td>

  </tr>

  <tr>

   <td width="241">Byte Offset</td>

   <td width="138">0x</td>

  </tr>

  <tr>

   <td width="241">Cache Index</td>

   <td width="138">0x</td>

  </tr>

  <tr>

   <td width="241">Cache Tag</td>

   <td width="138">0x</td>

  </tr>

  <tr>

   <td width="241">Cache Hit (Y/N)?</td>

   <td width="138"> </td>

  </tr>

  <tr>

   <td width="241">If Hit, Cache Byte Returned</td>

   <td width="138">0x</td>

  </tr>

 </tbody>

</table>


