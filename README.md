# get_next_line

The `get_next_line` project is part of the 42 school curriculum, challenging students to implement a function that reads a line from a file descriptor. This project aims to improve file reading skills in C and understand dynamic memory allocation.

## Overview
The `get_next_line` function reads a line from a given file descriptor, such as a file or standard input, and stores it in a buffer. Key features include:

- **Reading a line**: Reads a line from the file descriptor until a newline character (`\n`) is encountered or the end of the file is reached.
- **Dynamic memory allocation**: Allocates memory as needed to store the line, enabling efficient handling of lines of varying lengths.
- **Handling multiple file descriptors**: Supports reading from multiple file descriptors without losing track of their respective positions.

## Usage
1. Clone the project:
```bash
git clone https://github.com/seungwonme/get_next_line
```

2. Navigate to the project directory:
```bash
cd get_next_line && rm -rf .git
```

3. Link the library in your project and include the header file:
```c
#include "get_next_line.h"

int main(void)
{
	int		fd;
	char	*line;

	fd = open("example.txt", O_RDONLY);
	while (get_next_line(fd, &line))
	{
		ft_printf("%s\n", line);
		free(line);
	}
	close(fd);

	return (0);
}
```

- To clean up object files:
```bash
make clean
```

- To delete all build files:
```bash
make fclean
```

- To clean and rebuild the library:
```bash
make re
```

## Function Signature
```c
char	*get_next_line(int fd);
```
