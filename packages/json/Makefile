CC      = gcc
CFLAGS  =  -g -Wall
LDFLAGS = 
DEFS    = -DDEBUG -DSAFE_FREE
INCDIR  = ../../../../src/include -I../../src
OBJECTS = duda_package.o cJSON.o
SOURCES = duda_package.c cJSON.c

all: ../json.dpkg

../json.dpkg: $(OBJECTS)
	$(CC) $(CFLAGS) $(LDFLAGS) $(DEFS) -shared -Wl -o $@ $^ -lc -lm

.c.o: $(SOURCES)
	$(CC) $(CFLAGS) $(DEFS) -I$(INCDIR) -fPIC -c $<

clean:
	rm -rf *~ *.o
