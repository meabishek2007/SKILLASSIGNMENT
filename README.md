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
<img width="1919" height="1199" alt="Screenshot 2025-10-27 195106" src="https://github.com/user-attachments/assets/40923220-b18d-4a74-9a53-930b369de890" />
<img width="1919" height="1195" alt="Screenshot 2025-10-27 195046" src="https://github.com/user-attachments/assets/424e419d-74f8-40e4-aaa3-b12ec9127a4b" />



RESULT:

Thus the program to generate a 1 second delay using Timer 1 in Mode 1 and toggle all bits of Port 1 continuouslyIS executed.
