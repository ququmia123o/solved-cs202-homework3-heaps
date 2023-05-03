Download Link: https://assignmentchef.com/product/solved-cs202-homework3-heaps
<br>
In this programming assignment, you will find a software solution to the problem of the director of Covid-19 Clinic. She is trying to figure out how many doctors should work in this clinic. For each doctor in this clinic, the expense increases; however, according to the standards, the average waiting time for all patients should not exceed a given amount of time. So, she needs to optimize this number and asks for your help in this task. The clinic has the data of past patients. Your program should use these data to calculate average waiting times and find out the minimum number of doctors needed to meet the average waiting time requirement.

The data are stored in a plain text file<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>. The first line of the file contains the number of patients. The subsequent lines contain four integers, each separated by one or more whitespace characters (space or tab). These denote, respectively, the patient id, the patient priority (from 1 to 10, higher is more urgent), arrival time (in minutes from a given point—e.g., 12:00 am) and service time (in minutes).

For example, from the file content given below, we understand that there are 3 patients. The first patient with id 1 has priority of 9, arrives at the clinic at minute 1, and his examination lasts for 5 minutes.  The second patient with id 14 has priority of 3, arrives at the clinic at minute 70, and his examination lasts for 10 minutes. The third patient with id 5 has priority of 3, arrives at the clinic at minute 82, and his examination lasts for 70 minutes.

Sample input file:

<table width="0">

 <tbody>

  <tr>

   <td width="55">31</td>

   <td width="48">9</td>

   <td width="33">1</td>

   <td width="469">5</td>

  </tr>

  <tr>

   <td width="55">14</td>

   <td width="48">3</td>

   <td width="33">70</td>

   <td width="469">10</td>

  </tr>

  <tr>

   <td width="55">5</td>

   <td width="48">3</td>

   <td width="33">82</td>

   <td width="469">70</td>

  </tr>

 </tbody>

</table>

In this assignment, you are asked to write a simulation program that reads patient data from an input file and <u>calculates the minimum number of doctors required for a given maximum average waiting</u> <u>time</u>.

In your implementation, you may make the following assumptions:

<ul>

 <li>The data file will always be valid. All data are composed of integers.</li>

 <li>In the data file, the patients are sorted according to their arrival times. – There may be at most 2000 patients in the data file.</li>

</ul>

Your implementation must obey the following requirements:

<ul>

 <li>The patient with the highest priority should be examined first.</li>

 <li>In case of having two patients with the same highest priority, the patient who has waited longer should be selected first.</li>

 <li>If more than one doctor is available at a given time, the patient is assigned to the doctor with a lower id.</li>

 <li>Once a patient is assigned to a doctor, the doctor immediately starts examining that patient and is not available during the examination period given for that patient. After the examination of that patient ends, the doctor becomes available immediately.</li>

 <li>The waiting time of a patient is the duration (difference) between the arrival time of the patient and the time he is assigned to a doctor.</li>

</ul>




Put the class definition and implementation of the heap data structure in <strong>maxHeap1.h </strong>and<strong> maxHeap1.cpp</strong>, respectively. Put the function that drives your simulation as well as your main function in a file called <strong>simulator.cpp</strong> function.

The name of the input file and the maximum average waiting time will be provided as command line arguments to your program. Thus, your program should run using two command line arguments. The application interface is simple and given as follows:

<h2><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5a3e333031292e283b1a3235292e343b373f">[email protected]</a>:~&gt;./simulator_Q1 &lt;filename&gt; &lt;avgwaitingtime&gt;</h2>

Assuming that you have an executable called “simulator_Q1”, this command calls the executable with two command line arguments. The first one is the name of the file from which your program reads the patient data. The second one is the maximum average waiting time; your program should calculate the minimum number of doctors required for meeting this <strong>avgwaitingtime.</strong> You may assume that the maximum average waiting time is given as an integer.

<h2>Hint</h2>

Use the heap data structure to hold patients that are waiting for a doctor and to find the patient with the highest priority. Update the heap whenever a new patient arrives or a patient examination starts. In order to find the optimum number of doctors needed, repeat the simulation for increasing number of doctors and return the minimum number of doctors that will achieve the maximum average waiting time constraint. Display the simulation for which you find the optimum number of doctors.

<strong> </strong>

<strong>SAMPLE OUTPUT:</strong>

Suppose that you have the following input file consisting of the patient data. Also suppose that the name of the file is patients.txt.

<table width="0">

 <tbody>

  <tr>

   <td width="50">121</td>

   <td width="48">2</td>

   <td width="48">1</td>

   <td width="468">10</td>

  </tr>

  <tr>

   <td width="50">2</td>

   <td width="48">4</td>

   <td width="48">1</td>

   <td width="468">14</td>

  </tr>

  <tr>

   <td width="50">3</td>

   <td width="48">1</td>

   <td width="48">1</td>

   <td width="468">6</td>

  </tr>

  <tr>

   <td width="50">4</td>

   <td width="48">1</td>

   <td width="48">1</td>

   <td width="468">5</td>

  </tr>

  <tr>

   <td width="50">5</td>

   <td width="48">2</td>

   <td width="48">4</td>

   <td width="468">10</td>

  </tr>

  <tr>

   <td width="50">6</td>

   <td width="48">4</td>

   <td width="48">7</td>

   <td width="468">14</td>

  </tr>

  <tr>

   <td width="50">7</td>

   <td width="48">2</td>

   <td width="48">9</td>

   <td width="468">10</td>

  </tr>

  <tr>

   <td width="50">8</td>

   <td width="48">4</td>

   <td width="48">11</td>

   <td width="468">14</td>

  </tr>

  <tr>

   <td width="50">9</td>

   <td width="48">1</td>

   <td width="48">13</td>

   <td width="468">6</td>

  </tr>

  <tr>

   <td width="50">10</td>

   <td width="48">1</td>

   <td width="48">14</td>

   <td width="468">5</td>

  </tr>

  <tr>

   <td width="50">11</td>

   <td width="48">2</td>

   <td width="48">15</td>

   <td width="468">10</td>

  </tr>

  <tr>

   <td width="50">12</td>

   <td width="48">4</td>

   <td width="48">17</td>

   <td width="468">14</td>

  </tr>

 </tbody>

</table>

The output for this input file is given as follows for different maximum average waiting times. Please check your program with this input file as well as the others that you will create. Please note that we will use other input files when grading your assignments.













<h3><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="64000d0e0f17101605240c0b17100a050901">[email protected]</a>:~&gt;./simulator_Q1   patients.txt   5</h3>

<strong> </strong>

Minimum number of doctors required: 4




Simulation with 4 doctors:




Doctor 0 takes patient 2 at minute 1 (wait: 0 mins)

Doctor 1 takes patient 1 at minute 1 (wait: 0 mins)

Doctor 2 takes patient 3 at minute 1 (wait: 0 mins)

Doctor 3 takes patient 4 at minute 1 (wait: 0 mins)

Doctor 3 takes patient 5 at minute 6 (wait: 2 mins)

Doctor 2 takes patient 6 at minute 7 (wait: 0 mins)

Doctor 1 takes patient 8 at minute 11 (wait: 0 mins)

Doctor 0 takes patient 7 at minute 15 (wait: 6 mins)

Doctor 3 takes patient 11 at minute 16 (wait: 1 mins)

Doctor 2 takes patient 12 at minute 21 (wait: 4 mins)

Doctor 0 takes patient 9 at minute 25 (wait: 12 mins) Doctor 1 takes patient 10 at minute 25 (wait: 11 mins)




Average waiting time: 3.00 minutes

<strong> </strong>

<h3><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="cbafa2a1a0b8bfb9aa8ba3a4b8bfa5aaa6ae">[email protected]</a>:~&gt;./simulator_Q1   patients.txt   10</h3>




Minimum number of doctors required: 3




Simulation with 3 doctors:




Doctor 0 takes patient 2 at minute 1 (wait: 0 mins)

Doctor 1 takes patient 1 at minute 1 (wait: 0 mins)

Doctor 2 takes patient 3 at minute 1 (wait: 0 mins)

Doctor 2 takes patient 6 at minute 7 (wait: 0 mins)

Doctor 1 takes patient 8 at minute 11 (wait: 0 mins)

Doctor 0 takes patient 5 at minute 15 (wait: 11 mins)

Doctor 2 takes patient 12 at minute 21 (wait: 4 mins)

Doctor 0 takes patient 7 at minute 25 (wait: 16 mins)

Doctor 1 takes patient 11 at minute 25 (wait: 10 mins)

Doctor 0 takes patient 4 at minute 35 (wait: 34 mins)

Doctor 1 takes patient 9 at minute 35 (wait: 22 mins) Doctor 2 takes patient 10 at minute 35 (wait: 21 mins)




Average waiting time: 9.83 minutes




<h1>Question 2 – 25 points</h1>

In the previous question, there is 2000 limit for the number of patients. Now extend your program such that there is no such kind of limit. For that, first dynamically allocate an array with a size of 10 when you construct a heap. Then, double the size (i.e., extend the array by reallocating) if you exceed this number after an insertion. Likewise, halve the size (i.e., this time, shrink the array again by reallocating) if the number of items in the heap falls below the half of the allocated size after a deletion.

Put the class definition and implementation of this extended version in <strong>maxHeap2.h </strong>and <strong>maxHeap2.cpp</strong>, respectively. Use the same function names with the implementation that you use in the first question. So, you can use the same driver function given in <strong>simulator.cpp</strong>.

<a href="#_ftnref1" name="_ftn1">[1]</a> The file is a UNIX-style text file with the end-of-line denoted by a single 
 (ASCII 0x0A)