# CIV Absorber Catalog (CIV_healpix-dr1-cat-v1.fits)

This file contains the details of **CIV absorbers** detected in **DESI DR1 Quasars**.

---

## **HDU1: ABSORBER**
This HDU contains information on detected **CIV absorbers**.

| **Keyword**           | **Type**         | **Description** |
|-----------------------|-----------------|----------------|
| `Z_ABS`              | *(float)*        | Redshift of the absorber. |
| `CIV_1548_EW`        | *(float)*        | Rest-frame equivalent width (EW) of **CIV 1548** (Å). |
| `CIV_1550_EW`        | *(float)*        | Rest-frame equivalent width (EW) of **CIV 1550** (Å). |
| `CIV_EW_TOTAL`       | *(float)*        | Total rest-frame equivalent width (EW) of **CIV doublet** (Å). |
| `CIV_1548_EW_ERROR`  | *(float)*        | **1σ error** on **CIV 1548** EW (Å). |
| `CIV_1550_EW_ERROR`  | *(float)*        | **1σ error** on **CIV 1550** EW (Å). |
| `CIV_EW_TOTAL_ERROR` | *(float)*        | **1σ error** on total **CIV doublet** EW (Å). |
| `Z_ABS_ERR`          | *(float)*        | Measured error in the absorber redshift. |
| `GAUSS_FIT`          | *(numpy array)*  | Rest-frame **double Gaussian fitting parameters** for the absorber doublet. |
| `GAUSS_FIT_STD`      | *(numpy array)*  | **Uncertainties** in **double Gaussian fitting parameters**. |
| `SN_CIV_1548`        | *(float)*        | **SNR** of **1548 line** from residual and errors. |
| `SN_CIV_1550`        | *(float)*        | **SNR** of **1550 line** from residual and errors. |
| `CIV_1548_VDISP`     | *(float)*        | Rest-frame **intrinsic velocity dispersion** (corrected for instrumental resolution) for **CIV 1548** (km/s). |
| `CIV_1550_VDISP`     | *(float)*        | Rest-frame **intrinsic velocity dispersion** (corrected for instrumental resolution) for **CIV 1550** (km/s). |
| `CORRECTED_N`        | *(float)*        | Completeness-corrected absorber count. |
| `LOG10N`             | *(float)*        | log of **total column density** (in cm<sup>-2</sup>), calculated from apparent optical depth method. |
| `SIG_LOG10N`         | *(float)*        | uncertainty on log of **total column density** (in cm<sup>-2</sup>), calculated from apparent optical depth method. |
| `SATURATION`         | *(int)*          | saturation flag, 1: saturated, 0: unsaturated  |
| `fN`                 | *(int)*          | Column density measurement method, 1: weighted mean, 2: only first line, 3: only second line, -1: failure. |

---

## **HDU2: METADATA**
This HDU contains **metadata** related to the observed quasars.

| **Keyword**   | **Type**       | **Description** |
|--------------|---------------|----------------|
| `LOS_ID`     | *(int)*        | Line-of-sight (LOS) ID in **picca continuum modeling** (**same as TARGETID**). |
| `RA`         | *(float)*      | **Right Ascension** of quasars (°). |
| `DEC`        | *(float)*      | **Declination** of quasars (°). |
| `Z_QSO`      | *(float)*      | Redshift of quasars. |
| `MEANSNR`    | *(float)*      | **Mean signal-to-noise ratio** of the quasar spectrum from picca. |
| `TARGETID`   | *(int)*        | **DESI unique identifier** for each object. |
| `SURVEY`     | *(str)*        | **Survey name** in which the object was observed. |
| `PROGRAM`    | *(str)*        | **Program name** in which the object was observed. |
| `HPXPIXEL`   | *(int)*        | **Healpix ID** for the spectrum, do HPXPIXEL//100 to get the healpix directory name. |
| `ZQSO_ERR`   | *(float)*      | Error on **quasar redshift**. |
| `TSNR2_LRG`  | *(float)*      | Template signal-to-noise ratio for each quasar. Can be used to calculate effective exposure time, T<sub>eff</sub> = 12.15 x TSNR2\_LRG. |

---

### **Notes**
- This catalog is based on **DESI DR1 Quasars** and contains CIV absorbers identified in the spectra.
  
- Rest-frame equivalent widths (EWs) are measured in **Angstroms (Å)**.
  
- **Velocity dispersions (VDISP)** are corrected for instrumental resolution and given in **km/s**.
  
- In version `qsoabsfind/v1.0.3` (used to construct the original catalog), a small bug affected the estimation of velocity dispersion — specifically, the instrumental resolution was underestimated by a factor of 2.355. All **VDISP** values have been recomputed in the current catalog using the correct resolution. As a result, ~3% of systems now have **VDISP = 0**, indicating unresolved lines. Most of these are visually confirmed to be genuine absorbers and are therefore retained in the catalog and analysis.

- This bug has been fixed in `qsoabsfind/v1.0.5`, and any future catalogs built from `version >= v1.0.5` will automatically have to correct velocity dispersions for the lines.

- **For any issues or questions, please refer to Anand et al. 2025 (arXiv:).** 
