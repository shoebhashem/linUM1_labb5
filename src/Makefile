#This is a makefile
BINARY=program1
CODEDIRS=. 3D
INCDIRS=. ./
CC=gcc
DEPFLAGS=-MP -MD
CFLAGS=-Wall -g $(foreach D,$(INCDIRS),-I$(D)) $(DEPFLAGS)

CFILES=$(foreach D,$(CODEDIRS),$(wildcard  $(D)/*.c))

OBJECTS=$(patsubst %.c,%.o,$(CFILES))
DEPFILES=$(patsubst %.c,%.d,$(CFILES))

all: $(BINARY)

$(BINARY): $(OBJECTS)
	$(CC) -o $@ $^

%.o:%.c
	$(CC) $(CFLAGS) -c -o $@ $<

clean:
	rm *.o *.d program1
install:
	sudo cp program1 /opt/
uninstall:
	sudo rm /opt/program1

$(DEPFILES):

include $(wildcard $(DEPFILES))
