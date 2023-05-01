Download Link: https://assignmentchef.com/product/solved-cda46305636-project-2
<br>
<span class="kksr-muted">Rate this product</span>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

In this project, you need to implement both code compression and decompression using C, C++ or Java. Assume that the dictionary can have eight entries (index 3 bits) and the eight entries are selected based on frequency (the most frequent instruction should have index 000). If two entries have the same frequency, the priority should be given to the one that appears first in the original program order. The original code consists of 32-bit binaries. You are allowed to use only the following seven possible formats for compression. Note that if one entry (32-bit binary) can be compressed in more than one way, choose the most beneficial one i.e., the one that provides the shortest compressed pattern. If two formats produce exactly the same compression, choose the one that appears earlier in the following listing (e.g., run-length encoding appears earlier than direct matching). Also, if there is a scenario where you have two possible ways of applying bitmasks to a 32- bit binary, always give preference to the scenario where the leftmost bit ‘1’ for the bitmask pattern (e.g., 11 is preferred over 01). Please count the starting location of a mismatch from the leftmost (MSB) bit of the pattern – the position of the leftmost bit is 00000.

Format of the Run Length Encoding (RLE)Format of bitmask-based compression – starting location is counted from left/MSB

Format of the 1 bit Mismatch – mismatch location is counted from left/MSBFormat of the 2 bit consecutive mismatches – starting location is counted from left/MSBFormat of the 2 bit mismatches anywhere – Mismatch locations (ML) are counted from left/MSB Format of the Direct MatchingFormat of the Original Binaries

Run-Length Encoding (RLE) can be used when there is consecutive repetition of the same instruction. The first instruction of the repeated sequence will be compressed (or kept uncompressed if it is not part of the dictionary) as usual. The remaining ones will be compressed using RLE format shown above. The two bits in the RLE indicates the number of occurrences (00, 01, 10 and 11 imply 1, 2, 3 and 4 occurrences, respectively), excluding the first one. A single application of RLE can encode up to 4 instructions. Assume

000

Run Length Encoding (2 bits)

001

Starting Location (5 bits)

Bitmask (4 bits)

Dictionary Index (3 bits)

010

Mismatch Location (5 bits)

Dictionary Index (3 bits)

011

Starting Location (5 bits)

Dictionary Index (3 bits)

100

1st ML from left (5 bits)

2nd ML from left (5 bits)

Dictionary Index (3 bits)

101

Dictionary Index (3 bits)

110

Original Binary (32 bits)

that the longest sequence can be at most 5 repeating instructions (the first one using other formats and the last 4 using RLE). Note that, RLE should be used when it is profitable compared to other available options.

You are expected to implement the compression and decompression functions using C, C++ or Java. You need to show a working prototype that will take any 32-bit binary (0/1 text) file and compress it to produce an output file that shows compressed patterns arranged in a sequential manner (32-bit in each line, last line padded with 1’s, if needed), a separation marker “xxxx”, followed by eight dictionary entries. Your program should also be able to accept a compressed file (in the above format) and decompress to generate the decompressed (original) patterns. Please see the sample files posted in the webpage to avoid any confusion.

Command Line and Input/Output Formats: The simulator should be executed with the following command line. Please use parameters “1” and “2” to indicate compression, and decompression, respectively.

./SIM 1 (or java SIM 1) for compression ./SIM 2 (or java SIM 2) for decompression

Please hardcode the input and output files as follows:

<ol>

 <li>Input file for your compression function: original.txt</li>

 <li>Output produced by your compression function: cout.txt</li>

 <li>Input file for your decompression function: compressed.txt</li>

 <li>Output produced by your decompression function: dout.txt</li>

</ol>

Submission Policy:Please follow the submission policy outlined below. There will be up to 10% score penalty based on the

nature of submission policy violations.

<ol>

 <li>Please submit only one source file that includes both compression and decompression. Please add “.txt” at the end of your filename. Your file name must be SIM (e.g., SIM.c.txt or SIM.cpp.txt or SIM.java.txt). On top of the source file, please include the sentence: “/* On my honor, I have neither given nor received unauthorized aid on this assignment */”.</li>

 <li>Please test your submission. These are the exact steps that we will follow to grade your submission.</li>

</ol>

o Download your submission from eLearning (ensures your upload was successful). o Remove “.txt” extension (e.g., SIM.c.txt should be renamed to SIM.c)

o Login to storm.cise.ufl.edu. If you don’t have a CISE account, go to http://cise.ufl.edu/help/account.shtml and apply for one CISE class account. Then you use putty and winscp or other tools to login and transfer files.

o Please compile to produce an executable named SIM.§ gcc SIM.c –o SIM or javac SIM.java or g++ SIM.cpp –o SIM or

g++ -std=c++0x SIM.cpp -o SIM o Please do not print anything on screen.

o Assume hardcoded input/output files as outlined in the project description.o Compress the input file (original.txt) and check with the expected output (compressed.txt)

§ ./SIM 1 (or java SIM 1)§ diff –w –B cout.txt compressed.txt

o Decompress the input file (compressed.txt) and check with the expected output (original.txt) § ./SIM 2 (or java SIM 2)

§ diff –w –B dout.txt original.txt

<ol start="3">

 <li>In previous years, there were many cases where output format was different, filename was different, command line arguments were different, or e-Learning submission was missing. All of these led to un- necessary waste of time for TA, instructor and students. Please use the exactly same commands as outlined above to avoid 10% score penalty.</li>

 <li>You are not allowed to take or give any help in completing this project. In previous years, some students violated academic honesty (giving help or taking help in completing this project). We were able to establish cheating in several cases – those students received “0” in the project and their names were reported to UF Dean of Students Office. This time we will have double penalty for cheating.</li>