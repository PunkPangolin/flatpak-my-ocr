# flatpak-my-ocr

Flatpak build manifest for ocrmypdf. ~~This is just a private project, but someone might find it interesting. As far as I know, Flathub does not accept non-GUI programs, but you can build and run the flatpak manually.~~ Intended to be upstreamed someday.

Beware: Everything here is chaotic. Use at your own risk!

### Information regarding python modules

Everything generated with `flapak-pip-generator` and organized to make maintenance easy.

`python3-sphinx`is required to build `pngquant`

`python3-setuptools_rust` is required to build `python3-maturin`

`python3-maturin` is required to build `python3-cryptography`, is built with cargo and requires manual work

`python3-cffi` is required to build `python3-cryptography`

`python3-cryptography`is built with cargo, is built with cargo and requires manual work

`python3-pygments` is a runtime dependency of ocrmypdf and has to be added manually, because it gets skipped by `flatpak-pip-generator`

`python3-requirements.json` includes the following packages:

```
deprecation
img2pdf
packaging
pdfminer.six
pi-heif
Pillow
pluggy
rich
hatch-vcs
```
