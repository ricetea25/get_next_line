# get_next_line

## Description
`get_next_line` is a 42 project that requires us to write a function in c that can retrieve a line from a file using its file descriptor. The function returns the line read, including the newline character if present, or NULL if there's nothing else to read or an error occurs. Difficult part: OS kernel keeps a file offset for each open file descriptor, so it "knows" where it read to lets say 8 bytes then it knows to start at the 9th bytes to continue reading through read(). However, not every sentence in your file that you are reading from will be exactly 8 bytes, it reads everything regardless of what it is in 8 bytes. so my job is to give the user what is in line defined by '\n'. then keep whatever is left from current read() to the next time we read() from the same file descriptor.


## Requirements
- GCC compiler (compiles with -Wall -Werror -Wextra)
- C standard libraries
- bonus is basically a get next line that can read from different file descriptor simultaneous

## How to use
```bash
# Clone the repo
git clone <your-repo-url> get_next_line
cd get_next_line

# uncomment main to test or you could include it in your other projects after compiling with command below
#include <path_to_getnext_line>/get_next_line.h

# Compile mandatory
gcc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c

# compile bonus
gcc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line_bonus.c get_next_line_utils_bonus.c
