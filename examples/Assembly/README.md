Prerequisites:
* Ubuntu 14.04 LTS
* STM32F4 Discovery Board

Install software dependencies:
* `cd ~`
* `sudo add-apt-repository ppa:terry.guo/gcc-arm-embedded`
* `sudo apt-get update`
* `sudo apt-cache policy gcc-arm-none-eabi`
* `sudo apt-get install gcc-arm-none-eabi=4-8-2014q2-0trusty10` The latter packages contains GCC, GDB, binutils, newlib and newlib-nano libraries.
* `sudo apt-get install build-essential git openocd symlinks` 
* `git clone https://github.com/istarc/stm32.git`
* `cd ~/stm32`
* `git submodule update --init` This command is required to initialize submodules.

Build:
* `make clean`
* `make -j4 # Size-optimized build`
* Other build options:
	* `make -j4 all # Size-optimized build`
	* `make -j4 release-memopt # Size-optimized build`
	* `make -j4 release # Non-optimized build`
	* `make -j4 debug # Debug build` 

Deploy to target via OpenOCD:
* `make deploy`

More info:
* Assembly: [Mixing C & Assembly for Fun and Profit]()
