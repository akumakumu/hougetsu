## Dev Notes Under WSL2

### PowerShell

```powershell
# Listing USB device
usbipd list

# Bind to share device
usbipd bind -b [busid]

# Attach device to WSL2
usbipd attach --wsl --busid [busid]
```

### WSL2

```bash
# Check the attached device
lsusb

# Clear the tty
sudo chmod a+rw /dev/ttyACM*

# Source ESP-IDF Tools
# I'm using ESP-IDF version 5.3.1 atm
. $HOME/esp/v5.3/esp-idf/export.sh

# Specify your dev board
idf.py set-target esp32s3

# Build the project
idf.py build

# Flash to dev board
idf.py -p [port] flash
```