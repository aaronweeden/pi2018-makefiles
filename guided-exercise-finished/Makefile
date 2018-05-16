# Define the shell to use when executing the make commands
SHELL=/bin/sh # It is recommended to always use /bin/sh

# Define a macro for the name of the executable file
EXECUTABLE=fire.exe

# Define a macro for the compiler command
CC=gcc # Use the GNU compiler

# Define a macro for the compiler flags
CFLAGS=-Wall # Show all warnings
CFLAGS+=-std=gnu99 # Use the C99 standard
CFLAGS+=--pedantic # Be strict about code style

# Define a macro for the source files
SRCS=$(wildcard *.c) # Anything that ends in .c

# Define a macro for the object files
OBJS=$(SRCS:.c=.o) # The corresponding .o files for each of the C source files

# Define a macro for the libraries to link to
LIBS= # No libraries needed

# Define the rule for building the executable
$(EXECUTABLE): $(OBJS)
	$(CC) $(CFLAGS) -o $@ $^ $(LIBS)

# Define the rules for compiling the object files
main.o: main.c utils.h input.h memory.h output.h simulation.h
	$(CC) $(CFLAGS) -c -o $@ $<

utils.o: utils.c utils.h
	$(CC) $(CFLAGS) -c -o $@ $<

input.o: input.c input.h
	$(CC) $(CFLAGS) -c -o $@ $<

memory.o: memory.c memory.h
	$(CC) $(CFLAGS) -c -o $@ $<

output.o: output.c output.h utils.h
	$(CC) $(CFLAGS) -c -o $@ $<

simulation.o: simulation.c simulation.h utils.h
	$(CC) $(CFLAGS) -c -o $@ $<

# Define a rule for removing the object files
clean:
	rm -f $(OBJS)

# Define a rule for removing the object and executable files
distclean:
	rm -f $(OBJS) $(EXECUTABLE)

