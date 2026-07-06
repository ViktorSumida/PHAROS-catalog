PHAROS catalog FITS product
==============================================================================
Target: 18 Sco / HD 146233
Version: v1.4
Created UTC: 2026-06-30T18:11:38.372504+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for 18 Sco / HD 146233.
It is intended for exoplanet-atmosphere photochemistry and catalog release.

Main wavelength and flux convention
-----------------------------------
Wavelengths are stored in nm and Angstrom.
Surface flux is stored as erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
No 1 AU / TOA / Photochem irradiance column is stored in this FITS file.
Photochem/1 AU exports, if needed, should remain separate sidecar files.

Detailed observed-block labeling
--------------------------------
The final compact SED stores the low-energy block as Observed/Gaia/PHOENIX hybrid.
This FITS version uses the updated Gaia650/PHOENIX950 low-energy flux block when available and expands it into detailed labels.
Detailed-label source: coverage CSV: C:\Users\vikto\OneDrive\PhD_Mackenzie\Stellar Spectra\18 Sco\Outputs\Hybrid_Gaia650_PHOENIX950nm_smoothedPHXscale_cleanSegments\18_Sco_hybrid_final_segment_coverage.csv

FITS extensions
---------------
PRIMARY: target and catalog metadata.
SED: science-ready stitched SED with per-row component flags.
SEGMENTS: wavelength ranges, source class, and scaling notes for each stitch segment.
PROVENANCE: input files and method notes.
DIAGNOSTICS: original final diagnostics text preserved line-by-line.
NAMEKATA_UNCERT: optional Namekata/Sanz uncertainty envelope, if available.
README: this text, preserved inside the FITS file.

Stitch segments
---------------
01. XMM/EPIC-pn 1T APEC: 0.5234871-12.23532 nm, N=120, type=model_fit_to_observation
02. Namekata/Sanz: 12.5-114.5 nm, N=3880, type=semiempirical_reconstruction
03. HST/COS: 115.0001-208.9815 nm, N=36756, type=direct_observation
04. Gaia XP: 208.9895-208.9895 nm, N=1, type=direct_observation
05. IUE/LWP+LWR: 209.1387-227.2872 nm, N=69, type=observed_gapfill_bridge
06. HST/STIS E230: 227.505-311.9618 nm, N=33108, type=direct_observation
07. HST/STIS G430: 312.0328-569.4224 nm, N=938, type=direct_observation
08. HST/STIS G750: 569.6971-649.8467 nm, N=166, type=direct_observation
09. Gaia XP: 650-948 nm, N=150, type=direct_observation
10. PHOENIX: 950-5000 nm, N=51703, type=photosphere_model

Interpretation notes
--------------------
XMM/APEC is a model fitted to an observed X-ray spectrum and exported as surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
HST and Gaia are directly observed spectral/spectrophotometric anchors where available.
IUE segments are used as UV bridge/gap-fill components where needed.
For this v1.4 18 Sco rebuild, STIS/G750 is retained only to 650 nm, Gaia XP is used over 650--950 nm, and PHOENIX is used from 950 nm onward.

Selected diagnostic checks
--------------------------
Lx XMM 0.2-2.0 keV = 5.40523749e+26 erg/s
Sanz L_EUV = 6.16908439e+27 erg/s
Namekata final L_EUV after exact scaling = 6.16908439e+27 erg/s
Namekata/Sanz ratio after exact scaling = 1.00000000e+00
Difference factor after exact scaling = 1.00000000e+00
overlap scatter = 0.171030 dex

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
