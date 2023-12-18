# Experiment  03:Half Subtractor and Full subtractor
## Implementation of Half subtractor and Full subtractor circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y
### Procedure
Connect the supply (+5V) to the circuit Switch ON the main switch If the output is 1, then the led glows.
## Program:
```
module HalfSubstractor (a,b,diff,borrow);
input a,b;
output diff,borrow;
xor (diff,a,b);
and (borrow,~a,b);
endmodule
```
## Truth Table
![Screenshot 2023-12-18 132657](https://github.com/Prajin19/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979377/fc821c8d-e104-446f-9bfa-f195d2025e32)

## RTL Realization
![Screenshot 2023-12-18 111552](https://github.com/Prajin19/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979377/d6eef09b-5cb3-4346-acb5-36c9a83205bf)
## Timing Diagram
![Screenshot 2023-12-18 112054](https://github.com/Prajin19/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979377/c0fd5dc2-fddf-478b-ae2c-7a6687ab6ad7)


## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
Connect the supply (+5V) to the circuit Switch ON the main switch If the output is 1, then the led glows.
## Program:
```
module FullSubstractor(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
xor(diff,a,b,c);
assign borrow=~a&b|c&~(a^b);
endmodule
```

## Truth Table
![Screenshot 2023-12-18 133231](https://github.com/Prajin19/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979377/63f78848-e446-4df9-b53e-099ed02cbc7e)

##  RTL realization
![Screenshot 2023-12-18 130942](https://github.com/Prajin19/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979377/30fe9221-3f5b-467e-84ed-697da4d9e9b4)


## Timing diagram 
![Screenshot 2023-12-18 131319](https://github.com/Prajin19/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979377/ed56c6e0-74ed-4592-b303-3c69e744864d)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
