# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

AIM:
Write C programs to illustrate IPC using pipes mechanisms.

ALGORITHM:
Create a child process usingfork()

Create a simple pipe with C, we make use of the pipe() systemcall.

Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting

Close the read end of parent process using close() and perform writeoperation

Close the write end of child process and performreading

Display thetext.

PROGRAM:
```
#include <stdio.h>
int main()
{
int fd[2],child; char a[10];
printf("\n Enter the string:");
scanf("%s",a);
pipe(fd);
child=fork();
if(!child)
{
close(fd[0]);
write(fd[1],a,5); wait(0);
}
else
{
close(fd[1]);
read(fd[0],a,5); printf("The string received from pipe is: %s",a);
}
return 0;
}
```
OUTPUT:
![exp6](https://github.com/Reebak04/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/118364993/9c8acff9-6a79-4c60-86b3-50ad903981a7)

RESULT:
Thus, IPC using pipes mechanisms is illustrated using c program successfully.
