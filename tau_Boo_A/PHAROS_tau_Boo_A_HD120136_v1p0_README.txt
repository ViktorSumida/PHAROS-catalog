PHAROS catalog FITS product
==============================================================================
Target: tau Boo A / HD 120136
Formal target label: tau Bootis A / HD 120136
Version: v1.0
Created UTC: 2026-07-03T16:16:09.202644+00:00

Purpose
-------
This FITS file contains the PHAROS panchromatic hybrid SED for tau Boo A / HD 120136.
It is intended for exoplanet-atmosphere photochemistry and catalog use.

Flux convention
---------------
The SED extension stores stellar surface flux only.
No 1 AU, TOA, orbital-distance, or Photochem irradiance column is included in the FITS file.

FITS extensions
---------------
PRIMARY: target and catalog metadata.
SED: science-ready stitched surface-flux SED with per-row component flags.
SEGMENTS: wavelength ranges, source class, and scaling notes for each stitch segment.
PROVENANCE: input files and method notes.
DIAGNOSTICS: final diagnostics text stored line-by-line.
NAMEKATA_UNCERT: analytic Namekata/Sanz uncertainty envelope.
README: this human-readable description.

Stitch segments
---------------
01. Chandra LETG/HRC-S 2T APEC: 0.5203139-12.39471 nm, N=1600, type=model_fit_to_observation
02. Namekata/Sanz EUV: 12.4-114.5 nm, N=3881, type=semiempirical_reconstruction
03. IUE_SWP_MXLO: 115.3095-119.4165 nm, N=9, type=observed_gapfill_bridge
04. HST_STIS_G140M: 119.507-124.8547 nm, N=1001, type=direct_observation
05. IUE_SWP_MXLO: 124.9484-197.1986 nm, N=146, type=observed_gapfill_bridge
06. IUE_LWP_MXLO: 197.2333-197.6327 nm, N=2, type=observed_gapfill_bridge
07. IUE_SWP_MXLO: 197.7015-197.7015 nm, N=1, type=observed_gapfill_bridge
08. IUE_LWP_MXLO: 198.2983-256.7439 nm, N=117, type=observed_gapfill_bridge
09. HST_STIS_E230H: 256.8922-284.5411 nm, N=22584, type=direct_observation
10. IUE_LWP_MXLO: 284.8351-334.7601 nm, N=100, type=observed_gapfill_bridge
11. UV_Gaia_bridge: 334.7754-335.9847 nm, N=80, type=empirical_bridge
12. Gaia DR3 XP: 336-1020 nm, N=343, type=direct_observation
13. PHOENIX: 1020.052-5000 nm, N=50808, type=photosphere_model_scaled

Scientific construction
-----------------------
Chandra/LETG-HRC-S 2T APEC is used for the X-ray segment.
Namekata/Sanz reconstructs the unobserved EUV region.
The 12.4--91.2 nm Namekata/Sanz interval is normalized to the Sanz-Forcada EUV luminosity.
The 91.2 nm to first-UV-point extension uses the same Namekata/Sanz scale factor.
HST/STIS is preferred in the observed UV where available; IUE is used as gap fill.
Gaia XP and PHOENIX provide the optical/IR region.

Uncertainty
-----------
The NAMEKATA_UNCERT extension stores the analytic lognormal Namekata/Sanz uncertainty envelope.
It is full-weight over 12.4--91.2 nm and tapers smoothly to zero by 115 nm.

Catalog note
------------
When using this product, cite the PHAROS catalog paper when available.
Until public release, treat this as an internal/pre-release product.
