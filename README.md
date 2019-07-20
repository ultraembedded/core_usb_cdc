### USB CDC Device

Github:   [http://github.com/ultraembedded/core_usb_cdc](https://github.com/ultraembedded/core_usb_cdc)

This component is a simple USB Peripheral Interface (Device) implementation which enumerates as a full speed CDC-ACM device (12Mbit/s).

This IP has a simple FIFO interface (valid, data, accept) for input and output data, and an UTMI interface for connection to a USB PHY.

##### Features
* Full speed USB CDC device.
* Enumeration in hardware - no SW intervention required.
* UTMI PHY interface (see my UTMI to ULPI Conversion wrapper project to allow connection to a ULPI PHY e.g. USB3300)
* Simple 8-bit data input / output interface with handshaking (compliant with a 8-bit wide AXI4-Stream interface).

##### Configuration / Requirements
* Top: usb_cdc_core
* Clock: clk_i - 48MHz
* Reset: rst_i - Asynchronous, active high
* VID/PID can be changed in usb_desc_rom.v

##### Limitations
* Really basic USB-CDC class device implementation, will ignore encap, line state and line coding change requests!

##### Testing
Verified under simulation then tested on FPGA against Linux, Windows and MAC OS-X.

##### References
* [USB 2.0 Specification](https://usb.org/developers/docs/usb20_docs)
* [UTMI Specification](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb2-transceiver-macrocell-interface-specification.pdf)
* [USB Made Simple](http://www.usbmadesimple.co.uk/)
* [UTMI to ULPI Conversion](https://github.com/ultraembedded/cores/tree/master/ulpi_wrapper)
* [USB Full Speed PHY](https://github.com/ultraembedded/core_usb_fs_phy)