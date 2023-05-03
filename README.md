Download Link: https://assignmentchef.com/product/solved-cs207-assignment1-digital-design-theory
<br>
<h2>PART 1: DIGITAL design THEORY</h2>

Provide answers to the following questions:

<ol>

 <li>List the octal and hexadecimal numbers from 12 to 28. Using A, B, C and D for the last four digits, list the numbers from 12 to 28 in base 14.</li>

 <li>What is the largest signed and unsigned binary number that can be expressed with 14 bits? What are the equivalent decimal and hexadecimal numbers?</li>

 <li>Convert the decimal number 240 to binary in two ways: (a) convert directly to binary; (b) convert first to hexadecimal and then from hexadecimal to binary. Which method is faster?</li>

 <li>Describe the three basic types of logic calculation (write the truth table).</li>

 <li>Give the 1s’ and 2s’ complement code of the following decimal numbers, the answer should be 32 bit-width in hexadecimal notation.</li>

 <li>14274836</li>

 <li>-27854048</li>

</ol>

<h2>PART 2: DIGITAL design lab</h2>

<h5>Introduction</h5>

In this lab, you are required to use Vivado 2017.4 and Minisys Practice platform (xilinx FPGA chip artix 7 inside) to design a simple logic circuit: Do the addition on two unsigned 2bit numbers, do the simulation and verify its function on the board. You should submit the description of the operation steps, the Verilog design, the wave form from the simulation, and the on board testing steps and results.

<h5>Preamble</h5>

Before working on the coursework itself, you should master the following material. A separate tutorial document (on the Sakai site) has be provided to you which includes:

<ul>

 <li>Vivado: The Vivado software provides a complete design environment for system-on-a-programmable-chip (SOPC) design. Regardless of whether you use a personal computer or a Linux workstation, Vivado ensures easy design entry, fast processing, and straightforward device programming.</li>

 <li>Minisys Practice platform: a platform designed for Digital design ,Principles of Computer Organization and many other courses. This platform include FPGA chip ,storage chip and lots of Dial switches, LEDs for input and output.</li>

 <li>Verilog : standardized as IEEE 1364, is a <a href="https://en.wikipedia.org/wiki/Hardware_description_language">hardware description language</a>(HDL) used to model <a href="https://en.wikipedia.org/wiki/Electronic_system">electronic systems</a>. It is most commonly used in the <a href="https://en.wikipedia.org/w/index.php?title=Design_and_verification&amp;action=edit&amp;redlink=1">design and verification</a> of <a href="https://en.wikipedia.org/wiki/Digital_electronics">digital circuits</a> at the <a href="https://en.wikipedia.org/wiki/Register-transfer_level">register-transfer level</a> of <a href="https://en.wikipedia.org/wiki/Abstraction_(computer_science)">abstraction</a>. It is also used in the verification of <a href="https://en.wikipedia.org/wiki/Analogue_electronics">analog circuits</a> and <a href="https://en.wikipedia.org/wiki/Mixed-signal_integrated_circuit">mixed-signal circuits</a>, as well as in the design of <a href="https://en.wikipedia.org/w/index.php?title=Genetic_circuit&amp;action=edit&amp;redlink=1">genetic circuits</a>. http://www.verilog.com/</li>

</ul>

<h5>Exercise specification</h5>

<strong>TASK1: </strong>

Create a project named as Lab2_Addition, design the source code to get the addition of two input numbers: one is 2bit and another is 1bit. do the simulation and generate the bitstream which is used to program the FPGA chip and verify your design.




Note: there should be two inputs (we need input two operands through dial switch) and three outputs (three led groups needed to demonstrate the value of two operands and the result)

<strong><em>module </em></strong><em>Lab2_Addition(addend, augend, addend_led, augend_led, sum_led);</em>

<em>input [1:0] addend;</em>

<em>input augend;</em>

<em>output [1:0]addend_led;</em>

<em>output augend_led;</em>

<em>output [2:0] sum_led;</em>

<em>……</em>

<strong><em>endmodule</em></strong>

You will focus on how to use Vivado to do the design, simulation, generate the bitstream file which is used to program the FPGA chip (a part of the Minisys practice platform), you will also learn some basic concepts of Verilog. The steps you need to follow are:

<ol>

 <li>Create an empty project.</li>

 <li>Edit a design file (Verilog file) &amp; add it to the project.</li>

 <li>Edit a simulation file (Verilog file) &amp; add it to the project.</li>

 <li>Do the simulation using to verify if the function of design is ok. If not, modify your design and do the simulation again.</li>

 <li>Do the synthesize.</li>

 <li>Edit a constraints file (to define the Specifications of pins and the binding info between pins and the designed ports) &amp; add it to the project.</li>

 <li>Do the implementation.</li>

 <li>Generate the bitstream file.</li>

 <li>Turn on the board (Minisys &amp; FPGA chip inside) and connect Vivado to the board</li>

 <li>Program the device with the bitstream</li>

 <li>Test the design on the board (using dial switch as input, using led to see the state of output)</li>

</ol>




<strong>TASK2: </strong>

<ul>

 <li>Do the design using data flow, block style and structured style respectively (While doing the design with structured style, It is optional to use primitive or encapsulated IP) to verify the following theorem (you can find the design on the lab3 and lab4 courseware as a reference):</li>

</ul>

<strong>DeMorgan</strong>:  a) <strong>(x+y)’ = x’y’ </strong>        b) <strong>(xy)’ = x’+y’</strong>

<ul>

 <li>Create a test bench, do the simulation to verify the function of the design.</li>

 <li>Edit a constraints file (to define the Specifications of pins and the binding info between pins and the designed ports) &amp; add it to the project.</li>

 <li>Do the synthesis and implementation.</li>

 <li>Generate bitstream file, program the device with the bitstream</li>

 <li>Test the design on the board (using dial switch as input, using led to see the state of output).</li>

</ul>




<strong>TIPS: </strong>

<ul>

 <li>Putting all the circuit ( (x+y)’ , x’y’ ,(xy)’ and x’+y’) to one design file, and naming ports in different design file(corresponding to the different design style) with same name so that you can reuse the testbench file and constraint file with just a little modification (as in labs courseware, just modify the module name in your design file).</li>

 <li>Naming the file:

  <ol>

   <li>For data flow design, the source file should be v</li>

   <li>For block design, source file should be bd</li>

   <li>For structured design, the source file should be v</li>

  </ol></li>

 <li>All the 3 design could share the same test bench file because the number and name of ports are same while only name of module are If you want use test bench file of demorgan_df.v on demorgan_bd.bd ,just change the module name from demorgan_df to demorgan_bd is enough.</li>

 <li>All the 3 design could also share the same constrain file because the number and name of ports are the</li>

</ul>

<h5></h5>

PART 1: DIGITAL design THEORY

Provide your answers here:

PART 2: DIGITAL design LAB (Task1)

<h5>Design</h5>

<em>Describe the design of your system by providing the following information:</em>

<ul>

 <li><em>Verilog design (provide the Verilog code)</em></li>

 <li><em>Truth-table</em></li>

</ul>

<h5>simulation</h5>

<em>Describe how you build the test bench and do the simulation. </em>

<ul>

 <li><em>Using Verilog(provide the Verilog code)</em></li>

 <li><em>Wave form of simulation result (provide screen shots)</em></li>

 <li><em>The description on whether the simulation result is same as the truth-table, is the function of the design meet the expectation.</em></li>

</ul>

<h5>Constraint file and the testing</h5>

<em>Describe how</em><em> you </em><em>test your design on the Minisys Practice platform. </em>

<ul>

 <li><em>Constraint file (provide the screen shots on the feature of a pin and the binding info between pins and the input /output ports)</em></li>

 <li><em>The testing result (provide the screen shots (at least 3 testing scene) to show state of inputs and outputs along with the related descriptions.</em></li>

</ul>

<h5>the description of operation</h5>

<em>Describe the problem occurred while in the lab and your solution. Any suggestions are welcomed.</em>

<ul>

 <li><em>Problems</em><em> and solutions</em></li>

</ul>

PART 2: DIGITAL design LAB (Task2)

<h5>Design</h5>

<em>Describe the design of your system by providing the following information:</em>

<ul>

 <li><em>Verilog design while using data flow (provide the Verilog code)</em></li>

 <li><em>Verilog design while using structured design (provide the Verilog code)</em></li>

 <li><em>Block design (provide screen shots)</em></li>

 <li><em>Truth-table</em></li>

</ul>

<h5>simulation</h5>

<em>Describe how you build the test bench and do the simulation. </em>

<ul>

 <li><em>Using Verilog (provide the Verilog code)</em></li>

 <li><em>Wave form of simulation result (provide screen shots)</em></li>

 <li><em>The description on whether the simulation result is same as the truth-table, is the function of the design meet the expectation</em></li>

</ul>

<h5>Constraint file and the testing</h5>

<em>Describe how</em><em> you </em><em>test your design on the Minisys Practice platform. </em>

<ul>

 <li><em>Constraint file (provide the screen shots on the feature of a pin and the binding info between pins and the input /output ports)</em></li>

 <li><em>The testing result (provide the screen shots (at least 3 testing scene)) to show state of inputs and outputs along with the related descriptions. </em></li>

</ul>

<h5>the description of operation</h5>

<em>Describe the problem occurred while in the lab and your solution. Any suggestions are welcomed.</em>

<ul>

 <li><em>Problems</em><em> and solutions</em></li>

</ul>

<em> </em>