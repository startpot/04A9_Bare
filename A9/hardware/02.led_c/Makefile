objs := start.o led.o

led.bin : $(objs)
	arm-linux-gnueabihf-ld -Tled.lds -N -o led.elf $^
	arm-linux-gnueabihf-objcopy -O binary -S led.elf $@
	arm-linux-gnueabihf-objdump -D -m arm  led.elf > led.dis

%.o:%.c
	arm-linux-gnueabihf-gcc -Wall -marm -c -O2 -o $@ $<

%.o:%.S
	arm-linux-gnueabihf-gcc -Wall -marm -c -O2 -o $@ $<

clean:
	rm -f  *.dis *.bin *.elf *.o
	
