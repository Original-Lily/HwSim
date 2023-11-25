# CPUem - HACK code
HACK language code for use with https://www.nand2tetris.org/ CPU emulator:


<b>Adding Two Numbers</b>

<code>
// Program: Add2.asm
// Computes: RAM[2] = RAM[0] + RAM[1]
// Usage: put values in RAM[0], RAM[1]
@0
D=M // D = RAM[0]
@1
D=D+M // D = D + RAM[1]
@2
M=D // RAM[2] = D
</code>

<b>Terminating A Program</b>
We need to terminate programs safely. To do this, we end with an infinite loop.

<code>
@6
0;JMP 
</code>

<b>Flip Values Of RAM[0] and RAM[1]</b>

<code>
// Program: Flip.asm
// flips the values of
// RAM[0] and RAM[1]
@R1
D=M
@temp
M=D // temp = R1
@R0
D=M
@R1
M=D // R1 = R0
@temp
D=M
@R0
M=D // R0 = temp
(END)
@END
0;JMP
</code>

![image](https://github.com/Original-Lily/HwSim/assets/87139613/029bd3d6-bf84-4144-ba79-f1f804f63ebd)
