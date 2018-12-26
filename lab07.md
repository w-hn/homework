# 关于实验目标     
    1、了解ACC、PC、IR寄存器的全称与作用，并且通过观察指令的执行过程理解fetch-execute周期,了解基本的指令结构及二进制（机器语言）运作过程       
    2.理解机器语言程序的运作以及过程。          
    ![](https://lorisyy.github.io/HomeworkSpace/images/cpu1.png)    
    ![](https://lorisyy.github.io/HomeworkSpace/images/cpu2.png)    
     STEP AFTER STEP:       
PC (The Program Counter),which contains the address of the next instruction to be exececuted.     
IR (Instruction register),which contains a copy of the instructionbeing executed.       

ACC ,is short for Accumulator,which is used to hold data and the result of operation,an accumulator is a register in which intermediate arithmetic and logic results are stored.        

LOD #3：获得该指令后，指令被存在IR寄存器中，Decoder(解码器)对该指令进行解码操作，将前半部分的LOD作为命令传输到ALU中,并将后半部分的3通过MUX命令传入ALU中得到了ALU右边的数字3，寄存入ACC寄存器中。PC指令数加二代表该步骤已经执行完毕，下一步准备就绪。
          
ADD W:获得该指令后，该指令被寄存在IR寄存器中，Decoder对该指令进行解码操作，将ADD指令传输到ALU中,命令MUX将W的值从ACC中读取出来传入ALU,ALU根据命令ADD将两值相加，并且将执行结果传入ACC中寄存.PC计数器加2，下一条指令准备就绪。       

LOD#3与ADD W之间的区别在于，LODz指令直接读取已给的操作数，而ADD指令需要把寄存器中的数字读取出来后在进行操作。         

Binary:
00010100 00000111 0001表示最后八位的二进制数不是内存地址而是一个值 0100表示LOD 00000111表示的是7的二进制。       

RAM的地址：可以看出，需要利用内存空间的，后八位首位都是1，之后的七位二进制数字表示内存的地址。       

该CPU的内存地址有八位且为二进制，非16进制，八位二进制相当于为两位16进制数字，故该cpu有8位。     

int_8 a = 3; int_8 b = 7; int_8 c = 3 + 7;        


    
