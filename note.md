# 名词解释
1. IPL，Initial Program Loader，启动程序装载器；

# 硬件解释
## 英特尔 CPU
1. 家谱：8086 -> 80186 -> 286 -> 386 -> 486 -> Pentium -> PentiumPro -> PentiumII -> PentiumIII -> Pentium4 -> ...，286 及 286 以前的是 16 位，从 386 开始是 32 位；

## 软盘
1. cylinder，柱面。尽管高度非常低，但我们可以把它看成是一个套一个的同心圆筒，从外向内，分别称为柱面0、柱面1、...、柱面79，一共有80个柱面。
2. 磁头，针状的磁性设备，既可以从软盘正面接触磁盘，也可以从软盘背面接触磁盘，因此有正面和反面两个磁头，分别是磁头0号和磁头1号；
3. section，扇区。圆环柱面被均等地分成18份，分别称为扇区1、扇区2、...、扇区18；
4. 一张软盘有 80 个柱面，2 个磁头，18 个扇区，且一个扇区有 512 字节。所以，一张软盘的容量时：80x2x18x512= 1 474 560 Byte = 1 440KB；
5. 含有 IPL 的启动区，位于C0-H0-S1（柱面0，磁头0，扇区1的缩写），下一个扇区是C0-H0-S2； 

# NASK 指令
1. ORG: 来源于英文 "origin"，意思是“源头、起点”。它会告诉 nask，程序要从指定的这个地址开始，也就是要把程序装载到内存中的指定地址。

# 寄存器
## 通用寄存器
| 名称 | 含义 |
| -- | -- |
| AX | accumulator，累加寄存器。X 表示扩展（extend）的意思 |
| CX | counter，技术寄存器 |
| DX | data，数据寄存器 |
| BX | base，基址寄存器 |
| SP | stack pointer，栈指针寄存器 |
| BP | base pointer，基址指针寄存器 |
| SI | source index，源变址寄存器 |
| DI | destination index，目的变址寄存器 |

1. AX、CX、DX、BX 这 4 个 16 位寄存器还可以作为 8 个 8 位寄存器：AL、AH、CL、CH、DL、DH、BL、BH；
2. SP、BP、SI、DI 这 4 个 16 位寄存器不能用作 8 位寄存器。如果想取这 4 个寄存器的高 8 位或低 8 位，就必须用 "mov AX,SI" 将 SI 的值赋给 AX，然后再用 AL、AH 来取值；
3. 这 8 个 16 位寄存器对应的 32 位寄存器的名字是在其前面加上 E 字母：EAX、ECX、EDX、EBX、ESP、EBP、ESI、EDI；
4. 只有 BX、BP、SI、DI 存储内存地址时可以用于寻址，AX、CX、DX、SP 不可以；

## 段寄存器
| 名称 | 含义 |
| -- | -- |
| ES | extra segment，附加段寄存器 |
| CS | code segment，代码段寄存器 |
| SS | stack segment，栈段寄存器 |
| DS | data segment，数据段寄存器 |
| FS | 没有名称 |
| GS | 没有名称 |

1. 这 6 个段寄存器都是 16 位寄存器；

# 内存
1. VRAM，video RAM，0xa0000 ~ 0xaffff，共 64 KB；
