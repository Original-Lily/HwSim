# HwSim-LogicGates
Logic gates for use with https://www.nand2tetris.org/ hardware simulator:

<b>NOT</b>

    PARTS:
    Nand(a=in, b=in, out=out);

<b>AND</b>

    PARTS:
    Nand(a=a, b=b, out=nandOut);
    Not(in=nandOut, out=out);

<b>OR</b>

    PARTS:
    Not(in=a, out=nota);
    Not(in=b, out=notb);
    Nand(a=nota, b=notb, out=out);


<b>OR8WAY</b>

    PARTS:
     Or(a=in[0], b=in[1], out=t1);
     Or(a=in[2], b=t1, out=t2);
     Or(a=in[3], b=t2, out=t3);
     Or(a=in[4], b=t3, out=t4);
     Or(a=in[5], b=t4, out=t5);
     Or(a=in[6], b=t5, out=t6);
     Or(a=in[7], b=t6, out=out);

<b>MUX</b>

    PARTS:
    Not(in=sel, out=notsel);
    And(a=notsel, b=a, out=ares);
    And(a=sel, b=b, out=bres);
    Or(a=ares, b=bres, out=out);

<b>MUX4WAY8</b>

    PARTS:
    Mux8(a=a, b=b, sel=sel[0], out=outab);
    Mux8(a=c, b=d, sel=sel[0], out=outcd);
    Mux8(a=outab, b=outcd, sel=sel[1], out=out);

<b>DMUX</b>

    PARTS:
    Not(in=sel, out=notsel);
    And(a=notsel, b=in, out=a);
    And(a=sel, b=in, out=b);

<b>DMUX8WAY</b>

    PARTS:
    DMux(in=in, sel=sel[2], a=abcd, b=efgh);
    DMux(in=abcd, sel=sel[1], a=ab, b=cd);
    DMux(in=efgh, sel=sel[1], a=ef, b=gh);
    DMux(in=ab, sel=sel[0], a=a, b=b);
    DMux(in=cd, sel=sel[0], a=c, b=d);
    DMux(in=ef, sel=sel[0], a=e, b=f);
    DMux(in=gh, sel=sel[0], a=g, b=h);

<b>NOT8</b>

    PARTS:
	Not(in=in[0], out=out[0]);
	Not(in=in[1], out=out[1]);
	Not(in=in[2], out=out[2]);
	Not(in=in[3], out=out[3]);
	Not(in=in[4], out=out[4]);
	Not(in=in[5], out=out[5]);
	Not(in=in[6], out=out[6]);
	Not(in=in[7], out=out[7]);

<b>AND8</b>

    PARTS:
     And(a=a[0], b=b[0], out=out[0]);
     And(a=a[1], b=b[1], out=out[1]);
     And(a=a[2], b=b[2], out=out[2]);
     And(a=a[3], b=b[3], out=out[3]);
     And(a=a[4], b=b[4], out=out[4]);
     And(a=a[5], b=b[5], out=out[5]);
     And(a=a[6], b=b[6], out=out[6]);
     And(a=a[7], b=b[7], out=out[7]);

<b>OR8</b>

    PARTS:
     Or(a=a[0], b=b[0], out=out[0]);
     Or(a=a[1], b=b[1], out=out[1]);
     Or(a=a[2], b=b[2], out=out[2]);
     Or(a=a[3], b=b[3], out=out[3]);
     Or(a=a[4], b=b[4], out=out[4]);
     Or(a=a[5], b=b[5], out=out[5]);
     Or(a=a[6], b=b[6], out=out[6]);
     Or(a=a[7], b=b[7], out=out[7]);

<b>XOR</b>

    PARTS:
    And(a=a, b=b, out=ab);
    Or(a=a, b=b, out=aorb);
    Not(in=aorb, out=notaorb);
    Or(a=ab, b=notaorb, out=bla);
    Not(in=bla, out=out);

<b>MUX8</b>

    PARTS:
     Mux(a=a[0], b=b[0], sel=sel, out=out[0]);
     Mux(a=a[1], b=b[1], sel=sel, out=out[1]);
     Mux(a=a[2], b=b[2], sel=sel, out=out[2]);
     Mux(a=a[3], b=b[3], sel=sel, out=out[3]);
     Mux(a=a[4], b=b[4], sel=sel, out=out[4]);
     Mux(a=a[5], b=b[5], sel=sel, out=out[5]);
     Mux(a=a[6], b=b[6], sel=sel, out=out[6]);
     Mux(a=a[7], b=b[7], sel=sel, out=out[7]);

<b>MUX8WAY8</b>

    PARTS:
    Mux8(a=a, b=b, sel=sel[0], out=outab);
    Mux8(a=c, b=d, sel=sel[0], out=outcd);
    Mux8(a=e, b=f, sel=sel[0], out=outef);
    Mux8(a=g, b=h, sel=sel[0], out=outgh);
    Mux8(a=outab, b=outcd, sel=sel[1], out=outabcd);
    Mux8(a=outef, b=outgh, sel=sel[1], out=outefgh);
    Mux8(a=outabcd, b=outefgh, sel=sel[2], out=out);

<b>DMUX4WAY</b>

    PARTS:
    DMux(in=in, sel=sel[1], a=outa, b=outb);
    DMux(in=outa, sel=sel[0], a=a, b=b);
    DMux(in=outb, sel=sel[0], a=c, b=d);

<b>ALU</b>

    PARTS:
    Xor(a=a, b=b, out=sum);
    And(a=a, b=b, out=carry);

<b>FULLADDER</b>

    PARTS:
    HalfAdder(a=a, b=b, sum=absum, carry=abcarry);
    HalfAdder(a=absum, b=c, sum=sum, carry=abccarry);   
    Or(a=abcarry, b=abccarry, out=carry);               

<b>ADD8</b>

    PARTS:
    HalfAdder(a=a[0],   b=b[0],   sum=out[0],           carry=c0);
    FullAdder(a=a[1],   b=b[1],   c=c0,   sum=out[1],   carry=c1);
    FullAdder(a=a[2],   b=b[2],   c=c1,   sum=out[2],   carry=c2);
    FullAdder(a=a[3],   b=b[3],   c=c2,   sum=out[3],   carry=c3);
    FullAdder(a=a[4],   b=b[4],   c=c3,   sum=out[4],   carry=c4);
    FullAdder(a=a[5],   b=b[5],   c=c4,   sum=out[5],   carry=c5);
    FullAdder(a=a[6],   b=b[6],   c=c5,   sum=out[6],   carry=c6);
    FullAdder(a=a[7],   b=b[7],   c=c6,   sum=out[7],   carry=c7);

<b>INC8</b>

    PARTS:
    Add8(a=in, b[0]=true, out=out);

<b>ALU</b>
Mux16(a=x,b=false,sel=zx,out=xz);
Mux16(a=y,b=false,sel=zy,out=yz);
Not16(in=xz,out=negXz);
Mux16(a=xz,b=negXz,sel=nx,out=Xn);
Not16(in=yz,out=negYz);
Mux16(a=yz,b=negYz,sel=ny,out=Yn);
And16(a=Xn,b=Yn,out=XnANDYn);
Add16(a=Xn,b=Yn,out=XnADDYn);
Mux16(a=XnANDYn,b=XnADDYn,sel=f,out=F1);
Not16(in=F1,out=notF1);
Mux16(a=F1,b=notF1,sel=no,out=out,out[15]=Qng,out[0..7]=LO1, out[8..15]=HI1);
Or8Way(in=LO1,out=Or1);
Or8Way(in=HI1,out=Or2);
Or(a=Or1,b=Or2,out=nzr);
Not(in=nzr,out=zr);
And(a=Qng, b=true, out=ng);

<h2>SEQUENTIAL LOGIC AND MEMORY</h2>

<b>BIT</b>

    PARTS:
    Mux(a=dffOut, b=in, sel=load, out=muxOut);
    DFF(in=muxOut, out=dffOut);
    Or(a=false, b=dffOut, out=out);

<b>Register</b>

    PARTS:
    Bit(in=in[0], load=load, out=out[0]);
    Bit(in=in[1], load=load, out=out[1]);
    Bit(in=in[2], load=load, out=out[2]);
    Bit(in=in[3], load=load, out=out[3]);
    Bit(in=in[4], load=load, out=out[4]);
    Bit(in=in[5], load=load, out=out[5]);
    Bit(in=in[6], load=load, out=out[6]);
    Bit(in=in[7], load=load, out=out[7]);

<b>RAM8</b>

    PARTS:
    DMux8Way(in=load, sel=address,
      a=sel0,
      b=sel1,
      c=sel2,
      d=sel3,
      e=sel4,
      f=sel5,
      g=sel6,
      h=sel7
    );
    
    Register(in=in, load=sel0, out=r0);
    Register(in=in, load=sel1, out=r1);
    Register(in=in, load=sel2, out=r2);
    Register(in=in, load=sel3, out=r3);
    Register(in=in, load=sel4, out=r4);
    Register(in=in, load=sel5, out=r5);
    Register(in=in, load=sel6, out=r6);
    Register(in=in, load=sel7, out=r7);
    
    Mux8Way8(
      a=r0,
      b=r1,
      c=r2,
      d=r3,
      e=r4,
      f=r5,
      g=r6,
      h=r7,
      sel=address,
      out=out);

<b>RAM64</b>

    PARTS:
    DMux8Way(in=load,sel=address[0..2],a=a,b=b,c=c,d=d,e=e,f=f,g=g,h=h);
	RAM8(in=in,load=a,address=address[3..5],out=out0);
	RAM8(in=in,load=b,address=address[3..5],out=out1);
	RAM8(in=in,load=c,address=address[3..5],out=out2);
	RAM8(in=in,load=d,address=address[3..5],out=out3);
	RAM8(in=in,load=e,address=address[3..5],out=out4);
	RAM8(in=in,load=f,address=address[3..5],out=out5);
	RAM8(in=in,load=g,address=address[3..5],out=out6);
	RAM8(in=in,load=h,address=address[3..5],out=out7);
	Mux8Way8(a=out0,b=out1,c=out2,d=out3,e=out4,f=out5,g=out6,h=out7,sel=address[0..2],out=out);

<b>RAM512</b>

    PARTS:
	DMux8Way(in=load,sel=address[6..8],a=a,b=b,c=c,d=d,e=e,f=f,g=g,h=h);
	RAM64(in=in,load=a,address=address[0..5],out=out0);
	RAM64(in=in,load=b,address=address[0..5],out=out1);
	RAM64(in=in,load=c,address=address[0..5],out=out2);
	RAM64(in=in,load=d,address=address[0..5],out=out3);
	RAM64(in=in,load=e,address=address[0..5],out=out4);
	RAM64(in=in,load=f,address=address[0..5],out=out5);
	RAM64(in=in,load=g,address=address[0..5],out=out6);
	RAM64(in=in,load=h,address=address[0..5],out=out7);
	Mux8Way8(a=out0,b=out1,c=out2,d=out3,e=out4,f=out5,g=out6,h=out7,sel=address[6..8],out=out);

<b>RAM4K</b>

    PARTS:
    DMux8Way(in=load,sel=address[9..11],a=a,b=b,c=c,d=d,e=e,f=f,g=g,h=h);
	RAM512(in=in,load=a,address=address[0..8],out=out0);
	RAM512(in=in,load=b,address=address[0..8],out=out1);
	RAM512(in=in,load=c,address=address[0..8],out=out2);
	RAM512(in=in,load=d,address=address[0..8],out=out3);
	RAM512(in=in,load=e,address=address[0..8],out=out4);
	RAM512(in=in,load=f,address=address[0..8],out=out5);
	RAM512(in=in,load=g,address=address[0..8],out=out6);
	RAM512(in=in,load=h,address=address[0..8],out=out7);
	Mux8Way8(a=out0,b=out1,c=out2,d=out3,e=out4,f=out5,g=out6,h=out7,sel=address[9..11],out=out);

<b>RAM16K</b>

    PARTS:
    DMux4Way(in=load,sel=address[12..13],a=a,b=b,c=c,d=d);

		RAM4K(in=in,load=a,address=address[0..11],out=oa);
		RAM4K(in=in,load=b,address=address[0..11],out=ob);
		RAM4K(in=in,load=c,address=address[0..11],out=oc);
		RAM4K(in=in,load=d,address=address[0..11],out=od);
	
		Mux4Way16(a=oa,b=ob,c=oc,d=od,sel=address[12..13],out=out);
}


