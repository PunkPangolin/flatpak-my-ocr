# OCRmyPDF Flatpak Maintenance Documentation

## rust modules

`pngquant` is built using rust and will require new, manually generated `cargo-sources-pngquant.json` when updated.

## python modules

`python3-sphinx`is required to build documentation of `pngquant`

`python3-requirements.json` includes the following packages in this order:

```
lxml
pybind11
pikepdf
deprecation
img2pdf
packaging
pdfminer.six
pi-heif
Pillow
pluggy
rich
hatch-vcs
pygments
```

`pikepdf` requires qpdf

`cryptography`(dep of `pdfminer.six`) uses arch-dependent wheels and requires manual updates.

`pygments` has to be added manually and with `--ignore-installed` flag because it is part of the SDK (but not of the runtime) and gets skipped otherwise.
