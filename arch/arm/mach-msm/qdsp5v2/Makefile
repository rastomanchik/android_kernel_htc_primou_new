obj-y += afe.o audio_interct.o mi2s.o audio_dev_ctl.o voice.o snddev_data.o

obj-$(CONFIG_MARIMBA_CODEC) += snddev_icodec.o lpa.o
obj-$(CONFIG_TIMPANI_CODEC) += snddev_icodec.o lpa.o

obj-y += aux_pcm.o snddev_ecodec.o audio_out.o audpp.o snddev_mi2s.o
obj-y += audio_mp3.o audio_lpa.o mp3_funcs.o pcm_funcs.o audpreproc.o
obj-y += adsp.o adsp_driver.o adsp_info.o
obj-y += audio_acdb.o audio_aac.o audio_amrnb_in.o audio_evrc_in.o audio_qcelp_in.o audio_pcm_in.o
obj-y += audio_mvs.o

CFLAGS_audio_lpa.o := -DDEBUG
