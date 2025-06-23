## Parent Catalog of DESI DR1 Quasars for CIV Doublet Search

This file contains the details of **DESI DR1 Quasars** that were searched for **CIV absorbers**.

- **QSO Catalog Filename**: `dr1-QSO_healpix_cat_for_CIV_search.fits`
    This is the DESI DR1 QSO catalog file. It contains 94,986 unique Quasars that were searched for CIV absorbers absorber. The full datamodel for the catalog is below:

- **Citation**: If you use this catalog in your work, please cite [Anand et al. 2025](https://arxiv.org/abs/2504.20299). The paper describes the methodology, completeness, and limitations.

- Please see the **data model and column descriptions** below for details on the catalog format. There are also some **important usage notes** at the end that users should review before using the catalog.

## Data Model

| **Name**           | **Type**         | **Units** | **Description** |
|--------------------|------------------|-----------|-----------------|
| `TARGETID`         | int64            | —         | Unique DESI target ID |
| `Z`                | float64          | —         | quasar redshift |
| `ZERR`             | float64          | —         | Estimated error on updated redshift |
| `ZWARN`            | int64            | —         | Redshift warning bitmask for updated redshift ([see ZWARN docs](https://github.com/desihub/redrock/blob/main/py/redrock/zwarning.py)) |
| `CHI2`             | float64          | —         | Chi-squared of template fit at best-fit redshift |
| `COEFF`            | float64[4]       | —         | Coefficients of updated QSO-HIZ for best fit |
| `NPIXELS`          | int64            | —         | Number of input pixels (wavelengths) included in fit |
| `TARGET_RA`        | float64          | deg       | Right Ascension in decimal degrees (J2000) |
| `TARGET_DEC`       | float64          | deg       | Declination in decimal degrees (J2000) |
| `DESI_TARGET`      | int64            | —         | DESI target selection bitmask |
| `HPXPIXEL`         | int64            | —         | HEALPixel containing target at HPXNSIDE |
| `SURVEY`           | string           | —         | Survey name (e.g., `"main"`) |
| `PROGRAM`          | string           | —         | Program name (e.g., `"dark"`) |
| `BI_CIV`           | float64          | km/s      | Equivalent width of CIV absorption by Balnicity Index (BI) definition |
| `ERR_BI_CIV`       | float64          | km/s      | Uncertainty in `BI_CIV`; infinity indicates a potentially problematic fit |
| `NCIV_2000`        | int64            | —         | Number of CIV absorption troughs extending >2000 km/s |
| `VMIN_CIV_2000`    | float64[5]       | km/s      | Minimum velocity of BI absorption troughs blueward of CIV |
| `VMAX_CIV_2000`    | float64[5]       | km/s      | Maximum velocity of BI absorption troughs blueward of CIV |
| `AI_CIV`           | float64          | km/s      | Equivalent width of CIV absorption by Absorption Index (AI) definition |
| `ERR_AI_CIV`       | float64          | km/s      | Uncertainty in `AI_CIV`; infinity indicates a potentially problematic fit |
| `NCIV_450`         | int64            | —         | Number of CIV absorption troughs extending >450 km/s |
| `VMIN_CIV_450`     | float64[17]      | km/s      | Minimum velocity of AI absorption troughs blueward of CIV |
| `VMAX_CIV_450`     | float64[17]      | km/s      | Maximum velocity of AI absorption troughs blueward of CIV |
| `ZMASK`            | float64          | —         | Redshift after masking AI_CIV > 0 BAL features |
| `MEANSNR`            | float64          | —         | Mean signal-to-noise ratio for quasars from continuum modeling |
### **Contact**

- Please write to abhijeetanand2011@gmail.com, if you have questions.
