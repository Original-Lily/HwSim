# CPUem - HACK code
HACK language code for use with https://www.nand2tetris.org/ CPU emulator:


<b>Adding Two Numbers</b>

    @0
    D=M // D = RAM[0]
    @1
    D=D+M // D = D + RAM[1]
    @2
    M=D // RAM[2] = D

<br><b>Terminating A Program</b>
We need to terminate programs safely. To do this, we end with an infinite loop.

    @6
    0;JMP 

<br><b>Flip Values Of RAM[0] and RAM[1]</b>

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

<br>


![Untitled(1)](https://github.com/Original-Lily/HwSim/assets/87139613/d89d48b3-a9b5-4193-92ef-ff5d29d50697)
![Untitled](https://github.com/Original-Lily/HwSim/assets/87139613/0ba6adec-01a1-48fc-84cb-5ba16e2d0154)
