# Change your compiler settings here

# Clang seems to produce faster code
CCPP = g++
CC = gcc
OPTFLAGS = -fomit-frame-pointer -funroll-loops -fPIC -O2 -fno-strict-aliasing
#CCPP = clang++ -m64
#CC = clang -m64
#OPTFLAGS = -O4
DBGFLAGS = -g -DDEBUG
CFLAGS = -Wall -fstrict-aliasing
OPTLIBNAME = liblonghair.a


# Object files

library_o =  cauchy_256.o


# Release target (default)

release : CFLAGS += $(OPTFLAGS)
release : LIBNAME = $(OPTLIBNAME)
release : library


# Library target

library : clean $(library_o)
	ar rcs $(LIBNAME) $(library_o)

# Library objects

cauchy_256.o : cauchy_256.c cauchy_256.h cauchy_tables_256.inc MemSwap.c MemXOR.c MemSwap.h MemXOR.h Platform.h Config.h
	$(CC) $(CFLAGS) -c cauchy_256.c


# Cleanup

.PHONY : clean

clean :
	-rm -f *.a *.o
