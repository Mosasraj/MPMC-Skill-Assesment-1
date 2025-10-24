# Skill-Assesment-1
# Assembly language program in 8051 to exchange the contents of two memory blocks of equal length.
# Aim:
To write and execute an assembly language program using the 8051 microcontroller that exchanges the contents of two memory blocks of equal length stored in internal RAM.
#Algorithm:
1.Start the program and initialize the data pointer registers.
2.Load the starting address of Block A into R0.
3.Load the starting address of Block B into R1.
4.Load the number of bytes (block length) into R2.
5.Perform the following steps for each byte:
  Move the data from Block A (pointed by R0) to Accumulator A.
  Store that value temporarily in R3.
  Move the data from Block B (pointed by R1) to Accumulator A.
  Copy this value to Block A (R0).
  Retrieve the original Block A value from R3 and store it in Block B (R1).
  Increment both R0 and R1 to point to the next byte.
  Decrement R2 until it becomes zero.
6.When R2 = 0, the data exchange is complete.
7.Stop the program.
# Program
ORG 0000H                      ; Program start address
    MOV R0, #30H               ; Pointer to start of Block A
    MOV R1, #40H               ; Pointer to start of Block B
    MOV R2, #02                ; Length of blocks (number of bytes to exchange)
EXCHANGE_LOOP:
    CJNE R2, #00H, SWAP_BYTES  ; If length is zero, exit loop
    SJMP END_PROGRAM           ; Jump to end if done
SWAP_BYTES:
    MOV A, @R0                 ; Load byte from Block A into A
    MOV R3, A                  ; Store in temporary register R3
    MOV A, @R1                 ; Load byte from Block B into A
    MOV @R0, A                 ; Store Block B's byte into Block A
    MOV A, R3                  ; Retrieve original Block A's byte
    MOV @R1, A                 ; Store it into Block B
    INC R0                     ; Increment pointer for Block A
    INC R1                     ; Increment pointer for Block B
    DEC R2                     ; Decrement length counter
    SJMP EXCHANGE_LOOP         ; Repeat loop
END_PROGRAM:
END
# Output

<img width="900" height="500" alt="1 1" src="https://github.com/user-attachments/assets/6c77fbf8-9b22-489a-9a63-cbe5f81e9a67" />
<img width<img width="900" height="500" alt="1 2" src="https://github.com/user-attachments/assets/c3ade911-bcb8-436f-8462-4b461bfd0201" />

# Result
The program successfully exchanges the contents of two memory blocks of equal length using the 8051 microcontroller.
