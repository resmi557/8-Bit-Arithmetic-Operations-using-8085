# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
```
CMC
LDA 4200H
MOV B, A
LDA 4201H
ADD B
STA 4300H
JC STORE_CARRY
HLT
STORE_CARRY:MVI A,01H
STA 4301H
HLT
```




### Output:
<img width="1881" height="868" alt="Screenshot 2025-08-24 170056" src="https://github.com/user-attachments/assets/ad10d8bf-ac1d-4bfc-8142-c54bb01407cc" />

<img width="1894" height="865" alt="Screenshot 2025-08-24 170203" src="https://github.com/user-attachments/assets/ea1bb720-95c1-41dd-ae62-f661245abe5c" />

### Manual Calculation:
![image 1](https://github.com/user-attachments/assets/6459dc39-acbc-45f8-ac6f-ac01cdab37b8)





### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
CMP C
JC SWAP
MOV B,A
MOV A,C
SWAP: SUB B
STA 4300H
HLT
```

### Output:
<img width="1892" height="859" alt="Screenshot 2025-08-24 192533" src="https://github.com/user-attachments/assets/ace35619-c1f2-4797-b6ee-668d4d9c3c1b" />

<img width="1891" height="848" alt="Screenshot 2025-08-24 192555" src="https://github.com/user-attachments/assets/8d1bd122-94e9-4ce3-95ce-aa3a8003ab2a" />

### Manual calculation:
![image 2](https://github.com/user-attachments/assets/8618b805-c327-4066-b48e-8e7c86d94b97)






### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
MOV B,A
MVI A, 00H
LOOP: ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```



### Output:
<img width="1886" height="865" alt="Screenshot 2025-08-25 141755" src="https://github.com/user-attachments/assets/5af2eba1-25b1-4907-be1b-a3f185a31e22" />

<img width="1890" height="852" alt="Screenshot 2025-08-25 141814" src="https://github.com/user-attachments/assets/660ff6db-f44e-49b7-a409-5e3c1b72df25" />





### Manual calculation:

![IMAGE 4](https://github.com/user-attachments/assets/5dad615c-d963-4dc4-b9bd-8aa751833178)



### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
MOV B,A
MVI A,00H
LOOP:MOV A, C
CMP B
JC END
SUB B
MOV C, A
INR D
JMP LOOP
END: MOV A, D
STA 4300H
MOV A, C
STA 4301H
HLT
```


### Output:
<img width="1880" height="873" alt="Screenshot 2025-08-22 160448" src="https://github.com/user-attachments/assets/33fff56e-ecc3-4a16-ad2e-3158ffba32e4" />

<img width="1881" height="858" alt="Screenshot 2025-08-22 160617" src="https://github.com/user-attachments/assets/eb04c6f4-d13f-4d67-a945-ee41e2984257" />

### Manual calculation:
![IMAGE 3](https://github.com/user-attachments/assets/af9d7e91-c5a6-4f86-b1c8-7431e001d77e)



## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

