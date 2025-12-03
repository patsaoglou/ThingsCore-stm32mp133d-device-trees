# ThingsCore 1
The device trees for the ThingsCore 1 System-on-Module are shared. 
Link:https://dreamxlabs.gr/

# Bootchain
The device trees base is generated using STM32CubeIDE and boot chain of TF-A->OP-TEE->UBOOT->LINUX is succeeded. The device trees are configured for 512MB of DDR3 ram and LAN (LAN8742), USB, NOR, 8GB eMMC are recogninsed successfully.

For the binaries, the patched sources of TF-A, OP-TEE, UBOOT and linux by STMicroelectronics are used, found at the OpenSTLinux Developer Package.

If different size of RAM is used, the memory node of each stage must be changed but also the TF-A-FW-CONFIG files so TF-A knows on which memory section to find the entry point for OP-TEE and UBOOT. Also be mind that the dtsi of the SOC must be included in the project's uboot dtsi so the peripfheralls like serial and USB OTG are registered successfully to uboot.
