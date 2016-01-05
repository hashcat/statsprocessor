##
##  Makefile for sp
##

CFLAGS = -W -Wall -std=c99 -O2 -s
#CFLAGS = -W -Wall -std=c99 -g

CC_LINUX32        = gcc
CC_LINUX64        = gcc
CC_WINDOWS32      = /usr/bin/i686-w64-mingw32-gcc
CC_WINDOWS64      = /usr/bin/x86_64-w64-mingw32-gcc
CC_OSX32          = /usr/bin/i686-apple-darwin10-gcc
CC_OSX64          = /usr/bin/i686-apple-darwin10-gcc

CFLAGS_LINUX32    = $(CFLAGS) -m32 -DLINUX
CFLAGS_LINUX64    = $(CFLAGS) -m64 -DLINUX
CFLAGS_WINDOWS32  = $(CFLAGS) -m32 -DWINDOWS
CFLAGS_WINDOWS64  = $(CFLAGS) -m64 -DWINDOWS
CFLAGS_OSX32      = $(CFLAGS) -m32 -DOSX
CFLAGS_OSX64      = $(CFLAGS) -m64 -DOSX

all: sp64.bin

sp32: sp32.bin sp32.exe sp32.app
sp64: sp64.bin sp64.exe sp64.app

clean:
	rm -f sp32.bin sp64.bin sp32.exe sp64.exe sp32.app sp64.app

sp32.bin: sp.c
	$(CC_LINUX32)   $(CFLAGS_LINUX32)   -o $@ $^

sp64.bin: sp.c
	$(CC_LINUX64)   $(CFLAGS_LINUX64)   -o $@ $^

sp32.exe: sp.c
	$(CC_WINDOWS32) $(CFLAGS_WINDOWS32) -o $@ $^

sp64.exe: sp.c
	$(CC_WINDOWS64) $(CFLAGS_WINDOWS64) -o $@ $^

sp32.app: sp.c
	$(CC_OSX32)     $(CFLAGS_OSX32)     -o $@ $^

sp64.app: sp.c
	$(CC_OSX64)     $(CFLAGS_OSX64)     -o $@ $^
