PHAROS catalog FITS product
==============================================================================
Target: HD 17925 / EP Eri / GJ 117
Version: v1.0
Created UTC: 2026-06-01T20:24:11.827351+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for HD 17925 / EP Eri / GJ 117.
It is intended for exoplanet-atmosphere photochemistry and PHAROS catalog use.

Main wavelength and flux convention
-----------------------------------
Wavelengths are stored in nm and Angstrom.
Surface flux is stored as erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
The catalog FITS intentionally stores only stellar surface fluxes.
Photochem / 1 AU irradiance files remain separate sidecar products and are not stored in the SED HDU.

FITS extensions
---------------
PRIMARY: target and catalog metadata.
SED: science-ready stitched SED with per-row component flags.
SEGMENTS: wavelength ranges, source class, and scaling notes for each stitch segment.
PROVENANCE: input files and method notes.
DIAGNOSTICS: original final diagnostics text preserved line-by-line.
NAMEKATA_UNCERT: optional analytic Namekata/Sanz uncertainty envelope, if available.
README: this text, preserved inside the FITS file.

Stitch segments
---------------
01. XMM/MOS1 2T APEC: 0.5201522-12.3996 nm, N=10501, type=model_fit_to_observation
02. Namekata/Sanz: 12.4-114.5 nm, N=3881, type=semiempirical_reconstruction
03. IUE/SWP low-disp: 115.0583-167.5292 nm, N=263, type=observed_gapfill_bridge
04. HST/STIS NGSL: 167.6216-1019.651 nm, N=2875, type=direct_observation
05. PHOENIX scaled: 1019.685-5000 nm, N=76729, type=direct_observation

Interpretation notes
--------------------
XMM/APEC is a model fitted to an observed X-ray spectrum, exported as unabsorbed surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
IUE/SWP is used as a UV bridge between the Namekata segment and STIS/NGSL.
STIS/NGSL is the main directly observed UV/optical block.
PHOENIX is a photospheric model extension scaled to the red end of STIS/NGSL.
GALEX broadband/catalog products are not inserted as a continuous spectrum.
EP Eri may be unresolved/close binary in X-rays; the XMM anchor should be documented as a system-level coronal measurement unless later separation is possible.

Selected diagnostic checks
--------------------------

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
