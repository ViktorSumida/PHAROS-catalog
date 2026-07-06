PHAROS catalog FITS product: lambda Ser / HD 141004
==================================================

Object
------
Target: lambda Ser / HD 141004
Identifiers: HD 141004; HIP 77257; HR 5868; GJ 598; TIC 296740796
Spectral type: G0V
Adopted metadata: Teff=5900 K, logg=4.22, [Fe/H]=0.00, R=1.363 R_sun, d=11.920 pc.
These metadata values are stored for catalog bookkeeping and are not used by this FITS-packaging script to rescale the final SED.

Product
-------
This FITS stores the final stitched SED in stellar surface-flux units only:
    F_SURF_NM [erg s^-1 cm^-2 nm^-1]
    F_SURF_A  [erg s^-1 cm^-2 Angstrom^-1]

The FITS SED table deliberately does NOT contain 1 AU, TOA, orbital-distance, or Photochem irradiance columns.
The Photochem/1 AU text file remains a separate sidecar product when present:
    PHAROS_lambda_Ser_HD141004_Photochem_1AU_sidecar.txt

Wavelength coverage
-------------------
WMIN_NM = 0.55000001
WMAX_NM = 4999.98183593
NSED    = 125701
NSEG    = 10

Scientific construction
-----------------------
X-ray anchor: published L_X with FISM2 soft-X/X-ray spectral shape; no PHAROS APEC spectral fit
X-ray shape: FISM2 strict solar-minimum template
X-ray normalization: published L_X
EUV shape: FISM2 strict solar-minimum template
EUV normalization: Sanz-Forcada relation from published L_X
Published L_X = 6.80000000e+27 erg/s
Sanz-Forcada L_EUV(12.4-91.2 nm) = 5.44449577e+28 erg/s
FISM2 template L_EUV(12.4-91.2 nm) before scaling = 5.45406268e+27 erg/s
FISM2/Sanz scale factor = 9.98245911
Scaled/Sanz ratio = 1.000000000000

Final stitched segments
-----------------------
The exact segment list is stored in the SEGMENTS HDU and mirrors the segment manifest produced by the SED assembly script.
Expected high-level structure:
1. FISM2 soft-X/X-ray segment: 0.5-12.4 nm, scaled to the published L_X.
2. FISM2/Sanz EUV core: 12.4-91.2 nm, scaled to Sanz-Forcada L_EUV.
3. FISM2/Sanz transition bridge: 91.2 nm to first HST/COS wavelength.
4. HST/COS observed block 01: preserved blue block before internal gap.
5. IUE normalized HST-gap fill: local HST-edge-normalized fill for the detected HST internal gap.
6. HST/COS observed block 02: primary observed UV block.
7. IUE red gap-fill: redward gap-fill after final HST/COS wavelength.
8. PHOENIX bridge: fills the gap between IUE and CFLIB.
9. CFLIB optical PHOENIX-calibrated: relative optical spectrum scaled to PHOENIX.
10. PHOENIX tail: extends beyond CFLIB to 5000 nm.

Important caveats
-----------------
- lambda Ser does not have a PHAROS X-ray spectral fit in this product. The 0.5-12.4 nm block is a FISM2 spectral-shape template normalized to the published L_X, not an APEC model fit.
- The EUV segment uses FISM2 as spectral shape and Sanz-Forcada as energy normalization.
- The 91.2-115 nm bridge is not part of the 12.4-91.2 nm Sanz luminosity sanity check.
- The CFLIB optical spectrum is PHOENIX-calibrated because no Gaia/NGSL absolute optical anchor was used.
- The FITS is intended as the catalog surface-flux product; orbit-specific irradiance products should be kept as sidecars.

FITS extensions
---------------
PRIMARY          Catalog and target metadata.
SED              Science-ready stitched surface-flux SED; no 1 AU columns.
SEGMENTS         Segment-level provenance and flags.
PROVENANCE       Input files and method notes.
DIAGNOSTICS      Diagnostics text stored line-by-line.
FISM2_SANZ_UNCERT  Optional FISM2/Sanz analytic EUV uncertainty envelope when available.
README           This README text stored inside the FITS.

Created
-------
Created by: create_lambda_ser_pharos_fits.py
Created UTC: 2026-06-10T16:50:46+00:00
