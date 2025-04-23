# Coal-Lab-Tasks
*******LAB 2*******
Task no 1:

1.	Describe the function of each:
•	Accumulator Register (A, AX, EAX, RAX)
•	Base Register (B, BX, EBX, RBX)
•	Count Register (C, CX, ECX, RCX)
•	Data Register (D, DX, EDX, RDX)

1: Accumulator Register
•	The Accumulator Register is used to store the results of arithmetic and logical operations. It's also used to hold operands for these operations. In other words, it's a temporary storage location for data being processed.
•	Base Register (B, BX, EBX, RBX)
•	Points to a memory location
•	It stores the addresses of the data that is stored in the RAM
•	Used for data transfer between memory and registers
         BX: Extended to 16 bits
         EBX: Extended to 32 bits
         RBX: Extended to 64 bits
       Count Register (C, CX, ECX, RCX)
•	Keeps track of loop iterations
•	Used for counting and looping operations
•	Controls the number of repetitions

Data Register (D, DX, EDX, RDX)
•	Stores temporary data
•	Used for data transfer between registers and memory
•	Holds data for arithmetic and logical operations


2:Describe the role of index registers in source and destination operations. Provide an example using SI and DI in an assembly instruction
 
Role of Index Registers
Hold memory addresses
Help transfer data between memory and registers
Support array operations

Example: SI and DI Registers
MOV AL, [SI] (Copy byte from source array)
MOV [DI], AL (Copy byte to destination array)

SI: Holds source array address
DI: Holds destination array address
AL: Temporarily holds the byte being copied

3: Briefly describe the functions of these bits:
•	Overflow Flag (OF)
•	Zero Flag (ZF)
•	Carry Flag (CF)

Overflow Flag (OF): The Overflow Flag (OF) is set to 1 when the result of an arithmetic operation exceeds the maximum value that can be represented by the register. This indicates that the result has "overflowed" and lost its most significant bit.
Zero Flag (ZF): The Zero Flag (ZF) is set to 1 when the result of an arithmetic or logical operation is zero. This flag is used to test for equality or to check if a register contains a zero value.
Carry Flag (CF): The Carry Flag (CF) is set to 1 when the result of an arithmetic operation generates a carry-out from the most significant bit. This flag is used to indicate that a carry has occurred, and it's often used in multi-byte arithmetic operations

4:Write a simple program using MOV, ADD, and SUB instructions:
•	Move values to registers
•	Perform addition and subtraction
•	Store and display results

MOV AX, 8    ; Move 8 to AX
MOV BX, 5    ; Move 5 to BX
ADD AX, BX   ; Add BX to AX (AX = 13)
SUB AX, 6    ; Subtract 6 from AX (AX =7 )
MOV DX, 7   ; Store 7 in DX
********LAB 3*********
TASK !:
Code:
;To display single character  
org 100h
.data
.code 
main proc
      mov dl,'N'
      mov ah,2h
      INT 21H
main endp
end main
TASK 2:
Code:

;To display Name
org 100h
.data
.code 
main proc
      mov dl,'N'
      mov ah,2h
      INT 21H 
      mov dl,'A'
      mov ah,2h
      INT 21H
      mov dl,'Y'
      mov ah,2h
      INT 21H
      mov dl,'A'
      mov ah,2h
      INT 21H
      mov dl,'B'
      mov ah,2h
      INT 21H
main endp
end main
TASK 3;
Code:
org 100h
.data
.code
main proc   
    
    mov dl,110
     mov ah,1h
     INT 21H
     mov dl,97
     mov ah,1h
     INT 21H
     mov dl,121
     mov ah,1h
     INT 21H
     mov dl,97
     mov ah,1h
     INT 21H  
     mov dl,98
     mov ah,1h
     INT 21H
      mov dl,110-32
     mov ah,2h
     INT 21H
     mov dl,97-32
     mov ah,2h
     INT 21H
     mov dl,121-32
     mov ah,2h
     INT 21H
     mov dl,97-32
     mov ah,2h
     INT 21H
      mov dl,98-32
     mov ah,2h
     INT 21H
    main endp
end main
*******LAB 4********
TASK 1:
model small
.stack 100h
.data
.code
main proc
    mov dl,'6'
    mov ah,2 
    INT 21h  
    mov dl,'1'
    mov ah,2 
    INT 21h
    mov dl,'4'
    mov ah,2 
    INT 21h
    mov dl,'7'
    mov ah,2 
    INT 21h
    mov dl,'2'
    mov ah,2 
    INT 21h 
    mov ah,4ch
    INT 21h  
    main endp
end main
TASK 2:
Task no 2

.model small
.stack 100h
.data
.code
main proc
mov ah,1h    
INT 21h
SUB al,30h
mov bl,al
mov ah, 1h
INT 21h
SUB al,30h
ADD bl,al
ADD bl,30h
mov dl,bl
mov ah, 2h
INT 21h
mov ah,4ch
main endp
end main
*******LAB 5*******
TASK 1:
Code:
org 100h
.model small
.data
.code
main proc
    MOV AH, 01h
INT 21h
SUB AL, 30h
MOV BL, AL
MOV AH, 01h
INT 21h
SUB AL, 30h
MOV BH, AL
MOV AL, BH
ADD AL, 30h
MOV DL, AL
MOV AH, 02h
INT 21h
MOV AL, BL
ADD AL, 30h
MOV DL, AL
MOV AH, 02h
INT 21h  
end mainp
endmain
TASK 2:
Code;
org 100h
.model small
.data
.code
main proc
   
    MOV AH, 1h
    INT 21h
    SUB AL, 30h     
    MOV BL, AL     
    MUL BL          
    ADD AL, 30h
    MOV DL, AL
    MOV AH, 02h
    INT 21h
    MOV AH, 4Ch
    INT 21h

main endp
end main
TASK 3;
Code:
org 100h
.model small
.data
.code
main proc
    mov bl, 3        
    mov bh, 5       
    add bl, bh       
    mov dl, 6       
    sub bl, dl       
    add bl, 30h      
    mov dl, bl       
    mov ah, 2h      
    int 21h
    mov ah, 4Ch
    int 21h
main endp
end main
TASK 4;
Code;
MOV AH, 1    
INT 21H      
SUB AL, 30H  
MOV BL, AL   
MOV AH, 1    
INT 21H      
SUB AL, 30H   
MOV BH, AL    

XCHG BL, BH  
ADD BL, 30H  
MOV DL, BL
MOV AH, 2
INT 21H
MOV DL, ' '   
MOV AH, 2
INT 21H
ADD BH, 30H   
MOV DL, BH
MOV AH, 2
INT 21H
MOV AH, 4CH   
INT 21H   
end mainp
endmain
TASK 5:
Code:
org 100h
.model small
.data
.code
main proc
    mov ah, 1h       
    int 21h           
    add al, 30h       
    mov dl, al       
    mov ah, 2h
    int 21h           
    mov ah, 4Ch
    int 21h
main endp
end main
******LAB 6******
TASK 1:
Code:
.model small
.stack 100h
.data
    newline db '$'
.code
main proc
    mov ax, @data
    mov ds, ax
    mov ah, 01h          
    int 21h              
    sub al, 20h           
    mov dl, al            
    mov ah, 02h           
    int 21h
    mov dl, ' '           
    mov ah, 02h          
    int 21h
    mov ah, 4Ch
    int 21h
       main endp
end main
TASK 2:
.model small
.stack 100h
.data
    CV_data DB 'Name: Nayyab Razzaq' ,13,10
            DB 'Age: 20 Years',13,10
            DB 'Degree: BS Software Engineering',13,10
            DB 'Email: nayyab21@gmaol.com',13,10
            DB 'Phone: 0300-12224567',13,10
            DB 'Address: gulberg green' ,13,10
            DB 'Skills: coding C++, Java, Assembly ',13,10,'$'
.code
main proc   
    MOV AX, @data
    MOV DS, AX
    MOV DX, OFFSET CV_data  
    MOV AH, 09H
    INT 21H
    MOV AH, 10h
    INT 21H
    MOV AH, 13h
    INT 21H
    MOV AH, 4Ch  
    INT 21H
main endp
end main
TASK 3:
.model small
.stack 100h
.data
    msg DB 'Enter a character: $'   
    first DB 13, 10 , '$'        
    output DB 'The user entered: $' 
.code
Main proc
    MOV AX, @DATA
    MOV DS, AX
    MOV DX, OFFSET msg
    MOV AH, 09H
    INT 21H
    MOV AH, 01H
    INT 21H
    MOV BL, AL   
    MOV DX, OFFSET first
    MOV AH, 09H
    INT 21H
    MOV DX, OFFSET output
    MOV AH, 09H
    INT 21H
    MOV DL, BL
    MOV AH, 02H
    INT 21H
    MOV AH, 4CH
    INT 21H
main endp
end main
*******LAB 7********
TASK 1:
.model small 
.stack 100h 
.data 
.code 
main proc 
    mov ah, 01h 
    int 21h            
    sub al, '0'        
    mov bl, al       
    mul bl             ; AL * BL => AX = num^2 (square) 
       add al, '0'       
    mov dl, al         
    mov ah, 02h 
    int 21h 
 mov ah, 4Ch 
    int 21h 
main endp 
end main
TASK 2:
.model small 
.stack 100h 
.data 
.code 
main proc 
    mov ah, 01h 
    int 21h            
    sub al, '4'         
    mov bl, al         
    ; Input Height 
    mov ah, 01h 
    int 21h             
    sub al, '5'        
    mov dl, bl         
    mul al             
    mov bx, 2 
    div bx             
    add al, '0'        
    mov dl, al         
    mov ah, 02h 
    int 21h 
    mov ah, 4Ch 
    int 21h 
   main endp 
  end main
TASK 3:
.model small 
.stack 100h 
.data 
.code 
main proc 
    mov ah, 01h 
    int 21h             
    sub al, '0'  
    mov bl, al          
    mov ah, 01h 
    int 21h             
    sub al, '0'        
    mul bl             
    add al, '0'        
    mov dl, al        
    mov ah, 02h 
    int 21h 
    mov ah, 4Ch 
    int 21h 
    main endp 
end main
TASK 4:
.model small
.stack 100h

.code
main proc
    ; Read number
    mov ah, 01h
    int 21h
    sub al, '0'
    mov bl, al

    ; Calculate cube
    mov al, bl
    mul bl
    mul bl

    ; Print result (handling numbers greater than 9)
    mov cx, ax
    mov ah, 02h
    mov dl, ch
    add dl, '0'
    int 21h
    mov dl, cl
    add dl, '0'
    int 21h

    ; Exit
 mov ah, 4ch
    int 21h
main endp
end main
******LAB 8*******
TASK 1:
.model small
.stack 100h
.data
.code 
main proc
mov cx,5
mov dx,49 
label1:
mov ah,2
int 21h
add dx,2
loop label1
mov ah,4ch
int 21h
main endp
end main
TASK 2:
.model small
.stack 100h
.data
.code 
main proc
mov cx,5
mov dx,56 
label1:
mov ah,2
int 21h
sub dx,2
loop label1
mov ah,4ch
int 21h
main endp
end main
TASK 3:
.model small
.stack 100h
.data
.code 
main proc
    mov al,1
    add al,2
    add al,3  
    add al,'0'
    mov dl,al
    mov ah,2
    int 21h 
    mov ah,4ch
    int 21h
    main endp
end main
TASK 4:
.model small
.stack 100h
.data
.code 
main proc
mov cx,10
mov dx,57 
label1:
mov ah,2
int 21h
sub dx,1
loop label1
mov ah,4ch
int 21h
main endp
end main
TASK 5;
.model small
.stack 100h
.data 
msg1 db "enter character:$"
.code 
main proc
    
   mov ax,@data
   
   mov ds,ax
   mov ah,9
   mov dx,offset msg1
   int 21h
   mov ah,1
   int 21h
   mov bl,al
   mov cx,10
   label1:
   mov dl,bl
   mov ah,2h
   int 21h
   mov dl,13
   mov ah,2h
   int 21h
   mov dl,10
   int 21h
   loop label1
   mov ah,4ch
   int 21h
main endp
end main
TASK 6:
.model small
.stack 100h
.data 
.code 
main proc
    
  
  mov ax, @data
  mov ds, ax
  mov cl, 'a'
  
  print_loop:
  mov dl , cl
  mov ah , 02h
  int 21h
  
  inc cl
  cmp cl , 'z' +1
  jne print_loop
  
  mov ah, 4ch
  int 21h
main endp
end main
******LAB 9********
TASK 1:
.model small
.stack 100h
.data
    msg1 DB 10,13, "Enter First Number [A]: $"
    msg2 DB 10,13, "Enter Second Number [B]: $"
    msg_equal DB 10,13, "A is Equal to B$"
    msg_greater DB 10,13, "A is Greater than B$"
    msg_smaller DB 10,13, "A is smaller than B$"
.code
main proc
    mov ax, @data       
    mov ds, ax
    mov dx, offset msg1
    mov ah, 9
    int 21h
    mov ah, 1
    int 21h
    sub al, 30h         
    mov bl, al          
    mov dx, offset msg2
    mov ah, 9
    int 21h
    mov ah, 1
    int 21h
    sub al, 30h         
    mov bh, al          
    mov al, bl
    cmp al, bh
    je equal
    ja greater
    jb smaller
equal:
    mov dx, offset msg_equal
    mov ah, 9
    int 21h
    jmp exit
greater:
    mov dx, offset msg_greater
    mov ah, 9
    int 21h
    jmp exit
smaller:
    mov dx, offset msg_smaller
    mov ah, 9
    int 21h
exit:
    mov ah, 4ch
    int 21h
main endp
end main
TASK 2:
.model small
.stack 100h
.data
    msg1 DB 10,13, "Enter a one digit number: $"
    zero DB 10,13, "The number you entered is ZERO.$"
    positive DB 10,13, "The number you entered is POSITIVE.$"
.code
main proc
    mov ax, @data
    mov ds, ax
    mov dx, offset msg1
    mov ah, 9
    int 21h
    mov ah, 1
    int 21h
    sub al, 30h        
    cmp al, 0
    je number_zero         
    mov dx, offset positive
    mov ah, 9
    int 21h
    jmp exit
number_zero:
    mov dx, offset zero
    mov ah, 9
    int 21h
exit:
    mov ah, 4ch
    int 21h
main endp
end main
TASK 3:
.model small
.stack 100h
.data
    msg1 DB 10,13, "Enter a one-digit number: $"
    even DB 10,13, "The number you entered is EVEN.$"
    odd DB 10,13, "The number you entered is ODD.$"
.code
main proc
    mov ax, @data
    mov ds, ax
    mov dx, offset msg1
    mov ah, 9
    int 21h
    mov ah, 1
    int 21h
    sub al, 30h      
    mov ah, 0        
    mov bl, 2        
    div bl           
    cmp ah, 0
    je label_even          
    mov dx, offset odd
    mov ah, 9
    int 21h
    jmp exit
label_even:
    mov dx, offset even
    mov ah, 9
    int 21h
exit:
    mov ah, 4ch
    int 21h
main endp
end main
TASK 4:
.model small
.stack 100h
.data
    msg1 DB 10,13, "Enter your marks[one digit]: $"
    low DB 10,13, "Need hard work.$"
    good DB 10,13, "Satisfactory.$"
.code
main proc
    mov ax, @data
    mov ds, ax
    mov dx, offset msg1
    mov ah, 9
    int 21h
    mov ah, 1
    int 21h
    sub al, 30h       
    cmp al, 5
    jl less_marks      
    mov dx, offset good
    mov ah, 9
    int 21h
    jmp exit
less_marks:
    mov dx, offset low
    mov ah, 9
    int 21h
exit:
    mov ah, 4ch
    int 21h
main endp
end main
