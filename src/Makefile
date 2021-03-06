#
# Colem port on PSP 
#
# Copyright (C) 2008 Ludovic Jacomme (ludovic.jacomme@gmail.com)
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.
#
TARGET = pspcolem
PSPSDK = $(shell psp-config --pspsdk-path)
PSPBIN = $(shell psp-config --psp-prefix)/bin
SDL_CONFIG = $(PSPBIN)/sdl-config

OBJS = \
Coleco.o \
ColEm.o \
Debug.o \
SN76489.o \
Unix.o \
LibPsp.o \
Z80.o \
psp_main.o \
psp_sdl.o \
psp_gu.o \
psp_sound.o \
psp_font.o \
psp_battery.o \
psp_kbd.o \
psp_menu.o \
psp_danzeff.o \
psp_menu_set.o \
psp_menu_help.o \
psp_menu_cheat.o \
psp_menu_list.o \
psp_menu_kbd.o \
psp_menu_joy.o \
psp_editor.o \
psp_irkeyb.o \
psp_irda.o \
psp_joy.o \
miniunz.o \
unzip.o \
psp_fmgr.o


DEFAULT_CFLAGS = $(shell $(SDL_CONFIG) --cflags) -G0

PSP_FW_VERSION=500
PSPCOLEM_VERSION=1.3.1-fw5x

MORE_CFLAGS = -DUNIX -DBPP16 -DLSB_FIRST -DSOUND \
 -funroll-loops -ffast-math -fomit-frame-pointer \
 -fno-strength-reduce -finline-functions \
 -fsingle-precision-constant \
 -DPSPFW30X \
 -DUSE_IRDA_JOY -DUSE_PSP_IRKEYB \
 -DPSPCOLEM_VERSION=\"$(PSPCOLEM_VERSION)\" \
-DNO_STDIO_REDIRECT

OPTIM_CFLAGS= -O2

CFLAGS = $(DEFAULT_CFLAGS) $(MORE_CFLAGS)
CXXFLAGS = $(DEFAULT_CFLAGS) $(MORE_CFLAGS) -fno-exceptions -fno-rtti

LIBS += -lpspirkeyb -lpsppower -lSDL_image -lSDL -lGL -lpspvfpu -lpsprtc -lpng -ljpeg -lpspaudio -lpspgu -lpsphprm -lz -lm

BUILD_PRX=1

EXTRA_TARGETS   = EBOOT.PBP
PSP_EBOOT_TITLE = PSPCOLEM-v$(PSPCOLEM_VERSION)
PSP_EBOOT_ICON  = pspcolem.png
PSP_EBOOT_SND0  = pspcolem.at3
PSP_EBOOT_PIC1  = pspcolem-pic.png

include $(PSPSDK)/lib/build.mak

all: EBOOT.PBP

.c.o:
	$(CC) $(CFLAGS) $(OPTIM_CFLAGS) -c -o $@ $<

.cpp.o:
	$(CXX) $(CXXFLAGS) $(OPTIM_CFLAGS) -c -o $@ $<

psp_gu.o : psp_gu.c
	$(CC) -c $< $(CFLAGS) -O0 -o $@

Z80.o : Z80.c
	$(CC) -c $< $(CFLAGS) -O3 -o $@


install: all
	@mkdir -p /media/usbdisk/psp/game5XX/pspcolem/
	cp EBOOT.PBP /media/usbdisk/psp/game5XX/pspcolem/


realclean:
	/bin/rm -f $(OBJS) EBOOT.PBP PARAM.SFO

