CC 	= gcc
CFLAGS	=  -g -Wall
LDFLAGS = 
DEFS    = -DDEBUG -DSAFE_FREE
INCDIR  = ../../../src/include
SOURCES = duda.c duda_conf.c duda_api.c duda_event.c duda_queue.c \
	duda_body_buffer.c duda_sendfile.c duda_debug.c duda_global.c \
	duda_package.c duda_param.c duda_session.c duda_cookie.c \
	duda_console.c duda_xtime.c duda_utils.c webservice.c

OBJECTS = duda.o duda_conf.o duda_api.o duda_event.o duda_queue.o \
	duda_body_buffer.o duda_sendfile.o duda_debug.o duda_global.o \
	duda_package.o duda_param.o duda_session.o duda_cookie.o \
	duda_console.o duda_xtime.o duda_utils.o webservice.o

all: ../monkey-duda.so

../monkey-duda.so: $(OBJECTS)
	@(for d in $(DIRS); do $(MAKE) -C $$d ; done)
	$(CC) $(CFLAGS) $(LDFLAGS) $(DEFS) -shared -o $@ $^ -lc

.c.o: $(SOURCES)
	$(CC) $(CFLAGS) $(LDFLAGS) $(DEFS) -I$(INCDIR) -fPIC -c $<

clean:
	@(for d in $(DIRS); do $(MAKE) -C $$d clean; done)
	rm -rf *.o *~ *.*so*
