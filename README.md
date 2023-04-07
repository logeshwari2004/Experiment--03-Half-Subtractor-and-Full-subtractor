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
### STEP 1:
Use module projname(input,output) to start the Verilog programmming.

### STEP 2:
Assign inputs and outputs using the word input and output respectively.

### STEP 3:
Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

### STEP 4:
Use each output to represnt onre for differnce and the other for borrow.

### STEP 5:
End the verilog program using keyword endmodule.

Write the detailed procedure here 
## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: LOGESHWARI.P
RegisterNumber: 212221230055
/*
```
Half Subtractor :

module ex3(A,B,Difference,Borrow);
input A,B;
output Difference,Borrow;
wire X;
xor(Difference,A,B);
not(X,A);
and(Borrow,X,B);
endmodule

Full Subtractor:

module ex3(A,B,C,Difference,Borrow);
input A,B,C;
output Difference,Borrow;
assign Difference = A^B^C;
assign Borrow = ~A & (B^C) | B & C;
endmodule
```
## Output:
### Half Subtractor
### Truthtable
![DE4D](https://user-images.githubusercontent.com/94211349/230613172-cd34e24b-f13f-4856-a878-d93bcdf75473.png)

### RTL realization
![DE4E](https://user-images.githubusercontent.com/94211349/230613211-ae534a96-e201-4a10-b292-2f4ac2f4dfdf.png)

### Timing diagram 
![DE4F](https://user-images.githubusercontent.com/94211349/230613254-501aeafe-0a3c-4766-b3c3-8be7463b02a7.png)

## Full Subtractor
### Truthtable
![DE4H](https://user-images.githubusercontent.com/94211349/230613599-7c8e57bd-b627-45cd-b7df-ebd2c0ce8a69.png)

### RTL realization
![DE4I](https://user-images.githubusercontent.com/94211349/230613605-f3424ce1-3567-4b59-a992-64c0b127be67.png)

### Timing diagram
![DE4J](https://user-images.githubusercontent.com/94211349/230613622-ccc41ea1-2653-4c7d-b0a4-f6745cf6b86c.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
