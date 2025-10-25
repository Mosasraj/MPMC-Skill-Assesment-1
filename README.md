# Skill-Assesment-1
# Find Smallest Number in an Array Using 8086 Assembly (MASM)
# Aim:
To write an 8086 assembly language program using MASM that finds the smallest number in a given array of N elements and displays it on the screen.
## Apparatus / Software Required:
1.MASM 8086 Assembler

2.LINK.EXE (MASM Linker)

3.DOSBox (to run MASM programs)

4.Windows PC
## Algorithm:
1.Start the program 

2.Initialize the data segment and load the array of numbers.

3.Assume the first element as the smallest number.

4.Compare each element of the array with the current smallest.

5.Update the smallest number if a smaller value is found.

6.Store the smallest number in a memory location.

7.Display the smallest number on the screen using DOS interrupt INT 21H.

8.Exit the program cleanly using DOS interrupt INT 21H.

9.Stop the program.
# Program
```asm
DATA SEGMENT
    ARR DB 5, 6, 9, 8, 7    ; Array elements
    N   DB 5                     ; Number of elements
    SMALL DB ?                   ; To store smallest number
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA

START:
    MOV AX, DATA
    MOV DS, AX

    MOV CL, N
    LEA SI, ARR
    MOV AL,[SI]
    INC SI
    DEC CL

NEXT_ELEMENT:
    CMP AL,[SI]
    JBE SKIP_UPDATE
    MOV AL,[SI]
SKIP_UPDATE:
    INC SI
    DEC CL
    JNZ NEXT_ELEMENT

    MOV SMALL, AL

    ; Display smallest number
    MOV DL, SMALL
    ADD DL, 30H
    MOV AH, 02H
    INT 21H

    ; Exit program
    MOV AH, 4CH
    INT 21H

CODE ENDS
END START

```
# Output
<img width="605" height="422" alt="image" src="https://github.com/user-attachments/assets/4f9b0cb4-590f-4f7a-adf2-4c887bad54db" />


![WhatsApp Image 2025-10-25 at 11 05 52_ac6f55ae](https://github.com/user-attachments/assets/2a93c385-9a41-4208-bd94-c8d95ee243a6)

# Result
The program successfully Find Smallest Number in an Array Using 8086 Assembly (MASM).
