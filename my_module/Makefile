# 内核构建目录，一般由外部传进来（GitHub Actions 会传 KERNEL_DIR）
# 如果没传，给一个默认值（方便你将来本地编译）
KERNEL_DIR ?= /lib/modules/$(shell uname -r)/build

# 你的模块目标文件（把 .c 换成 .o）
obj-m := hello.o

all:
	$(MAKE) -C $(KERNEL_DIR) M=$(PWD) \
		ARCH=arm64 \
		CC=$(CC) \
		CLANG_TRIPLE=$(CLANG_TRIPLE) \
		CROSS_COMPILE=$(CROSS_COMPILE) \
		LD=$(LD) \
		AR=$(AR) \
		NM=$(NM) \
		STRIP=$(STRIP) \
		OBJCOPY=$(OBJCOPY) \
		modules

clean:
	$(MAKE) -C $(KERNEL_DIR) M=$(PWD) clean
