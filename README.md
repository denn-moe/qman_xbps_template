# xbps-src template for qman


```bash
git clone https://github.com/void-linux/void-packages.git
git clone https://github.com/denn-moe/qman_xbps_template.git
cp -r qman_xbps_template/{cogapp,qman} void-packages/srcpkgs
cd void-packages
./xbps-src binary-bootstrap
./xbps-src pkg qman

```
