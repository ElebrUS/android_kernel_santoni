dtb-$(CONFIG_ARCH_MSM8940) += msm8940-pmi8950-fdt.dtb 
dtb-$(CONFIG_ARCH_MSM8940_inbuilt) += msm8940-pmi8950-fdt1.dtb 

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/,$(dtb-y))
endif
clean-files := *.dtb
