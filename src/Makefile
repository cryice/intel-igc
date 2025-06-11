# 模块名称（最终生成 igc.ko）
MODNAME := igc
# 获取当前目录路径
PWD := $(shell pwd)
# 内核源码/构建路径，默认找当前系统内核对应目录，也可手动指定，如 KDIR := /lib/modules/$(shell uname -r)/build
KDIR ?= /lib/modules/$(shell uname -r)/build

# 声明要构建的内核模块，igc-objs 定义模块依赖的目标文件
obj-m += $(MODNAME).o
# 列出目录下需要编译的 .c 文件对应的 .o 文件，根据实际源码调整
$(MODNAME)-objs := igc_main.o igc_mac.o igc_i225.o igc_base.o igc_nvm.o igc_phy.o \
igc_diag.o igc_ethtool.o igc_ptp.o igc_dump.o igc_tsn.o igc_xdp.o

# 编译模块的指令，-C 进入内核构建目录，M= 指定驱动源码路径
all:
	make -C $(KDIR) M=$(PWD) modules
# 清理编译生成的文件
clean:
	make -C $(KDIR) M=$(PWD) clean