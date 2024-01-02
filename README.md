
# NAME: RAMYA.P
# REFERENCE NO:21223240137

# Experiment--04-Half-Subtractor-and-Full-subtractor
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

# PROGRAM:
     module project_4_1(a,b,borrow,diff);
     input a,b;
     output borrow,diff;
     assign borrow=~a&b;
     assign diff=a^b;
     endmodule
# RTL realization:


![291255631-24c991b9-2505-4e57-b23a-bc8d29030589](https://github.com/23014107/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/151625620/51d3d989-34b8-48ae-b202-c47dfea1912d)


# Truth table:
![291255700-bbe4f57d-e237-4d64-8829-d5f1d8eb7259](https://github.com/23014107/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/151625620/26e48f71-1ce3-4c14-98a1-8b0977228306)


# Timing diagram:
![291255810-452cb7d7-303b-4e75-8c5e-9c6d9a074c99](https://github.com/23014107/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/151625620/8b856650-dbce-452a-af66-5c427215005a)



## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin



## Program:
 
    module project_4_2(a,b,bin,borrow,diff);
    input a,b,bin;
    output diff,borrow;
    assign diff=(a^b)^bin;
    assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
    endmodule
    
# RTL REALIZATION:

![291256368-8a12efe3-c86e-4800-a68f-c70a7befe09e](https://github.com/23014107/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/151625620/5750bd6f-6697-4d45-b5d7-9dc2c46a7529)

# TRUTH TABLE:

![291256384-531e58ee-f0b6-4146-b10e-5116dcf5f12f](https://github.com/23014107/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/151625620/838aefe2-dc9c-4e16-b6a2-9fee56dd5b58)

# TIMING DIAGRAM:

![291256418-37e4998a-532a-4fd5-9411-3c5447e13330](https://github.com/23014107/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/151625620/68a28b07-158e-4de3-9a93-fc61ae581769)

# RESULT:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
