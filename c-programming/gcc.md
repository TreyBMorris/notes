# GNU Compiler Collection (GCC)

- The GNU Compiler Collection is a compiler from the GNU project that is used for various programming languages, but most notably C and C++
- GCC was originally the compiler for the GNU operating system and was developed to be free open source software.
- GNU actually encourages people to contribute changes or help with testing the GCC. They are available through Git and weekly snapshots according to their website.
- You can visit the GCC website [here](https://gcc.gnu.org)

## Using GCC
- When using GCC, you will first need a program. For all my examples, I will be focusing on using C since that is the current language that I am learning and wanting to use this for. My program will be called 'main.c' and will contain the following code,
```C
#include <stdio.h>
#inclue "main.h"
int main(){
  printf("Hello World!\n");
  return 0; 
}
```
To compile this program with the GCC, we will run the following command.
```bash
gcc main.c -o main
```
After running, we will get a file called "main". We can run this program in the terminal by using "./main" which will print Hello World!

- The -o flag is used to specify a name for the executable file. The default name for the executable is a.out which can also be ran by typing "./a.out"


