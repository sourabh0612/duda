CC      = gcc
CFLAGS  =  -g -Wall
LDFLAGS = 
DEFS    = -DDEBUG -DSAFE_FREE
INCDIR  = ../../../../src/include -I../../src
OBJECTS = duda_package.o sqlite.o
SOURCES = duda_package.c sqlite.c

all: ../sqlite.dpkg

../sqlite.dpkg: $(OBJECTS)
	$(CC) $(CFLAGS) $(LDFLAGS) $(DEFS) -shared -Wl -o $@ $^ -lc -lsqlite3

.c.o: $(SOURCES)
	$(CC) $(CFLAGS) $(DEFS) -I$(INCDIR) -fPIC -c $<

clean:
	rm -rf *~ *.o
