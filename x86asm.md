#X86 汇编
---
1. 通过C语言嵌入汇编的方式调用系统调用  
以`sys_write` 为例, i686的`write`的系统调用号为0x4,  
下面的代码将输出 `hello world`

	    /* *
    	 * File: write-asm.c
    	 * Desc: linux write system call with asm
    	 */
    	int main(int argc, char *argv[]) 
    	{
    		int iret = -1;
    		int fd = 1;
    		int len = 11;
    		char *str = "hello world";
    		asm volatile(
    				"mov %1, %%ebx\n\t"
    				"mov %2, %%ecx\n\t"
    				"mov %3, %%edx\n\t"
    				"mov $0x4, %%eax\n\t"
    				"int $0x80\n\t"
    				"mov %%eax, %0\n\t"
    				:"=m"(iret)
    				:"r"(fd),"m"(str),"r"(len)
    				);
    		return iret;
    	}

>编译命令: `gcc -o write-asm -m32 write-asm.c`  
**注意**: 将`str`传给`write`时，一定要用内存，否则输出的内容不正确
