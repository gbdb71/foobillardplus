        FooBillard++
                      based on foobillard 3.0a
                       --==##############==--

           Copyright (C) 2001 Florian Berger (foobillard)
          Copyright (C) 2010/2011 Holger Schaekel (foobillard++)

                   http://foobillardplus.sourceforge.net
                   
                      email: foobillardplus@go4more.de
                             

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License Version 2 as
    published by the Free Software Foundation;

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program; if not, write to the Free Software
    Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.

You need !
----------
   100% OpenGL compatible graphic card drivers for your operating system.
   
   The graphic card must have 50 to 80 Megabyte Video-RAM! If the driver can't
   allocate enough graphic card memory, the game graphics is ugly and corrupt!!
   
   Linux, WeTab, Mac OS 10.6.x or Windows OS (32 or 64 Bit) with a minimum of 10 MB
   free system memory at runtime.
   
   With minimum graphics = 1,6 GHz CPU

Thank you very much
-------------------

Many thanks to the band "Zentriert ins Antlitz", specially Marc Friedrich,
for the music in the game! Have a look on their great side at:

http://www.zentriertinsantlitz.de


The product is realized with the following amazing Open-Source Products:

- OpenGL !!
- Linux Ubuntu and OpenSuSe Distributions
- GNU C Compiler
- GNU Autotools
- The SDL Simple Media Library
- Eclipse C/C++ IDE
- Gimp Image Manipulation Program
- Blender 3D
- Audacity
- Free 3D graphics from www.terminal26.de
- Free 3D graphics from www.scopia.es
- Free 3d graphics from www.blendswap.com

- Sourceforge.net as hoster
- freecode.com for announcement
- google code for announcement
- youtube as hoster for the video samples

What is FooBillard++ ?
--------------------

   FooBillard++ is a free OpenGL-billard game for Linux and based on the
   original foobillard 3.0a source from Florian Berger. Why foo?
   Well, actually he had this logo (F.B.-Florian Berger) and then foo sounds a
   bit like pool (Somehow he wasn't quite attracted by the name FoolBillard)
   If you are a billard-pro and you're missing some physics,
   please tell us. Cause I've implemented it like I think it should work,
   which might differ from reality. Please contact us over sourceforge.net
   
   Started at 12/2010 an advanced version is in progress with foobillard++.
   It's not really a new game, but an advanced with a lot of fixes, new
   options, graphics and features until the last version of foobillard (2007).
   At this point it's started with a special version for the Touch-PC WeTab.

   You need to have SDL installed on your system.
   Furthermore libpng has to be installed for loading the textures.
   And freetype is used for font rendering.
   SDL_net is used for the networking mode
   SDL_mixer for sound and music
   
   The following features are implemented:
    - wood paneled table with gold covers and gold diamonds
    - reflections on balls
    - shadow pixmaps
    - detail switching of balls according to distance
    - zoom in/out - hold right mousebutton
    - FOV +/- - hold right mousebutton + CTRL
    - rotate - hold left mousebutton
    - animated cue
    - simple billard rules for 8 and 9-ball
    - simple AI-Player
    - strength adjustment
    - eccentic hit adjustment (button2+Shift)
    - lensflare
    - commandline options
    - config file (~/.foobillardrc)
    - lightweight red/green stereo !!!!
    - sound and music (using SDL)
    - statusline for info in gameplay
    - advanced hud
    - jump shots
    - advanced snipping mode
    - tournament for all games
    - basic OpenGL improvements (anisotropic, antialias)
    - full playable in bird's eye view
    - Tron like game mode
    - glassballs, if you like
   
   Press <F1> in game for a quick help !
   
   red-green stereo:
   -----------------
    one picture is drawn on red channel only, the other one
    on the other both channels (green, blue)
    so you can use either a green or blue or cyan filter for one eye (left),
    and a red one for the other eye (right).
   
   
   network game:
   -------------
   
    IP network support is possible. Now with IPv4. IPv6 is supported in the future.
    This function is heavily BETA.

    
   config file (.foobillardrc):
   ----------------------------
    You can place a config file named ".foobillardrc" in your home directory.
    Windows hold the file in hte directory associated with the content of the
    environment variable USERPROFILE.
    This file can contain all possible commandline arguments (without the
    preceeding "-" and one line for each argument).
    Commandline parameters are parsed afterwards, so they override the
    ".foobillardrc" settings. Please edit the file manually only in problem cases.
    The best way is, to delete it and start the program from cratch.
   
    
   KNOWN BUGS:
   -----------
   
   - Intel integrated graphic chips
   
   - On some Intel integrated graphic chips (GMA) the game is not playable with Linux.
   You need really 100% OpenGL compatible graphic card drivers.
      
   BUILDING:
   ---------

   For Mac OS are special files inside the directory osx from root. There is also a
   project file. Frretype and SDL are included there.
   
   All other compile the code like:

   Building for soundsupport and no Nvidia-related specs are standard.
   Please don't use enable-nvidia (it's only for testing.....)
   A build for more generic cards is in progress.

   For compilation from source you need the gnu autoconf and automake packages.
   After unpacking the sourceball change to the foobillardplus directory and
   type the follwing commands.

    aclocal --force  
    autoconf -f  
    autoheader -f  
    automake -a -c -f  

   simply type in main-directory (for standard-installation):

    ./configure  
    make  
    make install  
   
   A special very fast version is build with
   
    ./configure --enable-special  
    make  
    make install  

   if you want to enable the special WeTab Version type:

    ./configure --enable-wetab  
    make  
    make install  

   That version would be run only on a WeTab Tablet-PC

   Troublshooting:

   On problems in compiling change to the foobillardplus directory
   and type again

    aclocal --force  
    autoconf -f  
    autoheader -f  
    automake -a -c -f  
   
   There are some special options for ./configure:
   -----------------------------------------------
   
    --enable-wetab
   
   This builds a version for the german tablet WeTab (and only for that!!)
   Please don't use other optimization flags discussed later in this document,
   because this option is the only one you need!!
   
    --enable-touch
   
   This build a special version for generic touch-devices. It is set too with the
   --enable-wetab and also needed there.
   
    --enable-mathsingle=ARG
   
   compile math single precision (default=yes). if you use "no" it is compiled for
   math double precision. Clients with mixed single or double precision are not
   compatible in network games!!!

    --enable-fastmath
   
   compile fast math routine in (default=yes). With set this configure option, special
   optimized math-routines for cosine, sine, tangens are used. it has nothing to do
   with sse intrinsincs. The fast math routines are not nearly as accurate as the
   standard routines, but enough for the game.

    --enable-sse=ARG
   
   compile with intrinsics SSE commands and use. With enabled SSE, the use of
   enable-mathsingle defaults to yes. Double precision are automatically disabled.
   Use sse only on Intel or AMD based CPU systems!

   
    --enable-network=ARG
   
   compile for IP-network game support (default=yes). With no as argument, all
   network support is not compiled.
   
    --enable-sound=ARG
   
   enable sound (default=yes). With no as argument sound support is not compiled.
   
    --enable-win
   
   if set the source is compiling for ms-windows (32 and 64 Bit). You have to use
   as runtime environment MinGW/Msys under MS-Windows.
   http://sourceforge.net/projects/mingw
   
   Optimization problem of the gcc-suite (don't use with WeTab compiling!)
   -----------------------------------------------------------------------
   
   On many systems some optimizations with gcc generate not really stable code. To
   solve the problem, there are only a few optimizations (or none) really recommended.
   Here are the terminal code, to see which optimizations are possible on the target
   machine
   
     gcc -c -Q -O3 --help=optimizers > /tmp/O3-opts

   Have a look on the generated file for available optimizations on your system. Please
   be carefull to use them. Don't mix the following switches for optimizations in one
   configure call.
   
   With the configure script the following switches are available
   
    --enable-standard
   
   Here are the gcc optimizations CFLAGS from the systems are used. The default is no.
   
    --enable-special
   
   This switch uses some special level of optimizations and will produce hopefully a
   stable program. Default is no.
   
    --enable-optimization
   
   With this switch the highest optimization level is used. Be carefull. There is no
   guarantee from the author, that this produce a stable program. But a very quick
   program is compiling. 