# get_next_line
the get_next_line function as specified in the 42_network subject is a function that takes as first argument a file descriptor (stdin, stdout, return of the function open...) and as second argument a reference to a string named here "line", it reads the content of the file specified by fd one line at a time each time it is called, than it allocates the line read using malloc and references it to the variable "line".

what is a line?
a line is every stream of strings in a file delemited by '\n' character or EOF

where get_next_line gets_useful?
in parsing files, it organizes the way you read the file to be one line at a time and the next one and the next one ...

RETURN VALUES:
it returns the following values.
1 : If a line has been read.
0 : EOF has been reached.
-1 : An error happened.

USAGE:
```
#include <stdio.h>
#include <fcntl.h>

int main(int ac, char **av)
{
	int fd;
	char *str;
	int gnl_ret = 1;

	fd = open(av[1], O_RDONLY);
	if (ac == 2)
	{ 
		while (gnl_ret > 0)
		{
			gnl_ret = get_next_line(fd, &str);
			puts(str);
			free(str);
		}
	}
	return (0);
}
```
