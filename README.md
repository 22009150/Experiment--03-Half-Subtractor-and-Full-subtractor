# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
\STEP 1: Use module project name(input,output) to start the Verilog programmming.

STEP 2: Assign inputs and outputs using the word input and output respectively.

STEP 3: Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

STEP 4: Use each output to represnt onre for differnce and the other for borrow.

STEP 5: End the verilog program using keyword endmodule


## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: Archana.k

RegisterNumber:  212222240011
*/
# Half Subtractor:
```
module EX04(a,b,difference,borrow);
input a,b;
output difference,borrow;
wire x;
xor (difference,a,b);
not (x,a);
and (borrow,x,b);
endmodule
```
# Full subtractor:
```
module FullSub04(a,b,bin,difference,borrow);
input a,b,bin;
output difference,borrow;
wire p;
assign difference=((a^b)^bin);
not (p,a);
assign borrow=((p&b)|(p&bin)|(b&bin));
endmodule
```
## Output:
# Half Subtractor

![266498403-f32a9100-1e29-4929-aaae-947cd6cf8e8f](https://github.com/22009150/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118708624/c6ce8b3b-b4f4-4928-a3f4-454917850d39)

# Full Subtractor

![266495417-c83c5fad-8cf5-4a2a-99b8-606575ead6f7](https://github.com/22009150/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118708624/25a3f316-74ae-4948-a7de-89d9c23d3dd4)


## Truthtable
Half Subtractor

![Untitled](https://github.com/22009150/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118708624/a0c1cbae-6352-4b00-beef-b5546fb528f8)

Full Subtractor

![Untitled](https://github.com/22009150/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118708624/0ec7d598-b1fa-42ae-8b9c-ad625748d364)


## Timing diagram 
# Half Subtractor

![266497843-95fadd91-9046-4282-85cc-ecc973b65c24](https://github.com/22009150/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118708624/06356465-b18a-4844-8a67-014de40bb45b)

# Full Subtractor

![266497979-b91e4493-c685-4db8-89db-e4104131ef4c](https://github.com/22009150/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118708624/42a8264f-0ab4-4a52-b716-c8692c03723b)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
