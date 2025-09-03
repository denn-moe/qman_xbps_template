# xbps-src template for qman


```bash
# clone void-packages repo
git clone https://github.com/void-linux/void-packages.git

# clone this repo
git clone https://github.com/denn-moe/qman_xbps_template.git

# copy templates to srcpkgs
cp -r qman_xbps_template/{cogapp,qman} void-packages/srcpkgs

# cd into void-packages
cd void-packages

# prepare build environment
./xbps-src binary-bootstrap

# compile qman
./xbps-src pkg qman

# install qman
sudo xi -f qman
```
