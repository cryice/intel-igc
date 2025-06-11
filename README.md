# intel-igc
Linux 6.6.0 kernel driver for Intel(R) I225-V 2.5G Ethernet Controller

## Installation

Install it from source with:

```
git clone https://github.com/cryice/intel-igc.git
cd intel-igc

sudo dkms add .
sudo dkms build igc -v 6.6.0-72.6.0.56
sudo dkms install --force igc -v 6.6.0-72.6.0.56
```
