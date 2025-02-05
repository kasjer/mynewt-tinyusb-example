# mynewt-tinyusb-example

![tinyUSB_240x100](https://user-images.githubusercontent.com/249515/62646655-f9393200-b978-11e9-9c53-484862f15503.png)

[![Build Status](https://travis-ci.com/hathach/mynewt-tinyusb-example.svg?branch=master)](https://travis-ci.com/hathach/mynewt-tinyusb-example) [![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

Due to the newt package build system, Mynewt examples are better to be a spin-off from the [main stack repo](https://github.com/hathach/tinyusb). To run the examples

- Firstly check out the [official Mynewt documentation](https://mynewt.apache.org/documentation/) to set up and install newt tool
- Clone and install dependency repos

```
$ git clone https://github.com/hathach/mynewt-tinyusb-example.git
$ cd mynewt-tinyusb-example
$ newt install
```

## Supported Boards

Examples should be able to run with boards that are supported by Mynewt, provided that the mcu is already supported by TinyUSB stack. Following is board that is mainly used and tested

- [Nordic nRF52840 Development Kit (aka pca10056)](https://www.nordicsemi.com/Software-and-Tools/Development-Kits/nRF52840-DK)
- [STM32F407g Discovery](https://www.st.com/en/evaluation-tools/stm32f4discovery.html) Note: work in progress, not able to blink LED just yet.

### Nordic nRF52840DK PCA10056

Build and load bootloader

```
$ newt build pca10056_boot
$ newt load pca10056_boot
```

Now we can build tinyusb example, create image and load it

#### CDC MSC HID composite example

This example enumerated as composite device with CDC, MSC and HID

```
$ newt build pca10056_cdc_msc_hid
$ newt create-image pca10056_cdc_msc_hid 1.0.0
$ newt load pca10056_cdc_msc_hid
```

#### MSC dual Logical Unit

This example enumerated as mass storage with dual ram disk

```
$ newt build pca10056_msc_dual_lun
$ newt create-image pca10056_msc_dual_lun 1.0.0
$ newt load pca10056_msc_dual_lun
```


## STMicroeclectronic STM32F4 Discovery

Work in progresss, not able to blink LED just yet.