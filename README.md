# get_next_line
the get_next_line function as specified in the 42_network subject is a function that takes as first argument a file descriptor (stdin, stdout, return of the function open...) and as second argument a reference to a string named here "line", it reads the content of the file specified by fd one line at a time each time it is called, than it allocates the line read using malloc and references it to the variable "line".


RETURN VALUES:
it returns the following values.
1 : If a line has been read.
0 : EOF has been reached.
-1 : An error happened.

USAGE:


#include <stdio.h>
#include <fcntl.h>

int main(int ac, char **av)
{
	int fd;
	char *str;

	fd = open(av[1], O_RDONLY);
	if (ac == 2)
	{ 
		while (get_next_line(fd, &str) > 0)
		{
			puts(str);
			free(str);
		}
	}
	return (0);
}
