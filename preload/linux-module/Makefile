obj-m += vprobe-offsets.o

headers="/lib/modules/$(shell uname -r)/build"

all:
	make -C $(headers) M=$(PWD) modules
	insmod ./vprobe-offsets.ko
	cat /proc/vprobe-offsets > linux-offsets.emt
	rmmod vprobe-offsets.ko
	make -C $(headers) M=$(PWD) clean
	rm -f Module.markers Module.symvers

mod:
	make -C $(headers) M=$(PWD) modules

clean:
	make -C $(headers) M=$(PWD) clean

