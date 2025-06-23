## Parent Catalog of DESI DR1 Quasars for CIV Doublet Search

This file contains the details of **DESI DR1 Quasars** that were searched for **CIV absorbers**.

- **QSO Catalog Filename**: `dr1-QSO_healpix_cat_for_CIV_search.fits`
    This is the DESI DR1 QSO catalog file. It contains 94,986 unique Quasars that were searched for CIV absorbers absorber. The full datamodel for the catalog is below:

- **Citation**: If you use this catalog in your work, please cite [Anand et al. 2025](https://arxiv.org/abs/2504.20299). The paper describes the methodology, completeness, and limitations.

- Please see the **data model and column descriptions** below for details on the catalog format. There are also some **important usage notes** at the end that users should review before using the catalog.

## Data Model

## HDU1: METADATA
This HDU contains information on parent quasars.

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


### **Contact**

- Please write to abhijeetanand2011@gmail.com, if you have questions.
