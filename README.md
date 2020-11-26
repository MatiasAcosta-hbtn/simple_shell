 Simple_shell

 Simple_shell is a project created to simulate a command interpeter. In it you can write the usual commands as an standart input to be executed.

 ## File Contents
 This repository contains the following files:

 |   **File**   |   **Description**   |
 | -------------- | --------------------- |
 | main.c | the main function |
 | shell.h | header file |
 | main_functions.c | functions that read, split and execute an argument |
 | aux_funcs.c | aditional functions to the shell |
 | string_func.c | string related functions |
 | builtin_func.c | functions that controls builtins |
 | path_funcs.c | functions that handle the path |
 | clean_memory.c | function to clean memory |
 | AUTHORS | creators |
 | man_1_simple_shell | manual |

 To utilize this shell, follow the next steps:

 ## Clone the repository

 This way you will have all the files necessary.

 ```
 $ git clone https://github.com/ChloeDumit/simple_shell
 ```

 ## Compile it and start

 To start simple_shell you just need to compile using.

 ```
 gcc -Wall -Werror -Wextra -pedantic *.c -o hsh.
 ```

 ### Start the shell!

 ```
 ./hsh
 ```

 ## How to use it:

 ```
 $ /bin/ls
 $ ls -la
 $ pwd
 \
 ]
 ```
 ## Commands
 |   **Command**   |   **Description**   |
 | -------------- | --------------------- |
 | ls [option] | List directory contents. |
 | pwd | List working directory. |
 | cd [PATH] | Change directory. |
 | cp | Copy Files. |
 | mv | Move files. |
 | Ctrl + C | This signal will be ignored and print a new line. |
 | Ctrl + D | The simple shell will be terminated. |

 ### Command Execution

 After receiving a command, **hsh** tokenizes it into words using `" "` as a delimiter. The first word is considered the command and all remaining words are considered arguments to that command. **Hsh** then proceeds with the following actions:
 1. If the first character of the command is neither a slash (`\`) nor dot (`.`), the shell searches for it in the list of shell builtins. If there exists a builtin by that name, the builtin is invoked.
 2. If the first character of the command is none of a slash (`\`), dot (`.`), nor builtin, **hsh** searches each element of the **PATH** environmental variable for a directory containing an executable file by that name.
 3. If the first character of the command is a slash (`\`) or dot (`.`) or either of the above searches was successful, the shell executes the named program with any remaining given arguments in a separate execution environment.

 ## Builtins Commands
 |   **Command**   |   **Description**   |
 | -------------- | --------------------- |
 | env |  Run a program in a modified enviroment. |
 | exit | Cause normal process termination. |
 #### cd
   * Usage: `cd [DIRECTORY]`
     * Changes the current directory of the process to `DIRECTORY`.
       * If no argument is given, the command is interpreted as `cd $HOME`.

       Example:
       ```
       $ ./hsh
       $ pwd
       /home/vagrant/holberton/simple_shell
       $ cd ../
       $ pwd
       /home/vagrant/holberton
       $ cd
       $ pwd
       /home
       ```

       #### env
         * Usage: `env`
	   * Prints the current environment.

	   Example:
	   ```
	   $ ./hsh
	   $ env
	   NVM_DIR=/home/vagrant/.nvm
	   ```

	   ## Authors
	   * Matias Acosta <[MatiasAcosta-hbtn](https://github.com/MatiasAcosta-hbtn)>
	   * Matias Pirez <[ripjawws](https://github.com/ripjawws)>
	   # simple_shell
