#
# Copyright (C) 2017-2019 Ian Leonard <antonlacon@gmail.com>
# Copyright (C) 2018 Ted Hess <thess@kitschensync.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ffmpeg-old
PKG_VERSION:=3.4.9
PKG_RELEASE:=1

PKG_SOURCE:=ffmpeg-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://ffmpeg.org/releases/
PKG_HASH:=496fb4a9c396406e24841f3f3f108a7ae6397d6d1106ac1f953317c4529b1635
PKG_MAINTAINER:=Ted Hess <thess@kitschensync.net>, \
		Ian Leonard <antonlacon@gmail.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/ffmpeg-$(PKG_VERSION)

PKG_LICENSE:=LGPL-2.1-or-later GPL-2.0-or-later LGPL-3.0-or-later
PKG_LICENSE_FILES:=COPYING.GPLv2 COPYING.GPLv3 COPYING.LGPLv2.1 COPYING.LGPLv3
PKG_CPE_ID:=cpe:/a:ffmpeg:ffmpeg

FFMPEG_CUSTOM_ENCODERS:= \
	ac3 \
	jpegls \
	mpeg1video \
	mpeg2video \
	mpeg4 \
	pcm_s16be \
	pcm_s16le \
	png \
	vorbis \
	zlib \

FFMPEG_CUSTOM_DECODERS:= \
	aac \
	ac3 \
	alac \
	amrnb \
	amrwb \
	ape \
	atrac3 \
	flac \
	gif \
	h264 \
	hevc \
	jpegls \
	mp2 \
	mp3 \
	mpeg1video \
	mpeg2video \
	mpeg4 \
	mpegvideo \
	mpc7 \
	mpc8 \
	pcm_s16be \
	pcm_s16le \
	png \
	vc1 \
	vorbis \
	wavpack \
	wmav1 \
	wmav2 \
	zlib \

FFMPEG_CUSTOM_MUXERS:= \
	ac3 \
	ffm \
	h264 \
	hevc \
	mp3 \
	mp4 \
	mpeg1video \
	mpeg2video \
	mpegts \
	ogg \
	rtp \

FFMPEG_CUSTOM_DEMUXERS:= \
	aac \
	ac3 \
	amr \
	ape \
	avi \
	flac \
	ffm \
	h264 \
	hevc \
	matroska \
	mov \
	mp3 \
	mpegps \
	mpegts \
	mpegvideo \
	mpc \
	mpc8 \
	ogg \
	rm \
	rtsp \
	rtp \
	sdp \
	v4l2 \
	vc1 \
	wav \
	wv \

FFMPEG_CUSTOM_PARSERS:= \
	aac \
	flac \
	ac3 \
	h264 \
	hevc \
	mpegaudio \
	mpeg4video \
	mpegvideo \
	vc1 \

FFMPEG_CUSTOM_PROTOCOLS:= \
	file http icecast pipe rtp tcp udp

FFMPEG_MINI_DECODERS:= \
	ac3 \
	flac \
	jpegls \
	mp2 \
	mp3 \
	mpeg1video \
	mpeg2video \
	mpeg4 \
	mpegvideo \
	opus \
	png \
	vorbis \

FFMPEG_PATENTED_MINI_DECODERS:= \
	h264 \
	hevc \
	vc1 \

FFMPEG_MINI_DEMUXERS:= \
	avi \
	flac \
	matroska \
	mov \
	mp3 \
	mpegps \
	mpegts \
	mpegvideo \
	ogg \

FFMPEG_MINI_PROTOCOLS:= \
	file

FFMPEG_AUDIO_DECODERS:= \
	ac3 \
	adpcm_* \
	alac \
	amrnb \
	amrwb \
	ape \
	atrac3 \
	flac \
	mp2 \
	mp3* \
	mpc7 \
	mpc8 \
	opus \
	pcm_* \
	vorbis \
	wavpack \
	zlib \

FFMPEG_AUDIO_DEMUXERS:= \
	ac3 \
	aiff \
	amr \
	ape \
	avi \
	flac \
	ffm \
	matroska \
	mp3 \
	mov \
	mpc \
	mpc8 \
	mpegts \
	ogg \
	rm \
	rtsp \
	rtp \
	sdp \
	wav \
	wv \

FFMPEG_AUDIO_PROTOCOLS:= \
	file http icecast rtp tcp udp

FFMPEG_PATENTED_DECODERS:= \
	atrac3 \
	h264 \
	hevc \
	vc1 \

FFMPEG_PATENTED_ENCODERS:=$(FFMPEG_PATENDED_DECODERS)

FFMPEG_PATENTED_MUXERS:= \
	h264 \
	hevc \
	vc1 \

FFMPEG_PATENTED_DEMUXERS:=$(FFMPEG_PATENTED_MUXERS)

FFMPEG_PATENTED_PARSERS:= \
	h264 \
	hevc \
	vc1 \

PKG_CONFIG_DEPENDS:= \
	$(patsubst %,CONFIG_FFMPEG_CUSTOM_ENCODER_%,$(FFMPEG_CUSTOM_ENCODERS)) \
	$(patsubst %,CONFIG_FFMPEG_CUSTOM_DECODER_%,$(FFMPEG_CUSTOM_DECODERS)) \
	$(patsubst %,CONFIG_FFMPEG_CUSTOM_MUXER_%,$(FFMPEG_CUSTOM_MUXERS)) \
	$(patsubst %,CONFIG_FFMPEG_CUSTOM_DEMUXER_%,$(FFMPEG_CUSTOM_DEMUXERS)) \
	$(patsubst %,CONFIG_FFMPEG_CUSTOM_PARSER_%,$(FFMPEG_CUSTOM_PARSERS)) \
	$(patsubst %,CONFIG_FFMPEG_CUSTOM_PROTOCOL_%,$(FFMPEG_CUSTOM_PROTOCOLS))

include $(INCLUDE_DIR)/package.mk

define Package/ffmpeg-old/Default
 TITLE:=FFmpeg
 URL:=https://ffmpeg.org/
 DEPENDS+= +libpthread
endef

define Package/ffmpeg-old/Default/description
 FFmpeg is a a software package that can record, convert and stream digital
 audio and video in numerous formats.

 FFmpeg licensing / patent issues are complex. It is the reponsibility of the
 user to understand any requirements in this regard with its usage. See:
 https://ffmpeg.org/legal.html for further information.
endef


define Package/ffmpeg-old
$(call Package/ffmpeg-old/Default)
 SECTION:=multimedia
 CATEGORY:=Multimedia
 TITLE+= program
 DEPENDS+= +libffmpeg-full-old
 VARIANT:=full
endef

define Package/ffmpeg-old/description
$(call Package/ffmpeg-old/Default/description)
 .
 This package contains the FFmpeg command line tool.
endef

define Package/ffprobe-old
$(call Package/ffmpeg/Default)
 SECTION:=multimedia
 CATEGORY:=Multimedia
 TITLE+= CLI media identifier
 DEPENDS+= +libffmpeg-full-old
 VARIANT:=full
endef

define Package/ffprobe-old/description
$(call Package/ffmpeg-old/Default/description)
 .
 This package contains the FFprobe command line tool.
endef

define Package/ffserver-old
$(call Package/ffmpeg-old/Default)
 SECTION:=multimedia
 CATEGORY:=Multimedia
 TITLE+= streaming server
 DEPENDS+= +libffmpeg-full-old
 VARIANT:=full
endef

define Package/ffserver-old/description
$(call Package/ffmpeg-old/Default/description)
 .
 This package contains the FFmpeg streaming server.
endef

define Package/libffmpeg-old/Default
$(call Package/ffmpeg-old/Default)
 SECTION:=libs
 CATEGORY:=Libraries
 TITLE+= libraries
 DEPENDS+= +libpthread +zlib +libbz2
 PROVIDES:= libffmpeg-old
endef


define Package/libffmpeg-full-old
$(call Package/libffmpeg-old/Default)
 TITLE+= (full)
 DEPENDS+= +alsa-lib +PACKAGE_libopus:libopus \
    +SOFT_FLOAT:shine \
    +!SOFT_FLOAT:lame-lib \
    +PACKAGE_libx264:libx264
 VARIANT:=full
endef


define Package/libffmpeg-full-old/description
$(call Package/ffmpeg-old/Default/description)
 .
 This package contains full-featured FFmpeg shared libraries.
endef

# Strip off FPU notation
REAL_CPU_TYPE:=$(firstword $(subst +, ,$(CONFIG_CPU_TYPE)))
# Fixup cpu types recogized by ffmpeg configure
REAL_CPU_TYPE:=$(subst octeonplus,octeon+,$(REAL_CPU_TYPE))

FFMPEG_CONFIGURE:= \
	CFLAGS="$(TARGET_CFLAGS) $(TARGET_CPPFLAGS) $(FPIC)" \
	LDFLAGS="$(TARGET_LDFLAGS)" \
	./configure \
	--enable-cross-compile \
	--cross-prefix="$(TARGET_CROSS)" \
	--arch="$(ARCH)" \
	$(if $(REAL_CPU_TYPE),--cpu=$(call qstrip,$(REAL_CPU_TYPE)),) \
	--target-os=linux \
	--prefix="/usr" \
	--pkg-config="pkg-config" \
	--enable-shared \
	--enable-static \
	--enable-pthreads \
	--enable-zlib \
	--disable-doc \
	--disable-debug \
	\
	--disable-lzma \
	--disable-vaapi \
	--disable-vdpau \
	--enable-outdev=alsa

ifeq ($(CONFIG_SOFT_FLOAT),y)
FFMPEG_CONFIGURE+= \
	--disable-altivec \
	--disable-vsx \
	--disable-power8 \
	--disable-armv5te \
	--disable-armv6 \
	--disable-armv6t2 \
	--disable-inline-asm \
	--disable-mipsdsp \
	--disable-mipsdspr2 \
	--disable-mipsfpu \
	--disable-msa \
	--disable-mmi \
	--disable-fast-unaligned \
	--disable-runtime-cpudetect

else ifneq ($(findstring arm,$(CONFIG_ARCH))$(findstring aarch64,$(CONFIG_ARCH)),)
FFMPEG_CONFIGURE+= \
	--disable-runtime-cpudetect
# XXX: GitHub issue 3320 ppc cpu with fpu but no altivec (WNDR4700)
else ifneq ($(findstring powerpc,$(CONFIG_ARCH)),)
FFMPEG_CONFIGURE+= \
	--disable-altivec
endif

# libavcodec/mips/aacdec_mips.c build problem
# XXX: disable use of assembly on MIPS. Patches welcome.
ifneq ($(findstring mips,$(CONFIG_ARCH)),)
FFMPEG_CONFIGURE+= \
        --disable-asm --disable-inline-asm
endif

# selectively disable optimizations according to arch/cpu type
ifneq ($(findstring arm,$(CONFIG_ARCH)),)
	FFMPEG_CONFIGURE+= --enable-lto

	ifneq ($(findstring vfp,$(CONFIG_CPU_TYPE)),)
		FFMPEG_CONFIGURE+= --enable-vfp
	else
		FFMPEG_CONFIGURE+= --disable-vfp
	endif
	ifneq ($(findstring neon,$(CONFIG_CPU_TYPE)),)
		FFMPEG_CONFIGURE+= \
			--enable-neon \
			--enable-vfp
	else
		FFMPEG_CONFIGURE+= --disable-neon
	endif
endif

ifneq ($(findstring aarch64,$(CONFIG_ARCH)),)
	FFMPEG_CONFIGURE+= \
		--enable-lto \
		--enable-neon \
		--enable-vfp
endif

ifeq ($(ARCH),x86_64)
	FFMPEG_CONFIGURE+= --enable-lto
endif

ifeq ($(CONFIG_FFMPEG_X86ASM),y)
  FFMPEG_CONFIGURE += --enable-x86asm
else
  FFMPEG_CONFIGURE += --disable-x86asm
endif

ifeq ($(BUILD_VARIANT),full)

  FFMPEG_DISABLE= \
	$(foreach c, $(2), \
		--disable-$(1)="$(c)" \
	)

	FFMPEG_CONFIGURE+= \
		--enable-avresample \
		$(if $(CONFIG_BUILD_PATENTED),, \
			$(call FFMPEG_DISABLE,decoder,$(FFMPEG_PATENTED_DECODERS)) \
			$(call FFMPEG_DISABLE,encoder,$(FFMPEG_PATENTED_ENCODERS)) \
			$(call FFMPEG_DISABLE,muxer,$(FFMPEG_PATENTED_MUXERS)) \
			$(call FFMPEG_DISABLE,demuxer,$(FFMPEG_PATENTED_DEMUXERS)) \
			$(call FFMPEG_DISABLE,parser,$(FFMPEG_PATENTED_PARSERS))) \
		$(if $(CONFIG_PACKAGE_libopus),--enable-libopus)
  ifeq ($(CONFIG_SOFT_FLOAT),y)
	FFMPEG_CONFIGURE+= \
		--enable-small \
		\
		$(if $(CONFIG_PACKAGE_shine),--enable-libshine)
  else
	ifeq ($(ARCH),x86_64)
		FFMPEG_CONFIGURE+= --enable-hardcoded-tables
	else
		FFMPEG_CONFIGURE+= --enable-small
	endif
	FFMPEG_CONFIGURE+= $(if $(CONFIG_PACKAGE_lame-lib),--enable-libmp3lame)
  endif
  # x264 support and fdk-aac support can't coexist and be distributed.
  # Prioritize x264 over fdk-aac in default builds (maintain status-quo).
  ifneq ($(CONFIG_PACKAGE_libx264),)
	FFMPEG_CONFIGURE+= \
		--enable-gpl \
		--enable-libx264
  else
	FFMPEG_CONFIGURE+= $(if $(CONFIG_PACKAGE_fdk-aac),--enable-libfdk-aac)
  endif
endif

ifneq ($(CONFIG_TARGET_x86),)
  TARGET_CFLAGS+= -fomit-frame-pointer
endif

define Build/Configure
	( cd $(PKG_BUILD_DIR); $(FFMPEG_CONFIGURE) )
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		DESTDIR="$(PKG_INSTALL_DIR)" \
		all install
endef

# Only ffmpeg with libx264 is GPL (yes libpostproc); all other builds are lgpl (no libpostproc)
define Build/InstallDev/full
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/include/lib{avcodec,avdevice,avfilter,avformat,avresample,avutil,swresample,swscale} $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/lib{avcodec,avdevice,avfilter,avformat,avresample,avutil,swresample,swscale}.{a,so*} $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/lib{avcodec,avdevice,avfilter,avformat,avresample,avutil,swresample,swscale}.pc $(1)/usr/lib/pkgconfig/
ifneq ($(CONFIG_PACKAGE_libx264),)
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libpostproc $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libpostproc.{a,so*} $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libpostproc.pc $(1)/usr/lib/pkgconfig/
endif
endef

# XXX: attempt at installing "best" dev files available
ifeq ($(BUILD_VARIANT),full)
  # XXX: always install "full" dev files if -full is selected
  Build/InstallDev = $(Build/InstallDev/full)
endif

define Package/ffmpeg-old/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/ffmpeg $(1)/usr/bin/
endef

define Package/ffprobe-old/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/ffprobe $(1)/usr/bin/
endef

define Package/ffserver-old/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/ffserver $(1)/usr/bin/
endef


# Only ffmpeg with libx264 is GPL (yes libpostproc); all other builds are lgpl (no libpostproc)
define Package/libffmpeg-full-old/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/lib{avcodec,avdevice,avfilter,avformat,avresample,avutil,swresample,swscale}.so.* $(1)/usr/lib/
ifneq ($(CONFIG_PACKAGE_libx264),)
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libpostproc.so.* $(1)/usr/lib/
endif
endef

$(eval $(call BuildPackage,ffmpeg-old))
$(eval $(call BuildPackage,ffprobe-old))
$(eval $(call BuildPackage,ffserver-old))
$(eval $(call BuildPackage,libffmpeg-full-old))
