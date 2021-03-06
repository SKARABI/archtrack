**ArchTrack is now [BlackArch](http://blackarch.org/). The new development repository is here: https://github.com/BlackArch/blackarch**

## What is this?

Archtrack is able to turn an Arch Linux system into a fully functional
penetration testing system. There is a working pre-release of the Archtrack
package repository.

## Installation

### From the Archtrack unofficial user repository (recommended)

You can install the latest Archtrack pre-release from the Archtrack unofficial
user repository.

1. Add this to your `/etc/pacman.conf` file:

    ```
    [archtrack]
    SigLevel = Optional TrustAll
    Server = http://tixod.com
    ```

2. The repository has category groups. Run `pacman -Sg | grep archtrack-` to
   see them all. The 'archtrack' group contains all of the archtrack
   packages.
3. Some of the archtrack packages depend on AUR packages, so you should use a
   pacman+AUR wrapper such as yaourt to install Archtrack packages.
4. Try to install everything: `yaourt -Sy archtrack`. You will almost
   definitely find yourself face-to-face with a series of package conflicts.
   Take note of which packages are conflicting.
5. Install the conflicting packages. Make sure not to use the `--noconfirm`
   flag.
6. Run `yaourt --noconfirm -S archtrack`. Yaourt has to build an insane
   number of dependencies from the AUR, so you will almost definitely want to
   pass it the `--noconfirm` flag.

We're working on making the installation smoother. We plan on making an
Archtrack ISO as well.

Note that the tixod.com URL is temporary. We are working on obtaining the
archtrack.org domain name. These instructions are subject to change as well.

Here is proof that the current pre-release works: http://flic.kr/p/eGxE8e

You should consider installing Archtrack in a special root. To do this, take
a look at the 'extra/devtools' and 'extra/arch-install-scripts' packages.

More detailed installation instructions will be added later.

### From the AUR

You can also install archrack from the AUR (see https://aur.archlinux.org/packages/archtrack/)

If you choose to install Archtrack from the AUR, you may want to use an AUR
helper such as yaourt or packar.

If you install these packages with a AUR helper such as yaourt or packer, do
not run the AUR helper as root. These packages have massive dependency lists,
making it nearly impossible to check each depended-on PKGBUILD file for
malicious code.

Note that installing Archtrack from the AUR can be unreliable.
