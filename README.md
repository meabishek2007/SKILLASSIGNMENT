SKILL ASSIGNMENT-2

PROGRAM:
Write an assembly language program in 8051 to generate a 1 second delay using Timer 1 in Mode 1 and toggle all bits of Port 1 continuously.

APPARATUS REQUIRED:

LAPTOP WITH KEIL SOFTWARE

PROGRAM:
```
ORG 0000H

MAIN:   MOV P1,#0FFH
        MOV TMOD,#10H

HERE:   ACALL DELAY
        MOV A,P1
        CPL A
        MOV P1,A
        SJMP HERE

DELAY:  MOV R2,#20
AGAIN:  ACALL DELAY50
        DJNZ R2,AGAIN
        RET

DELAY50: MOV TH1,#3CH
         MOV TL1,#0B0H
         SETB TR1
WAIT50:  JNB TF1,WAIT50
         CLR TR1
         CLR TF1
         RET

END
```
OUTPUT:
<img width="1919" height="1199" alt="Screenshot 2025-10-27 195106" src="https://github.com/user-attachments/assets/c6c7af6c-b4ed-43b6-bda0-7e6237023d25" />
<img width="1919" height="1195" alt="Screenshot 2025-10-27 195046" src="https://github.com/user-attachments/assets/536e257e-a777-4f6f-a5a9-b52a356177e4" />


RESULT:

Thus the program to generate a 1 second delay using Timer 1 in Mode 1 and toggle all bits of Port 1 continuously.

