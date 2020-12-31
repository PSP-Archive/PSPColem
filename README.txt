
    Welcome to PSPColem

Original Author of ColEm

  Marat Fayzullin

Author of the PSP port version 

  Ludovic.Jacomme also known as Zx-81 (zx81.zx81@gmail.com)


1. INTRODUCTION
   ------------

  ColEm is one of the best emulator of the ColecoVision videogame system
  running on FreeBSD, HP-UX, SunOS, Solaris, Linux, and other Unix systems. 
  There are also ports to MacOS, MSDOS, Windows, OS/2, PocketPC and other 
  systems. See http://fms.komkon.org/ColEm/ for further informations.

  PSPColem is a port on PSP of the Unix version 1.0 of ColEm.

  Thanks to Danzel and Jeff Chen for their virtual keyboard,
  and to all PSPSDK developpers.

  *** Special thanks ***

  -> Fredjmh123 for his advices on the sound support ! ***
  -> Crait for his work on graphics for previous versions

  This version of PSPColem supports IRDA-Joystick box designed by
  my good friend Buzz ( see http://buzz.computer.free.fr ). 
  Schematic and PIC source code is provided in contrib folder.

  
  This package is under GPL Copyright, read COPYING file for
  more information about it.


2. INSTALLATION
   ------------

  Unzip the zip file, and copy the content of the directory fw5.x or fw1.5
  (depending of the version of your firmware) on the psp/game, psp/game150, or
  psp/game5xx if you use custom firmware 5.xx-M33.

  It has been developped on linux for Firmware 5.01-m33 and i hope it works also
  for all others M33 firmwares.

  Put your rom image files on "roms" sub-directory.

  For any comments or questions on this version, please visit
  http://zx81.zx81.free.fr or http://zx81.dcemu.co.uk


3. CONTROL
   ------------

3.1 - Virtual keyboard

  In the ColecoVision emulator window

  Normal mapping :

    PSP        ColecoVision 
  
    Triangle   1
    Square     2
    Cross      FIRE1
    Circle     FIRE2
    Up         Up
    Down       Down
    Left       Left
    Right      Right

    LTrigger   Toogle with L keyboard mapping
    RTrigger   Toggle with R keyboard mapping

  LTrigger mapping :

    PSP        ColecoVision 
  
    Square     Fps
    Triangle   Load state
    Cross      Save state
    Circle     Swap analog / pad
    Up         Inc delta
    Down       Dec delta
    Left       Render mode
    Right      Render mode

  RTrigger mapping :

    PSP        ColecoVision 
  
    Square     Reset
    Triangle   *
    Cross      Auto-fire
    Circle     FIRE2
    Up         0
    Down       3
    Left       Dec Fire
    Right      Inc Fire

    A-Pad      Joystick
  
    Press Start  + L + R   to exit and return to eloader.
    Press Select           to enter in emulator main menu.
    Press Start            open/close the On-Screen keyboard

  In the main menu

    L+R+Start  Exit the emulator
    R Trigger  Reset the ColecoVision console

    Triangle   Go Up directory
    Cross      Valid
    Circle     Valid
    Square     Go Back to the emulator window

  The On-Screen Keyboard of "Danzel" and "Jeff Chen"

    Use Analog stick to choose one of the 9 squares, and
    use Triangle, Square, Cross and Circle to choose one
    of the 4 letters of the highlighted square.

3.2 - IR keyboard

  You can also use IR keyboard. Edit the pspirkeyb.ini file
  to specify your IR keyboard model, and modify eventually
  layout keyboard files in the keymap directory.

  The following mapping is done :

  IR-keyboard   PSP

  Cursor        Digital Pad

  Tab           Start
  Ctrl-W        Start

  Escape        Select
  Ctrl-Q        Select

  Ctrl-E        Triangle
  Ctrl-X        Cross
  Ctrl-S        Square
  Ctrl-F        Circle
  Ctrl-Z        L-trigger
  Ctrl-C        R-trigger

  In the emulator window you can use the IR keyboard for
  cursor keys (but it doesn't work well).


4. LOADING COLECOVISION ROM FILES
   ------------

  If you want to load rom image in your emulator, you have to put your rom file
  (with .zip, or .rom file extension) on your PSP memory stick in the 'rom' 
  directory.

  Then, while inside PSPColem emulator, just press SELECT to enter in 
  the emulator main menu, and then using the file selector choose one 
  rom file to load in your emulator.

  Back to the emulator window, the rom should start automatically.

  You can use the virtual keyboard in the file requester menu to choose the
  first letter of the game you search (it might be useful when you have tons of
  games in the same folder). 

  Entering several time the same letter let you choose sequentially files
  beginning with the given letter. You can use the Run key of the virtual
  keyboard to launch the rom.

  You may use the Trigger key to swap between the two virtual keyboard panels
  (numbers & letters)


5. LOADING KEY MAPPING FILES
   ------------

  For given games, the default keyboard mapping between PSP Keys and
  ColecoVision keys, is not suitable, and the game can't be played on PSPColem.

  To overcome the issue, you can write your own mapping file. Using notepad for
  example you can edit a file with the .kbd extension and put it in the kbd 
  directory.

  For the exact syntax of those mapping files, have a look on sample files already
  presents in the kbd directory (default.kbd etc ...).

  After writting such keyboard mapping file, you can load them using the main menu
  inside the emulator.

  If the keyboard filename is the same as the rom filename (.zip etc ...)
  then when you load this rom, the corresponding keyboard file is automatically 
  loaded !

  You can now use the Keyboard menu and edit, load and save your
  keyboard mapping files inside the emulator. The Save option save the .kbd
  file in the kbd directory using the "Game Name" as filename. The game name
  is displayed on the right corner in the emulator menu.


6. CHEAT CODE (.CHT)
   ----------

  You can use cheat codes with PSP-Colem You can add your own cheat codes in the
  cheat.txt file and then import them in the cheat menu.

  All cheat codes you have specified for a game can be save in a CHT file 
  in 'cht' folder.  Those cheat codes would then be automatically loaded
  when you start the game.

  The CHT file format is the following :
  #
  # Enable, Address, Value, Comment
  #
  1,36f,3,Cheat comment

  Using the Cheat menu you can search for modified bytes in RAM between
  current time and the last time you saved the RAM. It might be very usefull to
  find "poke" address by yourself, monitoring for example life numbers.

  To find a new "poke address" you can proceed as follow :

  Let's say you're playing Zaxxon and you want to find the memory
  address where "number lives" is stored.

  . Start a new game in Zaxxon
  . Enter in the cheat menu. 
  . Choose Save Ram to save initial state of the memory. 
  . Specify the number of lives you want to find in
    "Scan Old Value" field.
    (for Zaxxon the initial lives number is 4)
  . Go back to the game and loose a life.
  . Enter in the cheat menu. 
  . Specify the number of lives you want to find in
    "Scan New Value" field.
    (for Zaxxon the lives number is now 3)
  . In Add Cheat you have several matching Addresses
  . Specify the Poke value you want (for example 6) 
    and add six new cheats with this address / value.
  . Try them one by one to identify what is the good
    one, while restarting new games and see if the 
    life number is 4 or 6. You will see that the good
    address is 717D. You can delete all others.

  The cheat is now activated in the cheat list 
  and you can save it using the "Save cheat" menu.

  Let's enjoy Zaxxon with infinite life !!

7. COMMENTS
   ------------

You can write your own comments for games using the "Comment" menu.  The first
line of your comments would then be displayed in the file requester menu while
selecting the given file name (roms, keyboard, settings).

8. SETTINGS
   ------------

You can modify several settings value in the settings
menu of this emulator.  The following parameters are
available :

  Sound enable : 
    enable or disable the sound

  IRDA device  : 
    type of IRDA device connected to PSP
    It could be None, Keyboard (such as Targus) 
    or Joystick (see IRDA Joy section)

  Speed limiter :
    limit the speed to a given fps value

  Skip frame : 
    to skip frame and increase emulator speed

  Display fps : 
    display real time fps value 

  Render mode : 
    many render modes are available with different
    geometry that should covered all games
    requirements

  Delta Y : 
    move the center of the screen vertically

  Vsync : 
    wait for vertical signal between each frame displayed

  Display LR led : 
    draw a small blue rectangle in top of the screen
    when trigger keys are pressed

  Clock frequency : 
    PSP clock frequency, by default the value is set
    to 133Mhz, and should be enough for most of all
    games.

10. JOYSTICK SETTINGS
   ------------

  You can modify several joystick settings value in the settings menu of this emulator.
  The following parameters are available :

  Swap Analog/Cursor : swap key mapping between PSP analog pad and PSP digital pad
  Auto fire period   : auto fire period
  Auto fire mode     : auto fire mode active or not

  See IRDA-Joy section for other parameters description.


11. IRDA-JOY SETTINGS
   ------------

  This version of PSPColem supports IRDA-Joystick box
  ( see http://buzz.computer.free.fr for all details ). 

  IRDA mode   : type of DB9 device connected to the "Irda Joystick box". It could be None, 
                Joystick, Single or double paddle.
  IRDA debug  : enable or disable debug mode to display data sent by the "Irda Joystick box".

  You can then define Irda Joystick box keys mapping to PSP keys. The default
  mapping is the following : 

  Joy Up             : Digital Up
  Joy Down           : Digital Down 
  Joy Left           : Digital Left
  Joy Right          : Digital Right
  Joy Fire           : Cross
  Paddle 1 +         : Analog Right
  Paddle 1 -         : Analog Left
  Paddle 1 Fire      : Cross
  Paddle 2 +         : Analog Up
  Paddle 2 -         : Analog Down
  Paddle 2 Fire      : Circle


12. COMPILATION
   ------------

  It has been developped under Linux using gcc with PSPSDK. 
  To rebuild the homebrew run the Makefile in the src archive.
