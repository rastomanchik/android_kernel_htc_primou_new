DHDCFLAGS = -DLINUX -DBCMDRIVER -DBCMDONGLEHOST -DUNRELEASEDCHIP -DBCMDMA32  \
	-DBCMFILEIMAGE -Dlinux -DDHD_SDALIGN=64 -DMAX_HDR_READ=64            \
	-DDHD_FIRSTREAD=64 -DDHDTHREAD -DDHD_GPL -DDHD_SCHED -DBDC           \
	-DTOE -DDHD_BCMEVENTS -DSHOW_EVENTS -DDONGLEOVERLAYS -DOEM_ANDROID   \
	-DBCMDBG -DDHD_USE_STATIC_BUF -DCONFIG_FIRST_SCAN -DAPSTA_CONCURRENT -DBRCM_WPSAP\
	-DCUSTOM_OOB_GPIO_NUM=46 -DOOB_INTR_ONLY -DMMC_SDIO_ABORT -DEMBEDDED_PLATFORM -DCUSTOMER_HW2 \
	-DPNO_SUPPORT -DBCMSDIO -DDHD_GPL -DBCMLXSDMMC -DBCMPLATFORM_BUS -DWIFI_ACT_FRAME -DKEEP_ALIVE \
	-DCSCAN -DBCM4329_LOW_POWER  -DBCMWAPI_WAI -DBCMWAPI_WPI -DHTC_KlocWork -DWL_CFG80211 -DWLP2P -DWL_COMPAT_WIRELESS \
    -DWL_CFG80211 -DWLP2P -DWL_COMPAT_WIRELESS -Wall -Wstrict-prototypes -Werror                                    \
	-Idrivers/net/wireless/bcmdhd_htc -Idrivers/net/wireless/bcmdhd_htc/include

ifdef COMPAT_WIRELESS
NOSTDINC_FLAGS := -I$(COMPAT_WIRELESS)/include/ \
        -include $(COMPAT_WIRELESS)/include/linux/compat-2.6.h
endif

DHDOFILES = dhd_linux.o linux_osl.o bcmutils.o dhd_common.o dhd_custom_gpio.o \
        siutils.o sbutils.o aiutils.o hndpmu.o bcmwifi.o dhd_sdio.o   \
        dhd_linux_sched.o dhd_cdc.o bcmsdh_sdmmc.o bcmsdh.o bcmsdh_linux.o    \
        bcmsdh_sdmmc_linux.o bcmevent.o dhd_bta.o wl_android.o wldev_common.o wl_linux_mon.o wl_cfg80211.o wl_cfgp2p.o dhd_cfg80211.o

DHDOFILES += wl_linux_mon.o wl_cfg80211.o wl_cfgp2p.o

obj-$(CONFIG_BCMDHD) += bcmdhd.o
bcmdhd-objs += $(DHDOFILES)
ifneq ($(CONFIG_WIRELESS_EXT),)
bcmdhd-objs += wl_iw.o
DHDCFLAGS += -DSOFTAP
endif
EXTRA_CFLAGS = $(DHDCFLAGS)
EXTRA_LDFLAGS += --strip-debug
