#
# Makefile for enemy shoot game using Dragonfly
#
# Copyright Mark Claypool and WPI, 2014
#
# 'make depend' to generate new dependency list
# 'make clean' to remove all constructed files
# 'make' to build executable
#
# Variables of interest:
#   GAMESRC is the source code files for the game
#   GAME is the game main() source
#   DEBUG can be set to -DDEBUG to enable various debug flags
#

CC= g++ 
#PLATFORM= -DCYGWIN		  # uncomment for cygwin
#PLATFORM= -DMACOS  	  # uncomment for macos
LDFLAGS= -lncurses -lrt	  # uncomment linux/cygwin
#LDFLAGS= -lncurses 	  # uncomment for macos
INCPATH= include	  # path to engine includes
ENG= lib/libdragonfly.a # dragonfly engine
GAMESRC= \
         Bullet.cpp \
         GameStart.cpp \
         GameOver.cpp \
         Hero.cpp \
         Points.cpp \

GAME= game.cpp
EXECUTABLE= game		
OBJECTS= $(GAMESRC:.cpp=.o)

all: $(EXECUTABLE) Makefile

$(EXECUTABLE): $(ENG) $(OBJECTS) $(GAME) $(GAMESRC) 
	$(CC) $(GAME) $(OBJECTS) $(ENG) $(PLATFORM) -o $@ -I$(INCPATH) $(LDFLAGS) 

.cpp.o: 
	$(CC) -c $(DEBUG) -I$(INCPATH) $(PLATFORM) $< -o $@

clean:
	rm -rf $(OBJECTS) $(EXECUTABLE) core dragonfly.log Makefile.bak *~

depend: 
	makedepend *.cpp 2> /dev/null
# DO NOT DELETE

Bullet.o: Bullet.h Enemy.h
Enemy.o: /usr/include/stdlib.h /usr/include/features.h
Enemy.o: /usr/include/sys/cdefs.h /usr/include/bits/wordsize.h
Enemy.o: /usr/include/gnu/stubs.h /usr/include/gnu/stubs-64.h
Enemy.o: /usr/include/sys/types.h /usr/include/bits/types.h
Enemy.o: /usr/include/bits/typesizes.h /usr/include/time.h
Enemy.o: /usr/include/endian.h /usr/include/bits/endian.h
Enemy.o: /usr/include/sys/select.h /usr/include/bits/select.h
Enemy.o: /usr/include/bits/sigset.h /usr/include/bits/time.h
Enemy.o: /usr/include/sys/sysmacros.h /usr/include/bits/pthreadtypes.h
Enemy.o: /usr/include/alloca.h Points.h Enemy.h Hero.h
game.o: GameStart.h Star.h Hero.h Enemy.h
GameOver.o: GameOver.h GameStart.h
GameStart.o: GameStart.h Hero.h Points.h
Hero.o: Bullet.h GameOver.h Hero.h
Points.o: Points.h
Star.o: /usr/include/stdlib.h /usr/include/features.h
Star.o: /usr/include/sys/cdefs.h /usr/include/bits/wordsize.h
Star.o: /usr/include/gnu/stubs.h /usr/include/gnu/stubs-64.h
Star.o: /usr/include/sys/types.h /usr/include/bits/types.h
Star.o: /usr/include/bits/typesizes.h /usr/include/time.h
Star.o: /usr/include/endian.h /usr/include/bits/endian.h
Star.o: /usr/include/sys/select.h /usr/include/bits/select.h
Star.o: /usr/include/bits/sigset.h /usr/include/bits/time.h
Star.o: /usr/include/sys/sysmacros.h /usr/include/bits/pthreadtypes.h
Star.o: /usr/include/alloca.h Star.h
