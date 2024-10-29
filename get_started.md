# Get Started
## If you are going be analyzing the requests
To analyze the request/response from the keyboard you need to install:

- [Wireshark](https://github.com/wireshark/wireshark)
- [USBPcap](https://github.com/desowin/usbpcap)

## If you are going to test or write custom software
For writing custom software or testing, you need to install (Recommended):

- [LibUSB](https://github.com/libusb/libusb)
- [PyUSB](https://github.com/pyusb/pyusb) (or any other wrapper library for libusb in another programming language)

## VENDOR_ID and PRODUCT_ID
You must use the **correct VID and PID** to communicate with the device!

_Default value:_

| VID    | PID    |
|--------|--------|
| 0x1A2C | 0x9CF4 |

If the default values are not suitable, **find the VID and PID manually.**
- **Windows**: use device manager (information -> equipment ID)
- **Linux**: use command in terminal
  
    ``bash
      dmesg | grep -i usb
    ``
## Protocols
Two protocols are used to communicate with the keyboard:

| Protocol | It's used                                                           |
|----------|---------------------------------------------------------------------|
| USB      | Low-level USB packets, e.g. used to process keystrokes              |
| USBHID   | A high protocol that supports additional commands for configuration |

## USBHID command parameters

| Parameter     | Value(s) | Mutable | Description                                                                                                        |
|---------------|----------|---------|--------------------------------------------------------------------------------------------------------------------|
| bmRequestType | 0x21     | No      | Determines the type of USB request                                                                                 |
| bmRequest     | 0x09     | No      | The exact request or command being issued to the USB device                                                        |
| wValue        | ?        | Yes     | Provides additional information or parameters for the request specified                                            |
| wIndex        | ?        | Yes     | Specifies the index or identifier associated with the request                                                      |
| wLength       | ?        | Yes     | How many bytes of data the host expects to send to or receive from the USB device as part of a control transfer    |
| data          | ?        | Yes     | The payload of information that is sent to or received from the USB device after the control transfer setup packet |

[?] - can have many different meanings

#### Refer to the [protocol documentation](protocol/main.md) to obtain the available values of the fields to be mutable