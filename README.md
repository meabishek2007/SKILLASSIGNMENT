SKILL ASSIGNMENT-1

PROGRAM:
Write an assembly language program in 8086 to search for a given number in an array of N elements and display whether the number is found or not found.

APPARATUS REQUIRED:

LAPTOP WITH KEIL SOFTWARE

PROGRAM:
```
DATA SEGMENT
    ARR DB 12, 45, 23, 56, 78, 90, 34
    N   DB 7
    NUM DB 56
    MSG1 DB 0DH,0AH,'NUMBER FOUND$'
    MSG2 DB 0DH,0AH,'NUMBER NOT FOUND$'
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA

START:
    MOV AX, DATA
    MOV DS, AX
    MOV CL, N
    LEA SI, ARR
    MOV AL, NUM

SEARCH_LOOP:
    CMP AL, [SI]
    JE FOUND
    INC SI
    DEC CL
    JNZ SEARCH_LOOP

NOT_FOUND:
    LEA DX, MSG2
    JMP DISPLAY

FOUND:
    LEA DX, MSG1

DISPLAY:
    MOV AH, 09H
    INT 21H
    MOV AH, 4CH
    INT 21H

CODE ENDS
END START

```
OUTPUT:

<img width="638" height="431" alt="Screenshot 2025-10-27 201543" src="https://github.com/user-attachments/assets/4860002c-a014-4765-b695-cfafbe9b78f5" />
<img width="635" height="428" alt="Screenshot 2025-10-27 201614" src="https://github.com/user-attachments/assets/c2b9a1f7-5be8-4d69-8998-b9818380da1c" />
<img width="636" height="427" alt="Screenshot 2025-10-27 201340" src="https://github.com/user-attachments/assets/24ef393d-a339-4661-9fcf-29f3cf48aebd" />


RESULT:
Thus the program to search for a given number in an array of N elements and display whether the number is found or not found.


