# esp8266-xtensa-toolchain
install esp8266 xtensa toolchain

video tutorial https://www.youtube.com/watch?v=9k2NUEowhUg from where im inspired ... thank you!

--------------------------------------------------------------------------------------------------------

page tutorial https://docs.espressif.com/projects/esp8266-rtos-sdk/en/latest/get-started/windows-setup.html

download Toolchain Setup https://dl.espressif.com/dl/esp32_win32_msys2_environment_and_toolchain-20181001.zip

extract
                        
copy msys32 folder directly to C:

apri command prompt and write this  
                        
\msys32\mingw32   << this command will open migw32 window
                        
                        next all commands one by one in new opened mingw32 window
                        -------------------------------------
                        mkdir -p ~/esp  >>  this command will create esp folder in C:\msys32\home\user directory
                        cd ~/esp   >> this command will go to this directory
now download and extract 

Download the toolchain for the ESP8266
v8.4.0

https://dl.espressif.com/dl/xtensa-lx106-elf-gcc8_4_0-esp-2020r3-win32.zip

and copy xtensa-lx106-elf folder to esp folder

and continue with commands in mingw32 window
                        continue with all commands one by one in new opened mingw32 window
                        -------------------------------------
                        export PATH="$PATH:$HOME/esp/xtensa-lx106-elf/bin"  >> create environment path 
                        printenv PATH  >> verify if is created 
                        git clone --recursive https://github.com/espressif/ESP8266_RTOS_SDK.git >> this command will install ESP8266_RTOS_SDK in esp folder
                        export IDF_PATH="$HOME/esp/ESP8266_RTOS_SDK"  >>create environment path IDF_PATH
                        printenv IDF_PATH  >> verify if is created
                        python --version   >>see python version
                        python2.7 -m pip install --user -r $IDF_PATH/requirements.txt  >> install requirements
                        dir  >> verify 
                        cd ESP8266_RTOS_SDK/   >> goto ESP8266_RTOS_SDK directory
                        cd examples  >> goto examples
                        dir  >> list
                        cd get-started  >> go to get-started
                        dir  >list
                        cd ~/esp  >> go to esp directory
                        cp -r $IDF_PATH/examples/get-started/hello_world .  >> copy hello_world to esp directory
                        cd hello_world   >> go to hello_world directory
                        make menuconfig  >> open menuconfig and set port where is connect module esp8266
                        make flash  >> compile and flash esp8266

-----------------------------------------------------------------------------------------------------
bellow a copy of all commands and response in mingw32
 i put > where i inserted command ( for watch easy )
----------------------------------------------------------------------------------------------------------

Copying skeleton files.
These files are for the users to personalise their msys2 experience.

They will never be overwritten nor automatically updated.

'./.bashrc' -> '/home/costycnc/.bashrc'
'./.bash_logout' -> '/home/costycnc/.bash_logout'
'./.bash_profile' -> '/home/costycnc/.bash_profile'
'./.inputrc' -> '/home/costycnc/.inputrc'
'./.profile' -> '/home/costycnc/.profile'
'./.vimrc' -> '/home/costycnc/.vimrc'

costycnc@costycnc-PC MINGW32 ~
>command   mkdir -p ~/esp

costycnc@costycnc-PC MINGW32 ~
>command   cd ~/esp

costycnc@costycnc-PC MINGW32 ~/esp
$

costycnc@costycnc-PC MINGW32 ~/esp
>command  export PATH="$PATH:$HOME/esp/xtensa-lx106-elf/bin"

costycnc@costycnc-PC MINGW32 ~/esp
>command   printenv PATH

/mingw32/bin:/usr/local/bin:/usr/bin:/bin:/c/Windows/System32:/c/Windows:/c/Windows/System32/Wbem:/c/Windows/System32/WindowsPowerShell/v1.0/:/opt/xtensa-esp32-elf/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/home/costycnc/esp/xtensa-lx106-elf/bin

costycnc@costycnc-PC MINGW32 ~/esp
>command git clone --recursive https://github.com/espressif/ESP8266_RTOS_SDK.git

Cloning into 'ESP8266_RTOS_SDK'...
remote: Enumerating objects: 29400, done.
remote: Counting objects: 100% (870/870), done.
remote: Compressing objects: 100% (402/402), done.
remote: Total 29400 (delta 500), reused 783 (delta 454), pack-reused 28530
Receiving objects: 100% (29400/29400), 63.88 MiB | 6.31 MiB/s, done.
Resolving deltas: 100% (17046/17046), done.
Checking out files: 100% (2880/2880), done.
Submodule 'components/coap/libcoap' (https://github.com/obgm/libcoap.git) registered for path 'components/coap/libcoap'
Submodule 'components/json/cJSON' (https://github.com/DaveGamble/cJSON.git) registered for path 'components/json/cJSON'
Submodule 'components/lwip/lwip' (https://github.com/espressif/esp-lwip.git) registered for path 'components/lwip/lwip'
Submodule 'components/mbedtls/mbedtls' (https://github.com/espressif/mbedtls.git) registered for path 'components/mbedtls/mbedtls'
Submodule 'components/mqtt/esp-mqtt' (https://github.com/espressif/esp-mqtt.git) registered for path 'components/mqtt/esp-mqtt'
Cloning into '/home/costycnc/esp/ESP8266_RTOS_SDK/components/coap/libcoap'...
remote: Enumerating objects: 13850, done.
remote: Counting objects: 100% (131/131), done.
remote: Compressing objects: 100% (90/90), done.
remote: Total 13850 (delta 47), reused 89 (delta 33), pack-reused 13719
Receiving objects: 100% (13850/13850), 5.97 MiB | 4.28 MiB/s, done.
Resolving deltas: 100% (9952/9952), done.
Cloning into '/home/costycnc/esp/ESP8266_RTOS_SDK/components/json/cJSON'...
remote: Enumerating objects: 4545, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (42/42), done.
remote: Total 4545 (delta 29), reused 37 (delta 17), pack-reused 4486
Receiving objects: 100% (4545/4545), 2.49 MiB | 4.05 MiB/s, done.
Resolving deltas: 100% (3014/3014), done.
Cloning into '/home/costycnc/esp/ESP8266_RTOS_SDK/components/lwip/lwip'...
remote: Enumerating objects: 51107, done.
remote: Counting objects: 100% (1138/1138), done.
remote: Compressing objects: 100% (439/439), done.
remote: Total 51107 (delta 786), reused 952 (delta 673), pack-reused 49969      
Receiving objects: 100% (51107/51107), 10.46 MiB | 3.07 MiB/s, done.
Resolving deltas: 100% (38530/38530), done.
Cloning into '/home/costycnc/esp/ESP8266_RTOS_SDK/components/mbedtls/mbedtls'...
remote: Enumerating objects: 155351, done.
remote: Total 155351 (delta 0), reused 0 (delta 0), pack-reused 155351
Receiving objects: 100% (155351/155351), 73.21 MiB | 4.84 MiB/s, done.
Resolving deltas: 100% (120218/120218), done.
Cloning into '/home/costycnc/esp/ESP8266_RTOS_SDK/components/mqtt/esp-mqtt'...
remote: Enumerating objects: 2837, done.
remote: Counting objects: 100% (547/547), done.
remote: Compressing objects: 100% (265/265), done.
remote: Total 2837 (delta 313), reused 506 (delta 277), pack-reused 2290
Receiving objects: 100% (2837/2837), 1.61 MiB | 3.04 MiB/s, done.
Resolving deltas: 100% (1544/1544), done.
Submodule path 'components/coap/libcoap': checked out 'cfec0d072c5b99ed3e54828ca50ea2f6b91e1f50'
Submodule 'ext/tinydtls' (https://git.eclipse.org/r/tinydtls/org.eclipse.tinydtls) registered for path 'components/coap/libcoap/ext/tinydtls'
Cloning into '/home/costycnc/esp/ESP8266_RTOS_SDK/components/coap/libcoap/ext/tinydtls'...
remote: Total 584 (delta 0), reused 584 (delta 0)        B/s
Receiving objects: 100% (584/584), 604.89 KiB | 457.00 KiB/s, done.
Resolving deltas: 100% (259/259), done.
Submodule path 'components/coap/libcoap/ext/tinydtls': checked out '3b24a701ed5b0785306aa732e739ecb1eb3d03f8'
Submodule path 'components/json/cJSON': checked out '3c8935676a97c7c97bf006db8312875b4f292f6c'
Submodule path 'components/lwip/lwip': checked out '4fd84abace0cd8a5a709c194fa54afb3cd39b3f7'
Submodule path 'components/mbedtls/mbedtls': checked out '9ef92c551eb8d92677034c3ec8078a8076febf41'
Submodule path 'components/mqtt/esp-mqtt': checked out '01594bf118ae502b5a0ead040446f2be75d26223'

costycnc@costycnc-PC MINGW32 ~/esp
>command export IDF_PATH="$HOME/esp/ESP8266_RTOS_SDK"

costycnc@costycnc-PC MINGW32 ~/esp
>command printenv IDF_PATH

/home/costycnc/esp/ESP8266_RTOS_SDK

costycnc@costycnc-PC MINGW32 ~/esp
>command python --version

Python 2.7.15

costycnc@costycnc-PC MINGW32 ~/esp
>command python2.7 -m pip install --user -r $IDF_PATH/requirements.txt

Requirement already satisfied: setuptools in c:/msys32/mingw32/lib/python2.7/site-packages (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 4)) (40.4.3)
Collecting click>=5.0 (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 8))
  Downloading https://files.pythonhosted.org/packages/d2/3d/fa76db83bf75c4f8d338c2fd15c8d33fdd7ad23a9b5e57eb6c5de26b430e/click-7.1.2-py2.py3-none-any.whl (82kB)
    100% |################################| 92kB 1.5MB/s
Requirement already satisfied: pyserial>=3.0 in c:/msys32/mingw32/lib/python2.7/site-packages (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 9)) (3.4)
Requirement already satisfied: future>=0.15.2 in c:/msys32/mingw32/lib/python2.7/site-packages (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 10)) (0.16.0)
Requirement already satisfied: cryptography<35,>=2.1.4 in c:/msys32/mingw32/lib/python2.7/site-packages (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (2.3.1)
Requirement already satisfied: pyparsing<2.4.0,>=2.0.3 in c:/msys32/mingw32/lib/python2.7/site-packages (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 12)) (2.2.0)
Collecting pyelftools>=0.22 (from -r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 13))
  Downloading https://files.pythonhosted.org/packages/04/7c/867630e6e6293793f838b31034aa1875e1c3bd8c1ec34a0929a2506f350c/pyelftools-0.29-py2.py3-none-any.whl (174kB)
    100% |################################| 184kB 2.2MB/s
Requirement already satisfied: idna>=2.1 in c:/msys32/mingw32/lib/python2.7/site-packages (from cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (2.7)
Requirement already satisfied: asn1crypto>=0.21.0 in c:/msys32/mingw32/lib/python2.7/site-packages (from cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (0.24.0)
Requirement already satisfied: six>=1.4.1 in c:/msys32/mingw32/lib/python2.7/site-packages (from cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (1.11.0)
Requirement already satisfied: cffi!=1.11.3,>=1.7 in c:/msys32/mingw32/lib/python2.7/site-packages (from cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (1.10.0)
Requirement already satisfied: enum34 in c:/msys32/mingw32/lib/python2.7/site-packages (from cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (1.1.6)
Requirement already satisfied: ipaddress in c:/msys32/mingw32/lib/python2.7/site-packages (from cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (1.0.22)
Requirement already satisfied: pycparser in c:/msys32/mingw32/lib/python2.7/site-packages (from cffi!=1.11.3,>=1.7->cryptography<35,>=2.1.4->-r C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt (line 11)) (2.19)
Installing collected packages: click, pyelftools
Successfully installed click-7.1.2 pyelftools-0.29

costycnc@costycnc-PC MINGW32 ~/esp
> dir
ESP8266_RTOS_SDK  xtensa-lx106-elf

costycnc@costycnc-PC MINGW32 ~/esp
> cd ESP8266_RTOS_SDK/

costycnc@costycnc-PC MINGW32 ~/esp/ESP8266_RTOS_SDK
> cd examples

costycnc@costycnc-PC MINGW32 ~/esp/ESP8266_RTOS_SDK/examples
> dir

common_components  peripherals  provisioning  storage  wifi
get-started        protocols    README.md     system

costycnc@costycnc-PC MINGW32 ~/esp/ESP8266_RTOS_SDK/examples
> cd get-started

costycnc@costycnc-PC MINGW32 ~/esp/ESP8266_RTOS_SDK/examples/get-started
> dir

hello_world

costycnc@costycnc-PC MINGW32 ~/esp/ESP8266_RTOS_SDK/examples/get-started
> cd ~/esp

costycnc@costycnc-PC MINGW32 ~/esp
> cp -r $IDF_PATH/examples/get-started/hello_world .

costycnc@costycnc-PC MINGW32 ~/esp
> cd hello_world

costycnc@costycnc-PC MINGW32 ~/esp/hello_world
> make menuconfig

make[1]: Entering directory '/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig'
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/mconf.c -o mconf.o
flex -L -Pzconf -ozconf.lex.c /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/zconf.l
bison -t -l -p zconf -o zconf.tab.c /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/zconf.y
sed -E "s/\\x0D$//" /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/zconf.gperf | gperf -t --output-file zconf.hash.c -a -C -E -g -k '1,3,$' -p -t
/usr/bin/gcc -I /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  zconf.tab.c -o zconf.tab.o
/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/check-lxdialog.sh -check /usr/bin/gcc  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig" -lncursesw -lintl
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/checklist.c -o lxdialog/checklist.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/util.c -o lxdialog/util.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/inputbox.c -o lxdialog/inputbox.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/textbox.c -o lxdialog/textbox.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/yesno.c -o lxdialog/yesno.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/menubox.c -o lxdialog/menubox.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/expand_env.c -o expand_env.o
/usr/bin/gcc -o mconf-idf mconf.o zconf.tab.o lxdialog/checklist.o lxdialog/util.o lxdialog/inputbox.o lxdialog/textbox.o lxdialog/yesno.o lxdialog/menubox.o expand_env.o -lncursesw -lintl
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/conf.c -o conf.o
/usr/bin/gcc -o conf-idf conf.o  zconf.tab.o expand_env.o -lncursesw -lintl
make[1]: Leaving directory '/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig'
make[1]: Entering directory '/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig'
/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/check-lxdialog.sh -check /usr/bin/gcc  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig" -lncursesw -lintl
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/checklist.c -o lxdialog/checklist.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/util.c -o lxdialog/util.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/inputbox.c -o lxdialog/inputbox.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/textbox.c -o lxdialog/textbox.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/yesno.c -o lxdialog/yesno.o
/usr/bin/gcc -c  -I/usr/include/ncursesw -DCURSES_LOC="<curses.h>"  -DNCURSES_WIDECHAR=1 -DLOCALE -MMD -MP -I "." -I "/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig"  /home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig/lxdialog/menubox.c -o lxdialog/menubox.o
/usr/bin/gcc -o mconf-idf mconf.o zconf.tab.o lxdialog/checklist.o lxdialog/util.o lxdialog/inputbox.o lxdialog/textbox.o lxdialog/yesno.o lxdialog/menubox.o expand_env.o -lncursesw -lintl
make[1]: Leaving directory '/home/costycnc/esp/ESP8266_RTOS_SDK/tools/kconfig'
Python requirements from C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt are satisfied.
DEFCONFIG
MENUCONFIG


*** End of the configuration.
*** Execute 'make' to start the build or try 'make help'.

GENCONFIG
Project is not inside a git repository, or git repository has no commits
will not use 'git describe' to determine PROJECT_VER.
App "hello-world" version: 1

costycnc@costycnc-PC MINGW32 ~/esp/hello_world
> make flash

Toolchain path: /home/costycnc/esp/xtensa-lx106-elf/bin/xtensa-lx106-elf-gcc
Toolchain version: esp-2020r3-49-gd5524c1
Compiler version: 8.4.0
Python requirements from C:/msys32/home/costycnc/esp/ESP8266_RTOS_SDK/requirements.txt are satisfied.
CC build/bootloader/main/bootloader_start.o
AR build/bootloader/main/libmain.a
CC build/bootloader/bootloader_support/src/bootloader_random.o
CC build/bootloader/bootloader_support/src/flash_encrypt.o
CC build/bootloader/bootloader_support/src/bootloader_sha.o
CC build/bootloader/bootloader_support/src/esp_image_format.o
CC build/bootloader/bootloader_support/src/flash_partitions.o
CC build/bootloader/bootloader_support/src/secure_boot_signatures.o
CC build/bootloader/bootloader_support/src/bootloader_clock.o
CC build/bootloader/bootloader_support/src/secure_boot.o
CC build/bootloader/bootloader_support/src/bootloader_common.o
CC build/bootloader/bootloader_support/src/bootloader_utility.o
CC build/bootloader/bootloader_support/src/bootloader_init.o
CC build/bootloader/bootloader_support/src/efuse.o
CC build/bootloader/bootloader_support/src/flash_qio_mode.o
CC build/bootloader/bootloader_support/src/bootloader_flash.o
AR build/bootloader/bootloader_support/libbootloader_support.a
CC build/bootloader/spi_flash/src/spi_flash.o
CC build/bootloader/spi_flash/src/spi_flash_raw.o
CC build/bootloader/spi_flash/port/port.o
AR build/bootloader/spi_flash/libspi_flash.a
CC build/bootloader/log/log.o
AR build/bootloader/log/liblog.a
CC build/bootloader/esp8266/source/ets_printf.o
CC build/bootloader/esp8266/source/crc.o
CC build/bootloader/esp8266/source/esp_fast_boot.o
AR build/bootloader/esp8266/libesp8266.a
LD build/bootloader/bootloader.elf
esptool.py v2.4.0
Building partitions from /home/costycnc/esp/ESP8266_RTOS_SDK/components/partition_table/partitions_singleapp.csv...
Project is not inside a git repository, or git repository has no commits
will not use 'git describe' to determine PROJECT_VER.
App "hello-world" version: 1
CC build/app_update/esp_app_desc.o
CC build/app_update/esp_ota_ops.o
AR build/app_update/libapp_update.a
CC build/bootloader_support/src/bootloader_random.o
CC build/bootloader_support/src/flash_encrypt.o
CC build/bootloader_support/src/bootloader_sha.o
CC build/bootloader_support/src/esp_image_format.o
CC build/bootloader_support/src/flash_partitions.o
CC build/bootloader_support/src/secure_boot_signatures.o
CC build/bootloader_support/src/bootloader_clock.o
CC build/bootloader_support/src/secure_boot.o
CC build/bootloader_support/src/bootloader_common.o
CC build/bootloader_support/src/bootloader_utility.o
CC build/bootloader_support/src/bootloader_init.o
CC build/bootloader_support/src/efuse.o
CC build/bootloader_support/src/flash_qio_mode.o
CC build/bootloader_support/src/bootloader_flash.o
AR build/bootloader_support/libbootloader_support.a
AR build/coap/libcoap.a
CC build/console/linenoise/linenoise.o
CC build/console/argtable3/argtable3.o
CC build/console/commands.o
CC build/console/split_argv.o
AR build/console/libconsole.a
CC build/esp-tls/esp_tls.o
CC build/esp-tls/esp_tls_mbedtls.o
AR build/esp-tls/libesp-tls.a
AR build/esp-wolfssl/libesp-wolfssl.a
CC build/esp8266/driver/adc.o
CC build/esp8266/driver/i2c.o
CC build/esp8266/driver/gpio.o
CC build/esp8266/driver/ledc.o
CC build/esp8266/driver/spi.o
CC build/esp8266/driver/i2s.o
CC build/esp8266/driver/pwm.o
CC build/esp8266/driver/hspi_logic_layer.o
CC build/esp8266/driver/uart.o
CC build/esp8266/driver/ir_tx.o
CC build/esp8266/driver/ir_rx.o
CC build/esp8266/driver/hw_timer.o
CC build/esp8266/source/startup.o
CC build/esp8266/source/esp_sleep.o
CC build/esp8266/source/esp_timer.o
CC build/esp8266/source/hw_random.o
CC build/esp8266/source/esp_fast_boot.o
CC build/esp8266/source/chip_boot.o
CC build/esp8266/source/esp_wifi_os_adapter.o
CC build/esp8266/source/smartconfig_ack.o
CC build/esp8266/source/ets_printf.o
CC build/esp8266/source/rom.o
CC build/esp8266/source/esp_wifi.o
CC build/esp8266/source/phy_init.o
CC build/esp8266/source/esp_fsleep.o
CC build/esp8266/source/system_api.o
CC build/esp8266/source/backtrace.o
CC build/esp8266/source/crc.o
CC build/esp8266/source/smartconfig.o
CC build/esp8266/source/task_wdt.o
CC build/esp8266/source/reset_reason.o
AR build/esp8266/libesp8266.a
CC build/esp_common/src/stack_check.o
CC build/esp_common/src/esp_err_to_name.o
AR build/esp_common/libesp_common.a
CC build/esp_event/esp_event_private.o
CC build/esp_event/event_loop_legacy.o
CC build/esp_event/esp_event.o
CC build/esp_event/event_send.o
CC build/esp_event/default_event_loop.o
AR build/esp_event/libesp_event.a
CC build/esp_gdbstub/src/gdbstub.o
CC build/esp_gdbstub/src/packet.o
CC build/esp_gdbstub/esp8266/gdbstub_esp8266.o
CC build/esp_gdbstub/xtensa/gdbstub_xtensa.o
AR build/esp_gdbstub/libesp_gdbstub.a
CC build/esp_http_client/esp_http_client.o
CC build/esp_http_client/lib/http_utils.o
CC build/esp_http_client/lib/http_auth.o
CC build/esp_http_client/lib/http_header.o
AR build/esp_http_client/libesp_http_client.a
CC build/esp_http_server/src/httpd_sess.o
CC build/esp_http_server/src/httpd_parse.o
CC build/esp_http_server/src/httpd_uri.o
CC build/esp_http_server/src/httpd_txrx.o
CC build/esp_http_server/src/httpd_main.o
CC build/esp_http_server/src/util/ctrl_sock.o
AR build/esp_http_server/libesp_http_server.a
CC build/esp_https_ota/src/esp_https_ota.o
AR build/esp_https_ota/libesp_https_ota.a
CC build/esp_ringbuf/ringbuf.o
AR build/esp_ringbuf/libesp_ringbuf.a
CC build/fatfs/diskio/diskio.o
CC build/fatfs/diskio/diskio_rawflash.o
CC build/fatfs/diskio/diskio_wl.o
CC build/fatfs/vfs/vfs_fat.o
CC build/fatfs/vfs/vfs_fat_spiflash.o
CC build/fatfs/port/freertos/ffsystem.o
CC build/fatfs/src/ffunicode.o
CC build/fatfs/src/ff.o
AR build/fatfs/libfatfs.a
CC build/freemodbus/common/esp_modbus_slave_tcp.o
CC build/freemodbus/common/esp_modbus_slave.o
CC build/freemodbus/common/esp_modbus_master_tcp.o
CC build/freemodbus/common/esp_modbus_master.o
CC build/freemodbus/modbus/mb.o
CC build/freemodbus/modbus/mb_m.o
CC build/freemodbus/modbus/ascii/mbascii_m.o
CC build/freemodbus/modbus/ascii/mbascii.o
CC build/freemodbus/modbus/functions/mbutils.o
CC build/freemodbus/modbus/functions/mbfuncholding_m.o
CC build/freemodbus/modbus/functions/mbfunccoils_m.o
CC build/freemodbus/modbus/functions/mbfunccoils.o
CC build/freemodbus/modbus/functions/mbfuncdisc_m.o
CC build/freemodbus/modbus/functions/mbfuncdiag.o
CC build/freemodbus/modbus/functions/mbfuncother.o
CC build/freemodbus/modbus/functions/mbfuncdisc.o
CC build/freemodbus/modbus/functions/mbfuncinput_m.o
CC build/freemodbus/modbus/functions/mbfuncinput.o
CC build/freemodbus/modbus/functions/mbfuncholding.o
CC build/freemodbus/modbus/rtu/mbrtu.o
CC build/freemodbus/modbus/rtu/mbcrc.o
CC build/freemodbus/modbus/rtu/mbrtu_m.o
CC build/freemodbus/modbus/tcp/mbtcp.o
CC build/freemodbus/modbus/tcp/mbtcp_m.o
CC build/freemodbus/tcp_slave/port/port_tcp_slave.o
CC build/freemodbus/tcp_slave/modbus_controller/mbc_tcp_slave.o
CC build/freemodbus/tcp_master/port/port_tcp_master.o
CC build/freemodbus/tcp_master/modbus_controller/mbc_tcp_master.o
CC build/freemodbus/port/portevent.o
CC build/freemodbus/port/porttimer.o
CC build/freemodbus/port/port.o
CC build/freemodbus/port/portother.o
CC build/freemodbus/port/porttimer_m.o
CC build/freemodbus/port/portother_m.o
CC build/freemodbus/port/portevent_m.o
AR build/freemodbus/libfreemodbus.a
CC build/freertos/port/esp8266/port.o
CC build/freertos/port/esp8266/freertos_hooks.o
CC build/freertos/port/esp8266/panic.o
CC build/freertos/freertos/timers.o
CC build/freertos/freertos/tasks.o
CC build/freertos/freertos/event_groups.o
CC build/freertos/freertos/stream_buffer.o
CC build/freertos/freertos/list.o
CC build/freertos/freertos/queue.o
AS build/freertos/port/esp8266/xtensa_vectors.o
AS build/freertos/port/esp8266/os_cpu_a.o
AS build/freertos/port/esp8266/xtensa_context.o
AR build/freertos/libfreertos.a
CC build/heap/src/esp_heap_trace.o
CC build/heap/src/esp_heap_caps.o
CC build/heap/port/esp8266/esp_heap_init.o
AR build/heap/libheap.a
CC build/http_parser/src/http_parser.o
AR build/http_parser/libhttp_parser.a
CC build/jsmn/src//jsmn.o
AR build/jsmn/libjsmn.a
CC build/json/cJSON/cJSON.o
CC build/json/cJSON/cJSON_Utils.o
AR build/json/libjson.a
CC build/libsodium/port/randombytes_esp8266.o
CC build/libsodium/libsodium/src/libsodium/crypto_aead/chacha20poly1305/sodium/aead_chacha20poly1305.o
CC build/libsodium/libsodium/src/libsodium/crypto_aead/xchacha20poly1305/sodium/aead_xchacha20poly1305.o
CC build/libsodium/libsodium/src/libsodium/crypto_auth/crypto_auth.o
CC build/libsodium/libsodium/src/libsodium/crypto_auth/hmacsha256/auth_hmacsha256.o
CC build/libsodium/libsodium/src/libsodium/crypto_auth/hmacsha512/auth_hmacsha512.o
CC build/libsodium/libsodium/src/libsodium/crypto_auth/hmacsha512256/auth_hmacsha512256.o
CC build/libsodium/libsodium/src/libsodium/crypto_box/crypto_box_easy.o
CC build/libsodium/libsodium/src/libsodium/crypto_box/crypto_box.o
CC build/libsodium/libsodium/src/libsodium/crypto_box/crypto_box_seal.o
CC build/libsodium/libsodium/src/libsodium/crypto_box/curve25519xsalsa20poly1305/box_curve25519xsalsa20poly1305.o
CC build/libsodium/libsodium/src/libsodium/crypto_core/curve25519/ref10/curve25519_ref10.o
CC build/libsodium/libsodium/src/libsodium/crypto_core/hchacha20/core_hchacha20.o
CC build/libsodium/libsodium/src/libsodium/crypto_core/hsalsa20/ref2/core_hsalsa20_ref2.o
CC build/libsodium/libsodium/src/libsodium/crypto_core/hsalsa20/core_hsalsa20.o
CC build/libsodium/libsodium/src/libsodium/crypto_core/salsa/ref/core_salsa_ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/crypto_generichash.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/generichash_blake2.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/ref/blake2b-compress-sse41.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/ref/blake2b-ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/ref/blake2b-compress-ssse3.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/ref/blake2b-compress-ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/ref/generichash_blake2b.o
CC build/libsodium/libsodium/src/libsodium/crypto_generichash/blake2b/ref/blake2b-compress-avx2.o
CC build/libsodium/libsodium/src/libsodium/crypto_hash/crypto_hash.o
CC build/libsodium/libsodium/src/libsodium/crypto_hash/sha256/hash_sha256.o
CC build/libsodium/libsodium/src/libsodium/crypto_hash/sha512/hash_sha512.o
CC build/libsodium/libsodium/src/libsodium/crypto_kdf/blake2b/kdf_blake2b.o
CC build/libsodium/libsodium/src/libsodium/crypto_kdf/crypto_kdf.o
CC build/libsodium/libsodium/src/libsodium/crypto_kx/crypto_kx.o
CC build/libsodium/libsodium/src/libsodium/crypto_onetimeauth/crypto_onetimeauth.o
CC build/libsodium/libsodium/src/libsodium/crypto_onetimeauth/poly1305/onetimeauth_poly1305.o
CC build/libsodium/libsodium/src/libsodium/crypto_onetimeauth/poly1305/donna/poly1305_donna.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/argon2-encoding.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/argon2-fill-block-ssse3.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/pwhash_argon2i.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/argon2-fill-block-ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/argon2.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/blake2b-long.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/argon2/argon2-core.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/crypto_pwhash.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/scryptsalsa208sha256/pbkdf2-sha256.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/scryptsalsa208sha256/crypto_scrypt-common.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/scryptsalsa208sha256/pwhash_scryptsalsa208sha256.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/scryptsalsa208sha256/scrypt_platform.o
CC build/libsodium/libsodium/src/libsodium/crypto_pwhash/scryptsalsa208sha256/nosse/pwhash_scryptsalsa208sha256_nosse.o
CC build/libsodium/libsodium/src/libsodium/crypto_scalarmult/crypto_scalarmult.o
CC build/libsodium/libsodium/src/libsodium/crypto_scalarmult/curve25519/scalarmult_curve25519.o
CC build/libsodium/libsodium/src/libsodium/crypto_scalarmult/curve25519/ref10/x25519_ref10.o
CC build/libsodium/libsodium/src/libsodium/crypto_secretbox/crypto_secretbox.o
CC build/libsodium/libsodium/src/libsodium/crypto_secretbox/crypto_secretbox_easy.o
CC build/libsodium/libsodium/src/libsodium/crypto_secretbox/xsalsa20poly1305/secretbox_xsalsa20poly1305.o
CC build/libsodium/libsodium/src/libsodium/crypto_shorthash/crypto_shorthash.o
CC build/libsodium/libsodium/src/libsodium/crypto_shorthash/siphash24/shorthash_siphash24.o
CC build/libsodium/libsodium/src/libsodium/crypto_shorthash/siphash24/shorthash_siphashx24.o
CC build/libsodium/libsodium/src/libsodium/crypto_shorthash/siphash24/ref/shorthash_siphashx24_ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_shorthash/siphash24/ref/shorthash_siphash24_ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_sign/crypto_sign.o
CC build/libsodium/libsodium/src/libsodium/crypto_sign/ed25519/sign_ed25519.o
CC build/libsodium/libsodium/src/libsodium/crypto_sign/ed25519/ref10/keypair.o
CC build/libsodium/libsodium/src/libsodium/crypto_sign/ed25519/ref10/open.o
CC build/libsodium/libsodium/src/libsodium/crypto_sign/ed25519/ref10/sign.o
CC build/libsodium/libsodium/src/libsodium/crypto_sign/ed25519/ref10/obsolete.o
CC build/libsodium/libsodium/src/libsodium/crypto_stream/chacha20/stream_chacha20.o
CC build/libsodium/libsodium/src/libsodium/crypto_stream/chacha20/ref/chacha20_ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_stream/crypto_stream.o
CC build/libsodium/libsodium/src/libsodium/crypto_stream/salsa20/stream_salsa20.o
CC build/libsodium/libsodium/src/libsodium/crypto_stream/salsa20/ref/salsa20_ref.o
CC build/libsodium/libsodium/src/libsodium/crypto_stream/xsalsa20/stream_xsalsa20.o
CC build/libsodium/libsodium/src/libsodium/crypto_verify/sodium/verify.o
CC build/libsodium/libsodium/src/libsodium/randombytes/randombytes.o
CC build/libsodium/libsodium/src/libsodium/sodium/utils.o
CC build/libsodium/libsodium/src/libsodium/sodium/runtime.o
CC build/libsodium/libsodium/src/libsodium/sodium/version.o
CC build/libsodium/libsodium/src/libsodium/sodium/core.o
CC build/libsodium/port/crypto_hash_mbedtls/crypto_hash_sha512_mbedtls.o
CC build/libsodium/port/crypto_hash_mbedtls/crypto_hash_sha256_mbedtls.o
AR build/libsodium/liblibsodium.a
CC build/log/log.o
AR build/log/liblog.a
CC build/lwip/apps/dhcpserver/dhcpserver.o
CC build/lwip/apps/ping/ping_sock.o
CC build/lwip/apps/ping/esp_ping.o
CC build/lwip/apps/ping/ping.o
CC build/lwip/apps/sntp/sntp.o
CC build/lwip/lwip/src/api/sockets.o
CC build/lwip/lwip/src/api/api_msg.o
CC build/lwip/lwip/src/api/err.o
CC build/lwip/lwip/src/api/if_api.o
CC build/lwip/lwip/src/api/netbuf.o
CC build/lwip/lwip/src/api/tcpip.o
CC build/lwip/lwip/src/api/netifapi.o
CC build/lwip/lwip/src/api/api_lib.o
CC build/lwip/lwip/src/api/netdb.o
CC build/lwip/lwip/src/apps/sntp/sntp.o
CC build/lwip/lwip/src/apps/netbiosns/netbiosns.o
CC build/lwip/lwip/src/core/tcp_out.o
CC build/lwip/lwip/src/core/udp.o
CC build/lwip/lwip/src/core/altcp_tcp.o
CC build/lwip/lwip/src/core/def.o
CC build/lwip/lwip/src/core/altcp.o
CC build/lwip/lwip/src/core/stats.o
CC build/lwip/lwip/src/core/netif.o
CC build/lwip/lwip/src/core/pbuf.o
CC build/lwip/lwip/src/core/tcp_in.o
CC build/lwip/lwip/src/core/raw.o
CC build/lwip/lwip/src/core/ip.o
CC build/lwip/lwip/src/core/dns.o
CC build/lwip/lwip/src/core/altcp_alloc.o
CC build/lwip/lwip/src/core/timeouts.o
CC build/lwip/lwip/src/core/tcp.o
CC build/lwip/lwip/src/core/sys.o
CC build/lwip/lwip/src/core/memp.o
CC build/lwip/lwip/src/core/init.o
CC build/lwip/lwip/src/core/inet_chksum.o
CC build/lwip/lwip/src/core/mem.o
CC build/lwip/lwip/src/core/ipv4/icmp.o
CC build/lwip/lwip/src/core/ipv4/autoip.o
CC build/lwip/lwip/src/core/ipv4/ip4.o
CC build/lwip/lwip/src/core/ipv4/igmp.o
CC build/lwip/lwip/src/core/ipv4/ip4_addr.o
CC build/lwip/lwip/src/core/ipv4/etharp.o
CC build/lwip/lwip/src/core/ipv4/dhcp.o
CC build/lwip/lwip/src/core/ipv4/ip4_frag.o
CC build/lwip/lwip/src/core/ipv4/ip4_napt.o
CC build/lwip/lwip/src/core/ipv6/icmp6.o
CC build/lwip/lwip/src/core/ipv6/ethip6.o
CC build/lwip/lwip/src/core/ipv6/mld6.o
CC build/lwip/lwip/src/core/ipv6/nd6.o
CC build/lwip/lwip/src/core/ipv6/ip6.o
CC build/lwip/lwip/src/core/ipv6/ip6_addr.o
CC build/lwip/lwip/src/core/ipv6/inet6.o
CC build/lwip/lwip/src/core/ipv6/dhcp6.o
CC build/lwip/lwip/src/core/ipv6/ip6_frag.o
CC build/lwip/lwip/src/netif/bridgeif.o
CC build/lwip/lwip/src/netif/lowpan6_common.o
CC build/lwip/lwip/src/netif/lowpan6_ble.o
CC build/lwip/lwip/src/netif/lowpan6.o
CC build/lwip/lwip/src/netif/zepif.o
CC build/lwip/lwip/src/netif/bridgeif_fdb.o
CC build/lwip/lwip/src/netif/ethernet.o
CC build/lwip/lwip/src/netif/slipif.o
CC build/lwip/port/esp8266/vfs_lwip.o
CC build/lwip/port/esp8266/freertos/sys_arch.o
CC build/lwip/port/esp8266/netif/dhcp_state.o
CC build/lwip/port/esp8266/netif/wlanif.o
CC build/lwip/port/esp8266/debug/lwip_debug.o
AR build/lwip/liblwip.a
CC build/main/hello_world_main.o
AR build/main/libmain.a
CC build/mbedtls/mbedtls/library/poly1305.o
CC build/mbedtls/mbedtls/library/platform_util.o
CC build/mbedtls/mbedtls/library/havege.o
CC build/mbedtls/mbedtls/library/ssl_cookie.o
CC build/mbedtls/mbedtls/library/md5.o
CC build/mbedtls/mbedtls/library/certs.o
CC build/mbedtls/mbedtls/library/ssl_ciphersuites.o
CC build/mbedtls/mbedtls/library/camellia.o
CC build/mbedtls/mbedtls/library/x509_crl.o
CC build/mbedtls/mbedtls/library/threading.o
CC build/mbedtls/mbedtls/library/aesni.o
CC build/mbedtls/mbedtls/library/bignum.o
CC build/mbedtls/mbedtls/library/arc4.o
CC build/mbedtls/mbedtls/library/cipher_wrap.o
CC build/mbedtls/mbedtls/library/rsa_internal.o
CC build/mbedtls/mbedtls/library/aes.o
CC build/mbedtls/mbedtls/library/xtea.o
CC build/mbedtls/mbedtls/library/base64.o
CC build/mbedtls/mbedtls/library/sha512.o
CC build/mbedtls/mbedtls/library/pkcs11.o
CC build/mbedtls/mbedtls/library/ecdsa.o
CC build/mbedtls/mbedtls/library/asn1write.o
CC build/mbedtls/mbedtls/library/oid.o
CC build/mbedtls/mbedtls/library/ecjpake.o
CC build/mbedtls/mbedtls/library/ssl_tls.o
CC build/mbedtls/mbedtls/library/debug.o
CC build/mbedtls/mbedtls/library/aria.o
CC build/mbedtls/mbedtls/library/ecdh.o
CC build/mbedtls/mbedtls/library/x509_crt.o
CC build/mbedtls/mbedtls/library/ssl_srv.o
CC build/mbedtls/mbedtls/library/sha1.o
CC build/mbedtls/mbedtls/library/chacha20.o
CC build/mbedtls/mbedtls/library/md2.o
CC build/mbedtls/mbedtls/library/x509_create.o
CC build/mbedtls/mbedtls/library/cmac.o
CC build/mbedtls/mbedtls/library/gcm.o
CC build/mbedtls/mbedtls/library/version.o
CC build/mbedtls/mbedtls/library/pem.o
CC build/mbedtls/mbedtls/library/padlock.o
CC build/mbedtls/mbedtls/library/asn1parse.o
CC build/mbedtls/mbedtls/library/timing.o
CC build/mbedtls/mbedtls/library/ssl_cli.o
CC build/mbedtls/mbedtls/library/pkwrite.o
CC build/mbedtls/mbedtls/library/ssl_cache.o
CC build/mbedtls/mbedtls/library/sha256.o
CC build/mbedtls/mbedtls/library/md_wrap.o
CC build/mbedtls/mbedtls/library/entropy.o
CC build/mbedtls/mbedtls/library/hkdf.o
CC build/mbedtls/mbedtls/library/rsa.o
CC build/mbedtls/mbedtls/library/ripemd160.o
CC build/mbedtls/mbedtls/library/nist_kw.o
CC build/mbedtls/mbedtls/library/pkcs5.o
CC build/mbedtls/mbedtls/library/version_features.o
CC build/mbedtls/mbedtls/library/cipher.o
CC build/mbedtls/mbedtls/library/entropy_poll.o
CC build/mbedtls/mbedtls/library/dhm.o
CC build/mbedtls/mbedtls/library/error.o
CC build/mbedtls/mbedtls/library/ssl_ticket.o
CC build/mbedtls/mbedtls/library/x509.o
CC build/mbedtls/mbedtls/library/blowfish.o
CC build/mbedtls/mbedtls/library/chachapoly.o
CC build/mbedtls/mbedtls/library/ecp.o
CC build/mbedtls/mbedtls/library/md4.o
CC build/mbedtls/mbedtls/library/x509_csr.o
CC build/mbedtls/mbedtls/library/pkparse.o
CC build/mbedtls/mbedtls/library/md.o
CC build/mbedtls/mbedtls/library/ccm.o
CC build/mbedtls/mbedtls/library/pkcs12.o
CC build/mbedtls/mbedtls/library/ecp_curves.o
CC build/mbedtls/mbedtls/library/pk_wrap.o
CC build/mbedtls/mbedtls/library/x509write_crt.o
CC build/mbedtls/mbedtls/library/ctr_drbg.o
CC build/mbedtls/mbedtls/library/platform.o
CC build/mbedtls/mbedtls/library/pk.o
CC build/mbedtls/mbedtls/library/x509write_csr.o
CC build/mbedtls/mbedtls/library/des.o
CC build/mbedtls/mbedtls/library/hmac_drbg.o
CC build/mbedtls/mbedtls/library/memory_buffer_alloc.o
CC build/mbedtls/port/esp_sha512.o
CC build/mbedtls/port/esp_mem.o
CC build/mbedtls/port/esp_hardware.o
CC build/mbedtls/port/net_sockets.o
CC build/mbedtls/port/esp_sha256.o
CC build/mbedtls/port/esp_timing.o
CC build/mbedtls/port/esp_aes.o
CC build/mbedtls/port/esp_sha1.o
CC build/mbedtls/port/mbedtls_debug.o
CC build/mbedtls/port/esp8266/arc4.o
CC build/mbedtls/port/esp8266/aes.o
CC build/mbedtls/port/esp8266/base64.o
CC build/mbedtls/port/esp8266/md5.o
CC build/mbedtls/port/esp8266/sha256.o
CC build/mbedtls/port/esp8266/sha1.o
CC build/mbedtls/port/esp8266/sha512.o
AR build/mbedtls/libmbedtls.a
AR build/mdns/libmdns.a
CC build/mqtt/esp-mqtt/mqtt_client.o
CC build/mqtt/esp-mqtt/lib/platform_esp32_idf.o
CC build/mqtt/esp-mqtt/lib/mqtt_msg.o
CC build/mqtt/esp-mqtt/lib/mqtt_outbox.o
AR build/mqtt/libmqtt.a
CC build/newlib/src/select.o
CC build/newlib/src/random.o
CC build/newlib/src/locks.o
CC build/newlib/src/esp_malloc.o
CC build/newlib/src/termios.o
CC build/newlib/src/reent_init.o
CC build/newlib/src/time.o
CC build/newlib/src/syscall.o
AR build/newlib/libnewlib.a
CXX build/nvs_flash/src/nvs_partition_manager.o
CXX build/nvs_flash/src/nvs_api.o
CXX build/nvs_flash/src/nvs_storage.o
CXX build/nvs_flash/src/nvs_handle_simple.o
CXX build/nvs_flash/src/nvs_partition_lookup.o
CXX build/nvs_flash/src/nvs_pagemanager.o
CXX build/nvs_flash/src/nvs_handle_locked.o
CXX build/nvs_flash/src/nvs_item_hash_list.o
CXX build/nvs_flash/src/nvs_page.o
CXX build/nvs_flash/src/nvs_partition.o
CXX build/nvs_flash/src/nvs_types.o
CXX build/nvs_flash/src/nvs_cxx_api.o
CXX build/nvs_flash/src/nvs_encrypted_partition.o
AR build/nvs_flash/libnvs_flash.a
CC build/openssl/library/ssl_stack.o
CC build/openssl/library/ssl_lib.o
CC build/openssl/library/ssl_x509.o
CC build/openssl/library/ssl_pkey.o
CC build/openssl/library/ssl_methods.o
CC build/openssl/library/ssl_cert.o
CC build/openssl/platform/ssl_port.o
CC build/openssl/platform/ssl_pm.o
AR build/openssl/libopenssl.a
CC build/protobuf-c/protobuf-c/protobuf-c/protobuf-c.o
AR build/protobuf-c/libprotobuf-c.a
AR build/protocomm/libprotocomm.a
CC build/pthread/pthread.o
CC build/pthread/pthread_cond_var.o
CC build/pthread/pthread_local_storage.o
AR build/pthread/libpthread.a
CC build/spi_flash/src/spi_flash_raw.o
CC build/spi_flash/src/spi_flash.o
CC build/spi_flash/src/partition.o
AR build/spi_flash/libspi_flash.a
CC build/spi_ram/spi_ram.o
CC build/spi_ram/spi_ram_fifo.o
AR build/spi_ram/libspi_ram.a
CC build/spiffs/esp_spiffs.o
CC build/spiffs/spiffs_api.o
CC build/spiffs/spiffs/src/spiffs_hydrogen.o
CC build/spiffs/spiffs/src/spiffs_check.o
CC build/spiffs/spiffs/src/spiffs_nucleus.o
CC build/spiffs/spiffs/src/spiffs_gc.o
CC build/spiffs/spiffs/src/spiffs_cache.o
AR build/spiffs/libspiffs.a
CC build/tcp_transport/transport_tcp.o
CC build/tcp_transport/transport.o
CC build/tcp_transport/transport_ssl.o
CC build/tcp_transport/transport_utils.o
CC build/tcp_transport/transport_ws.o
AR build/tcp_transport/libtcp_transport.a
CC build/tcpip_adapter/event_handlers.o
CC build/tcpip_adapter/tcpip_adapter_lwip.o
CC build/tcpip_adapter/esp_netif.o
AR build/tcpip_adapter/libtcpip_adapter.a
CC build/vfs/vfs.o
CC build/vfs/vfs_semihost.o
CC build/vfs/vfs_uart.o
AR build/vfs/libvfs.a
CXX build/wear_levelling/WL_Ext_Perf.o
CXX build/wear_levelling/Partition.o
CXX build/wear_levelling/SPI_Flash.o
CXX build/wear_levelling/WL_Ext_Safe.o
CXX build/wear_levelling/crc32.o
CXX build/wear_levelling/WL_Flash.o
CXX build/wear_levelling/wear_levelling.o
AR build/wear_levelling/libwear_levelling.a
AR build/wifi_provisioning/libwifi_provisioning.a
CC build/wpa_supplicant/port/os_xtensa.o
CC build/wpa_supplicant/src/ap/ap_config.o
CC build/wpa_supplicant/src/ap/wpa_auth.o
CC build/wpa_supplicant/src/ap/ieee802_1x.o
CC build/wpa_supplicant/src/ap/wpa_auth_ie.o
CC build/wpa_supplicant/src/common/wpa_common.o
CC build/wpa_supplicant/src/common/dpp.o
CC build/wpa_supplicant/src/common/sae.o
CC build/wpa_supplicant/src/crypto/aes-ctr.o
CC build/wpa_supplicant/src/crypto/crypto_mbedtls-ec.o
CC build/wpa_supplicant/src/crypto/ms_funcs.o
CC build/wpa_supplicant/src/crypto/sha256-tlsprf.o
CC build/wpa_supplicant/src/crypto/sha384-tlsprf.o
CC build/wpa_supplicant/src/crypto/crypto_internal-modexp.o
CC build/wpa_supplicant/src/crypto/bignum.o
CC build/wpa_supplicant/src/crypto/sha256-prf.o
CC build/wpa_supplicant/src/crypto/sha1-pbkdf2.o
CC build/wpa_supplicant/src/crypto/aes-ccm.o
CC build/wpa_supplicant/src/crypto/aes-cbc.o
CC build/wpa_supplicant/src/crypto/md5.o
CC build/wpa_supplicant/src/crypto/rc4.o
CC build/wpa_supplicant/src/crypto/sha256.o
CC build/wpa_supplicant/src/crypto/crypto_mbedtls-bignum.o
CC build/wpa_supplicant/src/crypto/dh_groups.o
CC build/wpa_supplicant/src/crypto/md4-internal.o
CC build/wpa_supplicant/src/crypto/sha1-internal.o
CC build/wpa_supplicant/src/crypto/aes-wrap.o
CC build/wpa_supplicant/src/crypto/crypto_mbedtls.o
CC build/wpa_supplicant/src/crypto/crypto_internal-cipher.o
CC build/wpa_supplicant/src/crypto/aes-omac1.o
CC build/wpa_supplicant/src/crypto/dh_group5.o
CC build/wpa_supplicant/src/crypto/crypto_ops.o
CC build/wpa_supplicant/src/crypto/sha1-tlsprf.o
CC build/wpa_supplicant/src/crypto/des-internal.o
CC build/wpa_supplicant/src/crypto/aes-siv.o
CC build/wpa_supplicant/src/crypto/tls_mbedtls.o
CC build/wpa_supplicant/src/crypto/crypto_internal-rsa.o
CC build/wpa_supplicant/src/crypto/sha256-kdf.o
CC build/wpa_supplicant/src/crypto/ccmp.o
CC build/wpa_supplicant/src/crypto/aes-unwrap.o
CC build/wpa_supplicant/src/crypto/crypto_internal.o
CC build/wpa_supplicant/src/crypto/aes-internal-dec.o
CC build/wpa_supplicant/src/crypto/sha1.o
CC build/wpa_supplicant/src/crypto/crypto_mbedtls-rsa.o
CC build/wpa_supplicant/src/crypto/aes-internal.o
CC build/wpa_supplicant/src/crypto/md5-internal.o
CC build/wpa_supplicant/src/crypto/sha256-internal.o
CC build/wpa_supplicant/src/crypto/aes-internal-enc.o
CC build/wpa_supplicant/src/eap_peer/eap_peap_common.o
CC build/wpa_supplicant/src/eap_peer/chap.o
CC build/wpa_supplicant/src/eap_peer/eap_mschapv2.o
CC build/wpa_supplicant/src/eap_peer/eap_peap.o
CC build/wpa_supplicant/src/eap_peer/eap_ttls.o
CC build/wpa_supplicant/src/eap_peer/eap_tls_common.o
CC build/wpa_supplicant/src/eap_peer/eap_tls.o
CC build/wpa_supplicant/src/eap_peer/mschapv2.o
CC build/wpa_supplicant/src/eap_peer/eap_common.o
CC build/wpa_supplicant/src/eap_peer/eap.o
CC build/wpa_supplicant/src/rsn_supp/wpa.o
CC build/wpa_supplicant/src/rsn_supp/wpa_ie.o
CC build/wpa_supplicant/src/rsn_supp/pmksa_cache.o
CC build/wpa_supplicant/src/utils/uuid.o
CC build/wpa_supplicant/src/utils/json.o
CC build/wpa_supplicant/src/utils/wpabuf.o
CC build/wpa_supplicant/src/utils/ext_password.o
CC build/wpa_supplicant/src/utils/base64.o
CC build/wpa_supplicant/src/utils/bitfield.o
CC build/wpa_supplicant/src/utils/common.o
CC build/wpa_supplicant/src/utils/wpa_debug.o
CC build/wpa_supplicant/src/esp_supplicant/esp_wpa_main.o
CC build/wpa_supplicant/src/esp_supplicant/esp_wpa2.o
CC build/wpa_supplicant/src/esp_supplicant/esp_wpa3.o
CC build/wpa_supplicant/src/esp_supplicant/esp_hostap.o
CC build/wpa_supplicant/src/esp_supplicant/esp_wps.o
CC build/wpa_supplicant/src/esp_supplicant/esp_wpas_glue.o
CC build/wpa_supplicant/src/wps/wps_enrollee.o
CC build/wpa_supplicant/src/wps/wps_attr_build.o
CC build/wpa_supplicant/src/wps/wps_registrar.o
CC build/wpa_supplicant/src/wps/wps_common.o
CC build/wpa_supplicant/src/wps/wps.o
CC build/wpa_supplicant/src/wps/wps_dev_attr.o
CC build/wpa_supplicant/src/wps/wps_attr_parse.o
CC build/wpa_supplicant/src/wps/wps_validate.o
CC build/wpa_supplicant/src/wps/wps_attr_process.o
AR build/wpa_supplicant/libwpa_supplicant.a
Generating esp8266.project.ld
LD build/hello-world.elf
esptool.py v2.4.0
Flashing binaries to serial port com3 (app at offset 0x10000)...
esptool.py v2.4.0
Connecting....
Chip is ESP8266EX
Features: WiFi
MAC: 68:c6:3a:cb:0a:7b
Uploading stub...
Running stub...
Stub running...
Configuring flash size...
Compressed 11072 bytes to 7432...
Wrote 11072 bytes (7432 compressed) at 0x00000000 in 0.7 seconds (effective 132.0 kbit/s)...
Hash of data verified.
Compressed 169376 bytes to 108624...
Wrote 169376 bytes (108624 compressed) at 0x00010000 in 9.7 seconds (effective 139.9 kbit/s)...
Hash of data verified.
Compressed 3072 bytes to 83...
Wrote 3072 bytes (83 compressed) at 0x00008000 in 0.0 seconds (effective 1575.4 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...

