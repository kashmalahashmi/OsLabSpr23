TASK 01

code:

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>
int main() {
    int num_children = 0;
    while (1) {
        pid_t pid = fork();
        if (pid < 0) {
            printf("Error creating children.\n");
            break;
        } else if (pid == 0) {
            printf("Child process created, id: %d\n", getpid());
            sleep(1);
            printf("Child process id: %d, parent id: %d\n", getpid(), getppid());
            sleep(1);
            printf("Child process terminating, id: %d\n", getpid());
            exit(0);
        } else {
            num_children++;
            printf("Parent process created child process, total children: %d\n", num_children);
            if (num_children >= 50) {
       printf("Maximum number of children\n");
      break;
      }
    sleep(2);
    }}
    while (wait(NULL) != -1) {}
    printf("All child processes have terminated.\n");
    return 0;
}

![task1](https://user-images.githubusercontent.com/123877043/220093487-000b0f66-34d3-4c81-a455-89a7011cec95.png)

What is the limit of child process a process can create?
ANS: The limit of child processes that a process can create is determined by the operating system.
On Linux systems, the maximum number of child processes that a process can create is controlled by the ulimit command. The default value for this limit is usually 1024, but it can be increased or decreased by the system administrator or by the user using the ulimit command.

Can you increase this limit. (Find out online)
Yes, the limit on the number of child processes that a process can create can be increased on Linux systems.
One way to increase the limit is to use the ulimit command with the -n option to set the maximum number of open file descriptors, which indirectly affects the number of processes that can be created. By default, each process is allowed to have up to 1024 open file descriptors, which includes both files and sockets. If a process needs to create more child processes, it may need to increase this limit.
COMMMAND: ulimit -n 4096



TASK 02:

![image](https://user-images.githubusercontent.com/123877043/220097429-a15b8913-a528-41da-b83e-bbeb7620c03f.png)


#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int main() {
    pid_t pid;
    pid = fork();
    if (pid < 0) {
        printf("Error forking.\n");
        return 1;
    } else if (pid == 0) {
        printf("Inception level 1\n");
        execl("/bin/sh", "sh", "-c", "./task2_exec", (char *) NULL);
    } else {
        int num_children = 0;

        while (1) {
            pid_t child_pid = fork();

            if (child_pid < 0) {
                printf("Error creating child process.\n");
                break;
            } else if (child_pid == 0) {
                printf("Child process created, id: %d\n", getpid());
                sleep(1);
                printf("Child process id: %d, parent id: %d\n", getpid(), getppid());
                sleep(1);
                printf("Child process terminating, id: %d\n", getpid());
                exit(0);
            } else {
                num_children++;
                printf("Parent process created child process, total children: %d\n", num_children);
                if (num_children >= 50) {
                    printf("Maximum number of children reached.\n");
                    break;
                }
                sleep(2);
            }
        }
        while (wait(NULL) != -1) {}
      printf("All child processes have terminated.\n");
    }
return 0;
}



