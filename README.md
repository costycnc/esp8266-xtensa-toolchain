# esp8266-xtensa-toolchain
install esp8266 xtensa toolchain

\msys32\mingw32


mkdir -p ~/esp


cd ~/esp

export PATH="$PATH:$HOME/esp/xtensa-lx106-elf/bin"


printenv PATH



git clone --recursive https://github.com/espressif/ESP8266_RTOS_SDK.git


export IDF_PATH="$HOME/esp/ESP8266_RTOS_SDK"


printenv IDF_PATH


python --version

python2.7 -m pip install --user -r $IDF_PATH/requirements.txt


dir


cd ESP8266_RTOS_SDK/

cd examples

dir


cd get-started


dir


cd ~/esp


cp -r $IDF_PATH/examples/get-started/hello_world .


cd hello_world


make menuconfig

make flash
