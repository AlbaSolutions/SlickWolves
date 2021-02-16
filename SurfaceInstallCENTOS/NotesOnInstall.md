## Best instructions:

https://github.com/linux-surface/linux-surface/wiki/Installation-and-Setup
* currently running from https://pkg.surfacelinux.com/fedora/f33/
* linux-surface.repo file
```bash
$ sudo dnf config-manager \
    --add-repo=https://pkg.surfacelinux.com/fedora/linux-surface.repo
```
### Need to get a kernel then get iptsd installed for touch integration
  1. should be a iptsd/ located in folder
  2. if not then pull from  https://github.com/linux-surface/iptsd
  3.  follow readme from that github source
  4.  the build of iptsd should install inih lib
  5. if not, there should be meson build from python under the inih dir
  6. pip3 install meson ninja  (to build the packages)
    -https://github.com/mesonbuild/meson
```bash
    $ git clone https://github.com/linux-surface/iptsd
    $ cd iptsd
    $ meson build
    $ ninja -C build
    $ sudo ./build/iptsd
```
## You will need to enable iptsd in systemd if ninja doesn't workout


```bash
    $ sudo systemctl enable iptsd
    $ sudo systemctl start iptsd    
```
* A reboot will wouldn't hurt...
