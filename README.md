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

# cross compile
./xbps-src -a i686 pkg qman
./xbps-src -a x86_64 pkg qman
./xbps-src -a aarch64 pkg qman
# etc.

# NOTE: as of now, musl builds fail with
FAILED: [code=1] src/qman.p/program.c.o
i686-linux-musl-gcc -Isrc/qman.p -Isrc -I../src -I/usr/i686-linux-musl/usr/include -flto=auto -fdiagnostics-color=always -DNDEBUG -D_FILE_OFFSET_BITS=64 -Wall -Winvalid-pch '-DQMAN_CONFIGDIR="/etc/xdg/qman"' -DQMAN_GZIP=true -DQMAN_BZIP2=true -DQMAN_LZMA=true -fstack-clash-protection -D_FORTIFY_SOURCE=2 -O2 -pipe -march=i686 -ffile-prefix-map=/builddir/qman-1.5.0/build=. -DLIBBSD_OVERLAY -isystem /usr/i686-linux-musl/usr/include/bsd -DNCURSES_WIDECHAR -MD -MQ src/qman.p/program.c.o -MF src/qman.p/program.c.o.d -o src/qman.p/program.c.o -c ../src/program.c
../src/program.c: In function 'man_loc':
../src/program.c:392:21: error: implicit declaration of function 'strcasestr'; did you mean 'wcscasestr'? [-Wimplicit-function-declaration]
  392 |         combo_ptr = strcasestr(dst, combo);
      |                     ^~~~~~~~~~
      |                     wcscasestr
../src/program.c:392:19: error: assignment to 'char *' from 'int' makes pointer from integer without a cast [-Wint-conversion]
  392 |         combo_ptr = strcasestr(dst, combo);
      |                   ^

```
