PHAROS catalog FITS product
==============================================================================
Target: 47 UMa / HD 95128
Version: v1.3
Created UTC: 2026-06-10T16:55:23.220030+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for 47 UMa / HD 95128.
It is intended for exoplanet-atmosphere photochemistry and PHAROS catalog use.

Main wavelength and flux convention
-----------------------------------
Wavelengths are stored in nm and Angstrom.
Surface flux is stored as erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
No 1 AU, TOA, orbital-distance, or Photochem irradiance column is stored in this FITS file.
Photochem/1 AU exports, if needed, should be distributed as separate sidecar files.

FITS extensions
---------------
PRIMARY: target and catalog metadata.
SED: science-ready stitched SED with per-row component flags.
SEGMENTS: wavelength ranges, source class, and scaling notes for each stitch segment.
PROVENANCE: input files and method notes.
DIAGNOSTICS: original final diagnostics text preserved line-by-line.
FISM2_SANZ_UNCERT: optional FISM2/Sanz analytic uncertainty envelope. Do not use NAMEKATA_UNCERT for FISM2-based targets.
README: this text, preserved inside the FITS file.

Stitch segments
---------------
01. FISM2/Lx X-ray: 0.55-12.35 nm, N=119, type=literature_scaled_reconstruction
02. FISM2/Sanz EUV: 12.45-91.15 nm, N=788, type=semiempirical_reconstruction
03. FISM2 transition bridge: 91.25-114.95 nm, N=238, type=semiempirical_transition_bridge
04. HST/COS FUV: 115-143.9194 nm, N=18736, type=direct_observation
05. IUE gap-fill: 144.0587-256.6681 nm, N=573, type=observed_gapfill_bridge
06. HST/STIS NUV: 256.9081-284.5525 nm, N=22574, type=direct_observation
07. IUE/LWR+LWP bridge: 284.6915-329.7958 nm, N=170, type=observed_gapfill_bridge
08. PHOENIX blue bridge: 330-345.95 nm, N=320, type=photosphere_model_bridge
09. Gaia DR3 XP sampled: 346-1020 nm, N=338, type=direct_observation
10. PHOENIX tail: 1020-4999.95 nm, N=79600, type=photosphere_model_scaled

Interpretation notes
--------------------
For 47 UMa, the adopted 0.5-125 nm high-energy product is a FISM2 solar-minimum reconstruction scaled to literature Lx and Sanz-Forcada EUV luminosity.
The XMM/PPS analysis was used for diagnostic/source-quality assessment, but the likely target source is low-count and weakly constrained; the final high-energy normalization is not a direct XMM/APEC spectral measurement.
The 12.4-91.2 nm FISM2/Sanz region is the EUV reconstruction. The 91.2-115 nm region is a transition bridge and should be treated as lower confidence.
HST provides the observed FUV/NUV UV chunks. IUE is used as an observed/scaled gap-fill bridge where needed.
Gaia DR3 XP provides the optical spectrophotometry. PHOENIX provides the short blue bridge to Gaia and the red/IR tail, when present in the final SED.
GALEX broadband/catalog photometry is diagnostic only and is not inserted as a continuous spectrum.

Selected diagnostic checks
--------------------------

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
