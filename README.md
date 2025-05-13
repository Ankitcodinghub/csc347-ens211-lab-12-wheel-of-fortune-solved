# csc347-ens211-lab-12-wheel-of-fortune-solved
**TO GET THIS SOLUTION VISIT:** [CSC347-ENS211 Lab 12-Wheel-of-Fortune Solved](https://www.ankitcodinghub.com/product/csc347-ens211-lab-12-wheel-of-fortune-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;94134&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC347-ENS211 Lab 12-Wheel-of-Fortune Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
&nbsp;

<strong>Objective </strong>

In this lab you will use a register and a counter to design a simple electric wheel of fortune game machine.

<strong>Introduction</strong>

The wheel of fortune you are designing works as follows. At the startup, the LED lights continuously rotate around using a bit pattern “00000001”, and at the same time the seven segment display continuously increments at a fast speed. The digit starts from 0000 and increments to FFFF and repeats. When a user presses a stop button, the LED rotation stops and the seven segment displays the number caught at the positive transition of the stop button press. When the user releases the button, it starts the whole process again, i.e., the LED lights rotates around, and the seven segment display increments the four digit hex number at a fast speed. The LED movements should be slow enough to be visible. However, the numbers on the seven segment display should be fast enough, so that it is hard to recognize except when it is stopped. In order to accomplish this, we need to create the following modules

&nbsp;

<ul>
<li><strong>A ring counter (or shift register) to rotate LEDs</strong></li>
<li><strong>A counter to increment number</strong></li>
</ul>
&nbsp;

The diagram of the system is shown below:

&nbsp;

<strong>Lab Procedure</strong>

&nbsp;

<ol>
<li><strong><u>Build an 8-bit ring counter</u></strong></li>
</ol>
A ring counter is a Shift Register (a cascade connection of flip-flops) with the output of the last flip flop connected to the input of the first. It is initialized such that only one of the flip flop output is 1 while the reminder is 0. The 1 bit is circulated so the state repeats every 8 clock cycles. Below is the circuit for an 8-bit ring counter. A skeleton of the Verilog description is provided, with some details missing. <strong><em>Your task is to fill in the blanks</em>.</strong>

module ring_counter(clk, reset, stop, direction, Q);

input clk, reset, stop, direction;

output [7:0] Q;

reg [7:0] Qtemp = 8’b00000001;

always @(posedge clk)

begin

if (reset == 1’b1)

Qtemp &lt;= 8’b00000001;

else if (stop == 1’b1)

Qtemp &lt;= 8’b00000001;

else if (direction == 1’b1)

Qtemp &lt;= {Qtemp[0],Qtemp[7:1]}; &nbsp; &nbsp;<em>//shifting right</em>

else

Qtemp &lt;= {Qtemp[6:0],Qtemp[7]}; &nbsp; &nbsp;<em>//shifting left</em>

end

assign Q = Qtemp;

endmodule

&nbsp;

<ol start="2">
<li><strong><u>Build a bidirectional (up/down) counter.</u></strong></li>
</ol>
Bidirectional counters, also known as Up/Down counters, are capable of counting in either up or down direction through any given count sequence and they can be reversed at any point within their count sequence by using an additional control input as shown below. Also the counter should have the functions to reset the count to zero, and stop counting. Again, a skeleton of the Verilog description of the counter is provided, with some details erased. <strong><em>Your task is to fill in the blanks</em></strong>.

&nbsp;

module counter(clk, reset, stop, direction, count);

input clk, direction; &nbsp;<em>// clock, direction for counting up or down &nbsp; &nbsp; &nbsp; </em>

input reset, stop;

output reg [3:0] count=0;

always @(posedge clk)

begin

if (reset == 1’b1)

count &lt;= 0; <em>// reset the counter</em>

else if (stop == 1’b1)

count &lt;= count; <em>// do nothing</em>

else if (direction == 1’b1)

count &lt;= count + 1; <em>// count up</em>

else

count &lt;= count – 1; <em>// count down</em>

end

endmodule

&nbsp;

<ol start="3">
<li><strong><u>Build top-level LED wheel of fortune</u></strong></li>
</ol>
Based on the diagram in the first page, write Verilog code to implement the wheel of fortune circuit. Once again, a skeleton of the Verilog description is provided, with some details erased. <strong><em>Fill in the blanks</em></strong> so your Verilog description exactly matches the circuit in the first page.

module wheeloffortune(clock, reset, stop, direction, LEDs, count);

input clock, reset, stop, direction;

output [7:0] LEDs;

output [3:0] count;

ring_counter U1(clock, reset, stop, direction, LEDs); &nbsp;<em>// instantiate the ring counter</em>

counter U2(clock, reset, stop, direction, count); &nbsp;<em>// instantiate counter</em>

endmodule

&nbsp;

<ol>
<li><strong>Testbench</strong>: create a Verilog testbench to test your wheel of fortune module and perform the simulation to check if it is working.</li>
<li>module test;</li>
<li>reg clock, reset, stop, direction; <em>// input</em></li>
<li>wire [7:0] LEDs; <em>// output</em></li>
<li>wire [3:0] count; <em>// output</em></li>
<li></li>
<li>wheeloffortune uut(clock, reset, stop, direction, LEDs, count); <em>// instantiate the module</em></li>
<li>&nbsp; &nbsp; &nbsp;initial</li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; begin</li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; clock = 0; <em>// start the simulation</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; forever &nbsp;#5 clock = ~clock; &nbsp;<em>// toggle clock</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; #500 $finish; &nbsp;<em>// stop the simulation</em></li>
<li>&nbsp; &nbsp; &nbsp;end</li>
<li></li>
<li>&nbsp; initial begin</li>
<li>&nbsp; &nbsp; &nbsp; $dumpfile(“dump.vcd”); $dumpvars(1, test); <em>// create a waveform file</em></li>
<li>&nbsp; &nbsp; &nbsp; $monitor( “stop= %b, LEDs = %b, count= %b”, stop, LEDs, count); &nbsp;<em>// print the outputs</em></li>
<li></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp;<em>// Initialize Inputs</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;reset = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// reset the circuit</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;stop = 0; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <em>// stop the simulation</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;direction = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// counting up</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#23 &nbsp;reset = 0; &nbsp; &nbsp; &nbsp; &nbsp; <em>// disable reset, start counting</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#80 &nbsp;stop = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// pause counting and light movement</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#20 &nbsp;stop = 0; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// resume counting and light movement &nbsp; </em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#20 direction =0; &nbsp; &nbsp; &nbsp; <em>// change direction of moving lights and couting</em></li>
<li></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#150 stop = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// pause counting and light movement</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#20 &nbsp;stop = 0; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// resume counting and light movement &nbsp; </em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#50 &nbsp;reset = 1; &nbsp; &nbsp; &nbsp; &nbsp; <em>// reset the circuit</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;#20 $finish; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// stop the simulation</em></li>
<li>&nbsp; &nbsp; &nbsp; &nbsp; end</li>
<li>endmodule</li>
<li></li>
</ol>
<strong><u>Submission Instructions:</u></strong>

<strong><u>&nbsp;</u></strong>

<u>Lab work submission</u>

<ol>
<li>Take a screenshot of your wavefroms.</li>
<li>Add the following information as comments to the beginning of your code. Make sure to click the “Save” button to save your project, then take a screenshot of your code.</li>
</ol>
// Author:&nbsp;&nbsp;&nbsp; Name

// Lab 12: &nbsp;Wheel-of-Fortune

// Link to your project

&nbsp;

<ol start="3">
<li>Copy the link of your design from the address bar of the browser.</li>
<li>On the Blackboard, click on Lab 12. Attach the screenshots from the first two steps and paste the link from Step 3 into the Comments area, then click the “Submit” button.</li>
</ol>
&nbsp;

<u>&nbsp;</u>

No report is needed for this lab.

&nbsp;

<a href="https://www.edaplayground.com/x/mtrR">https://www.edaplayground.com/x/mtrR</a>

&nbsp;

&nbsp;

<em>// Author: Gianna Rose</em>

<em>// Lab 12</em>

<em>// https://www.edaplayground.com/x/mtrR</em>

&nbsp;

module test;

reg clock, reset, stop, direction; <em>// input</em>

wire [7:0] LEDs; <em>// output</em>

wire [3:0] count; <em>// output</em>

&nbsp;

wheeloffortune uut(clock, reset, stop, direction, LEDs, count); <em>// instantiate the module</em>

initial

begin

clock = 0; <em>// start the simulation</em>

forever &nbsp;#5 clock = ~clock; &nbsp;<em>// toggle clock</em>

#500 $finish; &nbsp;<em>// stop the simulation</em>

end

&nbsp;

initial begin

$dumpfile(“dump.vcd”); $dumpvars(1, test); <em>// create a waveform file</em>

$monitor( “stop= %b, LEDs = %b, count= %b”, stop, LEDs, count); &nbsp;<em>// print the outputs</em>

&nbsp;

<em>// Initialize Inputs</em>

reset = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// reset the circuit</em>

stop = 0; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <em>// stop the simulation</em>

direction = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// counting up</em>

#23 &nbsp;reset = 0; &nbsp; &nbsp; &nbsp; &nbsp; <em>// disable reset, start counting</em>

#80 &nbsp;stop = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// pause counting and light movement</em>

#20 &nbsp;stop = 0; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// resume counting and light movement &nbsp; </em>

#20 direction =0; &nbsp; &nbsp; &nbsp; <em>// change direction of moving lights and couting</em>

&nbsp;

#150 stop = 1; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// pause counting and light movement</em>

#20 &nbsp;stop = 0; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// resume counting and light movement &nbsp; </em>

#50 &nbsp;reset = 1; &nbsp; &nbsp; &nbsp; &nbsp; <em>// reset the circuit</em>

#20 $finish; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<em>// stop the simulation</em>

end

endmodule

&nbsp;

&nbsp;

<em>// Author: Gianna Rose</em>

<em>// Lab 12</em>

<em>// https://www.edaplayground.com/x/mtrR</em>

&nbsp;

module ring_counter(clk, reset, stop, direction, Q);

input clk, reset, stop, direction;

output [7:0] Q;

&nbsp;

reg [7:0] Qtemp = 8’b00000001;

&nbsp;

always @(posedge clk)

begin

if (reset == 1’b1)

Qtemp &lt;= 8’b00000001;

else if (stop == 1’b1)

Qtemp &lt;= 8’b00000001;

else if (direction == 1’b1)

Qtemp &lt;= {Qtemp[0],Qtemp[7:1]}; &nbsp; &nbsp;<em>//shifting right</em>

else

Qtemp &lt;= {Qtemp[6:0],Qtemp[7]}; &nbsp; &nbsp;<em>//shifting left</em>

end

assign Q = Qtemp;

&nbsp;

endmodule

&nbsp;

module counter(clk, reset, stop, direction, count);

input clk, direction; &nbsp;<em>// clock, direction for counting up or down &nbsp; &nbsp; &nbsp; </em>

input reset, stop; &nbsp; <em>// reset, stop signal</em>

&nbsp;

output reg [3:0] count = 0; <em>// output register</em>

&nbsp;

always @(posedge clk)

begin

if (reset == 1’b1)

count &lt;= 0; <em>// reset the counter</em>

else if (stop == 1’b1)

count &lt;= count; <em>// do nothing</em>

else if (direction == 1’b1)

count &lt;= count + 1; <em>// count up</em>

else

count &lt;= count – 1; <em>// count down</em>

end

&nbsp;

endmodule

&nbsp;

module wheeloffortune(clock, reset, stop, direction, LEDs, count);

input clock, reset, stop, direction;

output [7:0] LEDs;

output [3:0] count;

&nbsp;

ring_counter U1(clock, reset, stop, direction, LEDs); &nbsp;<em>// instantiate the ring counter</em>

counter U2(clock, reset, stop, direction, count); &nbsp;<em>// instantiate counter</em>

endmodule

&nbsp;
