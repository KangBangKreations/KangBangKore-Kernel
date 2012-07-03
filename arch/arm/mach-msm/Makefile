obj-y += io.o idle.o timer.o
obj-y += clock.o
obj-$(CONFIG_DEBUG_FS) += clock-debug.o

obj-$(CONFIG_MSM_VIC) += irq-vic.o
obj-$(CONFIG_MSM_IOMMU) += devices-iommu.o

obj-$(CONFIG_ARCH_MSM7X00A) += dma.o irq.o acpuclock-arm11.o
obj-$(CONFIG_ARCH_MSM7X30) += dma.o
obj-$(CONFIG_ARCH_QSD8X50) += dma.o sirc.o

obj-$(CONFIG_MSM_PROC_COMM) += proc_comm.o clock-pcom.o vreg.o

obj-$(CONFIG_MSM_SMD) += smd.o smd_debug.o
obj-$(CONFIG_MSM_SMD) += last_radio_log.o
obj-$(CONFIG_MSM_SCM) += scm.o scm-boot.o

CFLAGS_scm.o :=$(call as-instr,.arch_extension sec,-DREQUIRES_SEC=1)

obj-$(CONFIG_HOTPLUG_CPU) += hotplug.o
obj-$(CONFIG_SMP) += headsmp.o platsmp.o

obj-$(CONFIG_MACH_TROUT) += board-trout.o board-trout-gpio.o board-trout-mmc.o devices-msm7x00.o
obj-$(CONFIG_MACH_TROUT) += board-trout.o board-trout-gpio.o board-trout-mmc.o board-trout-panel.o devices-msm7x00.o
obj-$(CONFIG_MACH_HALIBUT) += board-halibut.o devices-msm7x00.o
obj-$(CONFIG_ARCH_MSM7X30) += board-msm7x30.o devices-msm7x30.o
obj-$(CONFIG_ARCH_QSD8X50) += board-qsd8x50.o devices-qsd8x50.o
obj-$(CONFIG_ARCH_MSM8X60) += devices-msm8x60.o clock-local.o clock-8x60.o acpuclock-8x60.o
obj-$(CONFIG_ARCH_MSM8X60) += devices_htc.o htc_wifi_nvs.o sysinfo-8x60.o emmc_partitions.o
obj-$(CONFIG_ARCH_MSM8X60) += clock-rpm.o
obj-$(CONFIG_ARCH_MSM8X60) += saw-regulator.o
obj-$(CONFIG_ARCH_MSM8X60) += rpm-regulator.o rpm-regulator-8660.o
obj-$(CONFIG_ARCH_MSM8X60) += footswitch-8x60.o
obj-$(CONFIG_MSM8X60_AUDIO) += htc_acoustic_8x60.o htc_awb_cal.o
obj-$(CONFIG_MSM_SYSMON_COMM) += sysmon.o

obj-$(CONFIG_HTC_BATT_CORE) += htc_battery_core.o
obj-$(CONFIG_HTC_BATT8x60) += htc_battery_8x60.o

ifdef CONFIG_MSM_SUBSYSTEM_RESTART
	obj-y += subsystem_notif.o
	obj-y += subsystem_restart.o
	obj-y += ramdump.o
	obj-$(CONFIG_ARCH_MSM8X60) += subsystem-fatal-8x60.o
endif

obj-$(CONFIG_ARCH_MSM8960) += board-msm8960.o devices-msm8960.o

obj-$(CONFIG_ARCH_MSM7X30) += gpiomux-v1.o gpiomux.o
obj-$(CONFIG_ARCH_QSD8X50) += gpiomux-8x50.o gpiomux-v1.o gpiomux.o
obj-$(CONFIG_ARCH_MSM8X60) += gpiomux-8x60.o gpiomux-v2.o gpiomux.o

ifdef CONFIG_ARCH_MSM8X60
	obj-y += scm-log.o
endif

ifdef CONFIG_PM
	obj-$(CONFIG_ARCH_MSM8960) += pm-8x60.o
	obj-$(CONFIG_ARCH_MSM8X60) += pm-8x60.o
	obj-y += pm-boot.o
else
	obj-y += no-pm.o
endif
obj-$(CONFIG_MSM_SECURE_IO) += scm-io.o
ifdef CONFIG_MSM_NONSMD_PACKET_FILTER
obj-$(CONFIG_MSM_SMD) += htc_port_list_lte.o
else
obj-$(CONFIG_MSM_SMD) += htc_port_list.o
endif

ifeq ($(CONFIG_ARCH_MSM8X60_LTE),y)
obj-$(CONFIG_ARCH_MSM8X60_LTE) += 8x60-lte/
endif
