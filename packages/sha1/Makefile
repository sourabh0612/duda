CC      = gcc
CFLAGS  =  -g -Wall
LDFLAGS = 
DEFS    = -DDEBUG -DSAFE_FREE
INCDIR  = ../../../../src/include -I../../src
OBJECTS = duda_package.o sha1.o
SOURCES = duda_package.c sha1.c

all: ../sha1.dpkg

../sha1.dpkg: $(OBJECTS)
	$(CC) $(CFLAGS) $(LDFLAGS) $(DEFS) -shared -Wl -o $@ $^ -lc

.c.o: $(SOURCES)
	$(CC) $(CFLAGS) $(DEFS) -I$(INCDIR) -fPIC -c $<

clean:
	rm -rf *~ *.o
