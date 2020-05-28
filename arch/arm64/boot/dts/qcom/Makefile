ifeq ($(CONFIG_MACH_ASUS_MSM8916),y)
dtb-$(CONFIG_ARCH_MSM8916) += msm8916-mtp-ze550kl.dtb \
	msm8939-cdp-ze550kl.dtb \
	msm8939-cdp-ze600kl.dtb \
	msm8939-cdp-zd550kl.dtb
else
dtb-$(CONFIG_ARCH_MSM8916) += msm8916-cdp.dtb \
	msm8916-cdp-smb1360.dtb \
	msm8916-mtp.dtb \
	msm8916-mtp-smb1360.dtb \
	msm8916-qrd-skuh.dtb \
	msm8916-qrd-skuhf.dtb \
	msm8916-qrd-skui.dtb \
	msm8916-qrd-skuic.dtb \
	msm8916-qrd-skuid.dtb \
	msm8916-qrd-skut1.dtb \
	apq8016-mtp.dtb \
	apq8016-mtp-smb1360.dtb \
	apq8016-sbc.dtb \
	msm8939-qrd-skuk.dtb \
	msm8939-qrd-skul.dtb \
	msm8939-cdp.dtb \
	msm8939-cdp-jdi.dtb \
	msm8939-mtp.dtb \
	msm8939-mtp-jdi.dtb \
	msm8939-mtp-smb1360.dtb \
	msm8939-mtp-wcd9306.dtb \
	msm8939-v3.0-qrd-skuk.dtb \
	msm8939-v3.0-qrd-skul.dtb \
	msm8939-v3.0-cdp.dtb \
	msm8939-v3.0-cdp-jdi.dtb \
	msm8939-v3.0-mtp.dtb \
	msm8939-v3.0-mtp-jdi.dtb \
	msm8939-v3.0-mtp-smb1360.dtb \
	msm8939-v3.0-mtp-wcd9306.dtb \
	msm8936-qrd-skuk.dtb \
	msm8936-cdp.dtb \
	msm8936-cdp-smb1360.dtb \
	msm8936-mtp.dtb \
	msm8936-mtp-smb1360.dtb \
	msm8936-mtp-wcd9306.dtb \
	msmtellurium-sim.dtb \
	msmtellurium-rumi.dtb \
	msm8929-cdp.dtb \
	msm8929-mtp.dtb \
	msm8929-mtp-smb1360.dtb \
	msm8929-mtp-jdi-smb1360.dtb \
	msm8929-mtp-wcd9306-smb1360.dtb \
	msm8929-qrd-skul.dtb \
	msm8929-qrd-skulb.dtb \
	msm8929-cdp-jdi.dtb
endif

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif

targets += dtbs
targets += $(addprefix ../, $(DTB_LIST))

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(DTB_LIST))

clean-files := *.dtb
