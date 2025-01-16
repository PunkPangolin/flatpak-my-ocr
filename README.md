# OCRmyPDF Flatpak Maintenance Documentation

## TODO metainfo.xml

Will be part of upstream in the next tag (probably 16.9.0), replace file with `src/ocrympdf/data/io.ocrmypdf.ocrmypdf.xml` in manifest and remove the file from the GitHub repository.

## flatpak-external-data-checker and updates

Checks every module for updates, but will only raise a PR when `ocrmypdf` gets an update. This PR will include all updates available at this point.

`pngquant`, `python3-maturin` and `python3-cryptography` are built using rust and will require new, manually generated `cargo-sources-${module}.json` files when updated.

## pikepdf

Utilizes a submodule for the pikepdf manifest. `dependabot` is configured to check for updates daily.

## python modules

Everything was generated with `flapak-pip-generator` and is organized in this structure to make maintenance easy. All python modules use `noarch` wheels (where available) or are built from source.

`python3-sphinx`is required to build documentation of `pngquant`

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
