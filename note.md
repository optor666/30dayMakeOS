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
