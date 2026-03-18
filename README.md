# RNode Flash and Configure Instructions

This guide explains how to flash RNode firmware and configure an RNode device as a Reticulum interface using the **Columba** app on Android.

## Requirements

- Android smartphone with USB OTG support
- USB OTG (On-The-Go) cable
- Compatible RNode device (e.g. Heltec LoRa 32 v3, ESP32-based LoRa board)
- [Columba app](https://github.com/attermann/columba) installed on your Android device

---

## Part 1 — Flashing the Firmware

### Step 1 — Connect the device and open Flash Firmware

Connect your RNode device to your Android phone using a USB OTG cable. The Columba app will detect the USB device and display an action menu. Tap **Flash Firmware** to update or install RNode firmware on the device.

![USB Device Connected menu](imgs/Screenshot_20260318_095556_Columba.jpg)

---

### Step 2 — Grant USB permission

The RNode Flasher wizard will open. A system dialog will appear asking you to allow the Columba app access to the connected USB device. Tap **OK** to grant permission.

![USB permission dialog](imgs/Screenshot_20260318_095602_One%20UI%20Home.jpg)

---

### Step 3 — Select USB device

After granting permission, your device will appear in the list as **Unknown Device** with its USB VID and PID (e.g. VID: 0x303A | PID: 0x0002). Select it (a checkmark will appear) and tap **Continue**.

![Select USB Device](imgs/Screenshot_20260318_095612_Columba.jpg)

---

### Step 4 — Device detection (Manual Selection)

The app will attempt to automatically identify the board type. If auto-detection fails, a **Detection Failed** message will appear. This is normal for generic ESP32 boards. Tap **Continue with Manual Selection** to proceed and choose your board type manually in the next step.

![Detection Failed — Manual Selection](imgs/Screenshot_20260318_095617_Columba.jpg)

---

### Step 5 — Select board type and start flashing

Select your board type from the list (e.g. *Heltec LoRa 32 v3*). The app will download and flash the appropriate firmware. A progress screen will appear showing the current flash percentage and status (e.g. *Syncing with bootloader…*).

> ⚠️ **Do not disconnect the device while flashing is in progress.**

![Flashing Firmware — progress](imgs/Screenshot_20260318_095637_Columba.jpg)

---

### Step 6 — Wait for flashing to complete

The flashing process continues until 100%. Status messages will update as each stage completes (sync, erase, write, verify).

![Flashing Firmware — in progress](imgs/Screenshot_20260318_095642_Columba.jpg)

---

### Step 7 — Flashing done

Once flashing is complete, the wizard will advance to the **Done** screen confirming success. The device will automatically reboot with the new firmware.

![Flashing complete](imgs/Screenshot_20260318_095852_Columba.jpg)

---

### Step 8 — Verify the device

After flashing, the device LED should light up indicating the firmware is running correctly.

![Device after flashing](imgs/20260318_095943.jpg)

---

## Part 2 — Configuring the RNode

### Step 1 — Open Configure RNode

Reconnect or keep the device connected. The USB Device Connected menu will appear again. Tap **Configure RNode** to set up the device as a Reticulum interface.

![USB Device Connected — Configure RNode](imgs/Screenshot_20260318_100017_Columba.jpg)

---

### Step 2 — Enter radio parameters

The configuration screen will open. Set the following radio parameters according to your regional frequency plan and network requirements:

- **Frequency** — carrier frequency in MHz (e.g. `868.0` for Europe, `915.0` for North America)
- **Bandwidth** — channel bandwidth (e.g. `250 kHz`)
- **TX Power** — transmit power in dBm (e.g. `17`)
- **Spreading Factor** — LoRa spreading factor (e.g. `8`)
- **Coding Rate** — LoRa coding rate (e.g. `5`)

![Configure RNode — parameters](imgs/Screenshot_20260318_100056_Columba.jpg)

---

### Step 3 — Physical device during configuration

The device remains connected via USB throughout the configuration process.

![Device during configuration](imgs/20260318_100150.jpg)

---

### Step 4 — Apply configuration

Review your settings and tap **Apply** or **Save** to write the configuration to the device.

![Apply configuration](imgs/Screenshot_20260318_100343_Columba.jpg)

---

### Step 5 — Confirm settings

The app may display a confirmation or summary of the written configuration.

![Configuration confirmation](imgs/Screenshot_20260318_100354_Columba.jpg)

---

### Step 6 — Configuration complete

The RNode will be configured and ready to operate as a Reticulum interface. A success message will confirm the configuration has been saved to the device.

![Configuration saved](imgs/Screenshot_20260318_100358_Columba.jpg)

---

### Step 7 — Reticulum interface ready

The device is now configured and will appear as a LoRa interface in Reticulum. You can verify it is active in the Columba app's interface list.

![Interface active](imgs/Screenshot_20260318_100704_Columba.jpg)

---

## Additional Options

The USB Device Connected menu also offers:

| Option | Description |
|---|---|
| **Configure Transport** | Set radio parameters for standalone transport (router) mode |
| **Disable Transport** | Clear saved transport config and return the device to normal interface mode |
