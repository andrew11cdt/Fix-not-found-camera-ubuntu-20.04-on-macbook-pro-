# Fix-not-found-camera-ubuntu-20.04-on-macbook-pro
I wiped out MacOS and install Ubuntu on my macbook pro 2015 after getting freezing macOS (when updated version).
But the problem is Camera of Mac could not found.
After several hours, finally I found solutions that is install firmware of facetimehd for fixing "Not found camera" error.
```
cd /etc/local/src
git clone https://github.com/patjak/bcwc_pcie.git
cd bcwc_pcie/firmware
git clone https://github.com/patjak/facetimehd-firmware
cd facetimehd-firmware
sudo make
sudo make install
cd ../..
sudo make
sudo make install   # (Update with make install for 18.04)    
sudo depmod
sudo modprobe -r bdc_pci
sudo modprobe facetimehd
```

issue ref: [here](https://itectec.com/ubuntu/ubuntu-macbook-pro-camera-not-working-on-ubuntu-18-04/)
