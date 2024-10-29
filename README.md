# physical_computing
how to do c programming on arduino
install on windows
1. download c compiler on windows using (https://www.freecodecamp.org/news/how-to-install-c-and-cpp-compiler-on-windows/)
2. download arduino uno 1.8.19
3. go inside the arduino files into the bin file and copy the link(C:\Users\mtbai\Downloads\arduino-1.8.19-windows\arduino-1.8.19\hardware\tools\avr\bin)
4. Make soft links.
5. first open command prompt using administer and put these three commands
mklink avr-gcc.exe "C:\Users\mtbai\Downloads\arduino-1.8.19-windows\arduino-1.8.19\hardware\tools\avr\bin\avr-gcc.exe"
mklink avr-objcopy.exe "C:\Users\mtbai\Downloads\arduino-1.8.19-windows\arduino-1.8.19\hardware\tools\avr\bin\avr-objcopy.exe"
mklink avrdude "C:\Users\mtbai\Downloads\arduino-1.8.19-windows\arduino-1.8.19\hardware\tools\avr\bin\avrdude"

6. Check that they are there by writing (dir C:\Windows\System32\avr*)
7. Now open command prompt and cd to where you c code is and run your c code using these three commands
1.
avr-gcc -Wall -g -Os -mmcu=atmega328p code.c -o code.elf
2.
avr-objcopy -O ihex code.elf code.hex

3.
avrdude -p atmega328p -c arduino -P /dev/tty.COM3 -b 115200 -D -U flash:w:code.hex:i
Or try
avrdude -C "C:\Users\mtbai\Downloads\arduino-1.8.19-windows\arduino-1.8.19\hardware\tools\avr\etc\avrdude.conf" -p atmega328p -c arduino -P COM3 -b 115200 -D -U flash:w:"C:\Users\mtbai\Desktop\code.hex":i


install on mac
