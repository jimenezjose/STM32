# STM32
STM32F4 Nucleo 

### Download the [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html) code generation GUI:

![alt text]( https://github.com/jimenezjose/STM32/blob/master/Images/STM32CubeMX%20Download.png "STM32MX")
![alt text]( https://github.com/jimenezjose/STM32/blob/master/Images/STM32CubeMX.png "STM32MX")

### Download the [gcc ARM compiler](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads):

![alt text]( https://github.com/jimenezjose/STM32/blob/master/Images/gcc-arm%20compiler%20download.png "gcc arm")

### Mac OSX: [Brew will be needed](https://brew.sh/).

Install [st-flash](http://macappstore.org/stlink/) to uplaod data to the text section of the stm32: 

### Other OS: STLink GitHub Repo

[st-flash Repo](https://github.com/texane/stlink):
Not too sure on this part but just try to download STLink. 
I also found this [link on the arm website](https://www.st.com/en/development-tools/stsw-link004.html).
If you manage to figure it out, document what you did, so I can post it here.

## Disclaimer: You do not have to use a Makefile. I only did it because I am fairly familiar using it. Many used IDEs to upload code to the STM32. But this is the way I did it. Again you do not have to do it this way. If you figure out another way to upload code to the stm32 that is totally fine and encouraged.

### Make an LED_Blink program. Follow this [video](https://youtu.be/BJdXR0Al6os):

    The only difference that we will have is in section, if you are using a Makefile, is in minute 5:08 of the video.
    In the Toolchain/IDE section in the settings for the STM32MX it should be Makefile instead of MDK-ARM V5.
    
![alt text]( https://github.com/jimenezjose/STM32/blob/master/Images/gcc-arm%20compiler%20download.png "gcc arm")

### The folowing directions will be Mac specific only because I configured the software on my MacOS machine.

If you are getting "command \*\*\* not found". I had the same issues. So luckily, I figured out what the problem was.
Every time you attempt to execute a command a binary file is executed. For example if I enter "echo hi" the echo command
only executes because there is a binary file in the "\bin" directory named "echo". So find your binary files. It should be in the folders you downloaded. For a more concrete example follow this quick tutorial.

### Say "arm-none-eabi-gcc" command is not found.

### Before anything find the arm-none-eabi-gcc binary file. How? I'll show a [video](https://youtu.be/NxK8P0QOFqw).

## How to flash code on to the STM32
```
st-flash write [binary file] 0x08000000
```
[NUCLEO-F4 Data Sheet - Pinout](https://www.st.com/content/ccc/resource/technical/document/user_manual/98/2e/fa/4b/e0/82/43/b7/DM00105823.pdf/files/DM00105823.pdf/jcr:content/translations/en.DM00105823.pdf)

[NUCLEO-F4 Data Sheet - Memory Mapping](https://www.st.com/resource/en/datasheet/cd00237391.pdf)

[Pin Functions](https://simonmartin.ch/resources/stm32/dl/STM32%20Tutorial%2001%20-%20GPIO%20Operations%20using%20HAL%20(and%20FreeRTOS).pdf)
