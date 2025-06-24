## CIV Absorber Catalog from DESI DR1 Quasars

This file contains the details of **C IV absorbers** (a doublet at rest-frame wavelengths 1548 and 1550 Å) detected in **DESI DR1 quasar spectra**.

- **Absorber Catalog Filename**: `CIV_healpix-dr1-cat-v1.fits`

    This is the CIV absorber catalog file. It contains 32,321 CIV absorber systems detected in 94,986 Quasars from DESI DR1. Each entry corresponds to a detected absorber, with columns described in the data model below. Note that `TARGETID` is not a unique identifier, as multiple absorbers can be found along the line of sight to a single target. To uniquely specify an absorber, use the combination of TARGETID and `Z_ABS`.

- **Citation**: If you use this catalog in your work, please cite [Anand et al. 2025](https://arxiv.org/abs/2504.20299) and [Anand et al. 2021](https://arxiv.org/abs/2103.15842). These two papers describe the methodology, completeness, and limitations.

- **Codebase**: The pipeline used to generate this catalog is open source and available at: [https://github.com/abhi0395/qsoabsfind](https://github.com/abhi0395/qsoabsfind)

- Please see the **data model and column descriptions** below for details on the catalog format. There are also some **important usage notes** at the end that users should review before using the catalog.
  
---

## **HDU1: ABSORBER**
This HDU contains information on detected **CIV absorbers**.

| **Keyword**           | **Type**         | **Units**      | **Description** |
|-----------------------|------------------|----------------|-----------------|
| `Z_ABS`              | *(float64)*       | —              | Redshift of the absorber. |
| `CIV_1548_EW`        | *(float64)*       | Å              | Rest-frame equivalent width (EW) of **CIV 1548** (Å). |
| `CIV_1550_EW`        | *(float64)*       | Å              | Rest-frame equivalent width (EW) of **CIV 1550** (Å). |
| `CIV_EW_TOTAL`       | *(float64)*       | Å              | Total rest-frame equivalent width (EW) of **CIV doublet** (Å). |
| `CIV_1548_EW_ERROR`  | *(float64)*       | Å              | **1σ error** on **CIV 1548** EW (Å). |
| `CIV_1550_EW_ERROR`  | *(float64)*       | Å              | **1σ error** on **CIV 1550** EW (Å). |
| `CIV_EW_TOTAL_ERROR` | *(float64)*       | Å              | **1σ error** on total **CIV doublet** EW (Å). |
| `Z_ABS_ERR`          | *(float64)*       | —              | Measured error in the absorber redshift. |
| `GAUSS_FIT`          | *(numpy array, float64)*  | —      | Rest-frame **double Gaussian fitting parameters** for the absorber doublet. (`Amp1`, `line_center1`, `sigma1`, `Amp2`, `line_center2`, `sigma2`). These correspond to the amplitudes, line centers, and Gaussian widths (σ) for the 1548 Å and 1550 Å components, respectively. |
| `GAUSS_FIT_STD`      | *(numpy array, float64)*  | —      | **Uncertainties** in **double Gaussian fitting parameters**. |
| `SN_CIV_1548`        | *(float64)*       | —              | **SNR** of **1548 line** from residual and errors. |
| `SN_CIV_1550`        | *(float64)*       | —  | **SNR** of **1550 line** from residual and errors. |
| `CIV_1548_VDISP`     | *(float64)*       | km/s           | Rest-frame **intrinsic velocity dispersion** (corrected for instrumental resolution) for **CIV 1548** (km/s). |
| `CIV_1550_VDISP`     | *(float64)*       | km/s           | Rest-frame **intrinsic velocity dispersion** (corrected for instrumental resolution) for **CIV 1550** (km/s). |
| `CORRECTED_N`        | *(float64)*       | —  | Completeness-corrected absorber count. |
| `LOG10N`             | *(float64)*       | cm⁻² (log10)   | log of **total column density** (in cm<sup>-2</sup>), calculated from apparent optical depth method. |
| `SIG_LOG10N`         | *(float64)*       | cm⁻² (log10)   | uncertainty on log of **total column density** (in cm<sup>-2</sup>), calculated from apparent optical depth method. |
| `SATURATION`         | *(int64)*         | —              | saturation flag, 1: saturated, 0: unsaturated |
| `fN`                 | *(int64)*         | —              | Column density measurement method, 1: WEIGHTED MEAN, 2: FIRST, 3: SECOND, 4: Corrected λ1550 (partial saturation), 5: Lower limit from λ1550 (strong saturation), 6: Lower limit from λ1548 (strong saturation and 1550 is not available) -1: FAIL. |

---

## **HDU2: METADATA**
This HDU contains **metadata** related to the observed quasars.

| **Keyword**   | **Type**       | **Units**        | **Description** |
|--------------|----------------|------------------|-----------------|
| `LOS_ID`     | *(int64)*       | —                | Line-of-sight (LOS) ID in **picca continuum modeling** (**same as TARGETID**). |
| `RA`         | *(float64)*     | degrees          | **Right Ascension** of quasars (degrees). |
| `DEC`        | *(float64)*     | degrees          | **Declination** of quasars (degrees). |
| `Z_QSO`      | *(float64)*     | —                | Redshift of quasars. |
| `MEANSNR`    | *(float64)*     | —                | **Mean signal-to-noise ratio** of the quasar spectrum from picca. |
| `TARGETID`   | *(int64)*       | —                | **DESI unique identifier** for each object. |
| `SURVEY`     | *(str32)*       | —                | **Survey name** in which the object was observed. |
| `PROGRAM`    | *(str32)*       | —                | **Program name** in which the object was observed. |
| `HPXPIXEL`   | *(int64)*       | —                | **Healpix ID** for the spectrum, do HPXPIXEL//100 to get the healpix directory name. |
| `ZQSO_ERR`   | *(float64)*     | —                | Error on **quasar redshift**. |
| `TSNR2_LRG`  | *(float32)*     | —                 | Template signal-to-noise ratio for each quasar. Can be used to calculate effective exposure time, T<sub>eff</sub> = 12.15 x TSNR2\_LRG. |
| `EFFTIME`    | *(float32)*     | seconds          | Effective exposure time in seconds, T<sub>eff</sub> = 12.15 x TSNR2\_LRG. |

---

### **Notes**
- This catalog is based on **DESI DR1 Quasars** and contains CIV absorbers identified in the spectra.
  
- Rest-frame equivalent widths (EWs) are measured in **Angstroms (Å)**.
  
- **Velocity dispersions (VDISP)** are corrected for instrumental resolution and given in **km/s**.
  
- In version `qsoabsfind/v1.0.3` (used to construct the original catalog), a small bug affected the estimation of velocity dispersion — specifically, the instrumental resolution was underestimated by a factor of 2.355. All **VDISP** values have been recomputed in the current catalog using the correct resolution. As a result, <3.5% of systems now have **VDISP = 0**, indicating unresolved lines. Most of these are visually confirmed to be genuine absorbers and are therefore retained in the catalog and analysis.
  
- This bug has been fixed in `qsoabsfind/v1.0.5`, and any future catalogs built from `version >= v1.0.5` will automatically have correct velocity dispersions for the lines.
  
- Column densities are measured using the Apparent Optical Depth Method (AODM; [Savage & Sembach 1991](https://ui.adsabs.harvard.edu/abs/1991ApJ...379..245S/abstract)).

### **Contact**

- Please write to abhijeetanand2011@gmail.com, if you have questions.
