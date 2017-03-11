.SUFFIXES: .c.o

GXX         = g++
CFLAGS      =
LIBS        = -lm
OBJS    	= _c2sp.o _fft.o _fftr.o _freqt.o _gc2gc.o _gnorm.o _ignorm.o \
			  _mgc2mgc.o _mgc2sp.o fileio.o fillz.o getfp.o getmem.o movem.o
EXE         = bin/mgc2sp

SOPR		= test/sopr
X2X			= test/x2x

all: $(EXE)

$(EXE): $(OBJS) mgc2sp.o
	mkdir bin
	gcc -o $(EXE) $(OBJS) mgc2sp.o -lm
    
.c.o:
	gcc -I. -c $< -o $@

test:
	$(EXE) -a 0.45 -g 0 -m 39 -l 1024 -o 2 test/sample.mgc | $(SOPR) -P | $(X2X) +fd > bin/sample.sp

clean:
	rm -rf *.o
	rm -rf bin

.PHONY: all test clean
