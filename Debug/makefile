################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (10.3-2021.10)
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Third_Party/SEGGER/SEGGER/subdir.mk
-include Third_Party/SEGGER/OS/subdir.mk
-include Third_Party/SEGGER/Config/subdir.mk
-include Third_Party/FreeRTOS/portable/MemMang/subdir.mk
-include Third_Party/FreeRTOS/portable/GCC/ARM_CM4F/subdir.mk
-include Third_Party/FreeRTOS/subdir.mk
-include Drivers/STM32F4xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

OPTIONAL_TOOL_DEPS := \
$(wildcard ../makefile.defs) \
$(wildcard ../makefile.init) \
$(wildcard ../makefile.targets) \


BUILD_ARTIFACT_NAME := FREERTOS_EmulatorTesting
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
FREERTOS_EmulatorTesting.elf \

MAP_FILES += \
FREERTOS_EmulatorTesting.map \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
FREERTOS_EmulatorTesting.list \

OBJCOPY_HEX += \
FREERTOS_EmulatorTesting.hex \


# All Target
all: main-build

# Main-build Target
main-build: FREERTOS_EmulatorTesting.elf secondary-outputs

# Tool invocations
FREERTOS_EmulatorTesting.elf FREERTOS_EmulatorTesting.map: $(OBJS) $(USER_OBJS) D:\EMBEDDED\RTOS\FREERTOS_EmulatorTesting\STM32F405RGTX_FLASH.ld makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-gcc -o "FREERTOS_EmulatorTesting.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m4 -T"D:\EMBEDDED\RTOS\FREERTOS_EmulatorTesting\STM32F405RGTX_FLASH.ld" --specs=nosys.specs -Wl,-Map="FREERTOS_EmulatorTesting.map" -Wl,--gc-sections -static --specs=nano.specs -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

FREERTOS_EmulatorTesting.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "FREERTOS_EmulatorTesting.list"
	@echo 'Finished building: $@'
	@echo ' '

FREERTOS_EmulatorTesting.hex: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objcopy  -O ihex $(EXECUTABLES) "FREERTOS_EmulatorTesting.hex"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) FREERTOS_EmulatorTesting.elf FREERTOS_EmulatorTesting.hex FREERTOS_EmulatorTesting.list FREERTOS_EmulatorTesting.map default.size.stdout
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST) $(OBJCOPY_HEX)

fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

.PHONY: all clean dependents main-build fail-specified-linker-script-missing warn-no-linker-script-specified

-include ../makefile.targets
