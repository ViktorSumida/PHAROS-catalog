PHAROS catalog FITS product
==============================================================================
Target: pi1 UMa / HD 72905
Version: v1.2
Created UTC: 2026-05-29T21:25:49.843243+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for pi1 UMa / HD 72905.
It is intended for exoplanet-atmosphere photochemistry and catalog release.

Main wavelength and flux convention
-----------------------------------
Wavelengths are in nm and Angstrom. Surface flux is stored as
erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
The catalog FITS intentionally stores only stellar surface fluxes.
Photochem/orbital irradiance exports, when needed, should be distributed
as separate sidecar text files and are not stored in the SED extension.

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
01. XMM/EPIC-pn 2T APEC: 0.517774-12.37029 nm, N=700, type=model_fit_to_observation
02. Namekata/Sanz: 12.4-114.5 nm, N=3881, type=semiempirical_reconstruction
03. HST spectral product: 115.0004-170.9782 nm, N=45858, type=direct_observation
04. IUE/SWP bridge: 171.0493-197.8715 nm, N=161, type=observed_gapfill_bridge
05. IUE/LWR+LWP bridge: 197.8996-256.7474 nm, N=222, type=observed_gapfill_bridge
06. HST spectral product #2: 256.8803-284.4999 nm, N=22627, type=direct_observation
07. IUE/LWR+LWP bridge #2: 284.7068-334.7675 nm, N=189, type=observed_gapfill_bridge
08. Gaia DR3 XP sampled: 336-1020 nm, N=343, type=direct_observation
09. PHOENIX scaled: 1020.05-5000 nm, N=59276, type=photosphere_model_scaled

Interpretation notes
--------------------
XMM/APEC is a model fitted to an observed X-ray spectrum, exported as unabsorbed surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
HST and Gaia are the preferred directly observed UV/optical segments where available.
IUE is used only as a gap-fill bridge between higher-priority observed segments.
PHOENIX is a photospheric model extension scaled to Gaia XP in the red optical.
GALEX broadband/catalog photometry is not inserted; no GALEX spectral-like file was found for this final product.

Selected diagnostic checks
--------------------------
L_XMM_integral_0.5166_12.4nm_erg_s = 1.162113015618328e+29
L_Namekata_integral_12p4_91p2nm_erg_s = 5.463938430168554e+29
L_Namekata_integral_12p4_115nm_erg_s = 6.289918725878996e+29
Namekata_Sanz_final_ratio = 1.000000000000000e+00
PHOENIX_scale = 9.706761742631755e-01
GALEX spectral-like files = 0

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
