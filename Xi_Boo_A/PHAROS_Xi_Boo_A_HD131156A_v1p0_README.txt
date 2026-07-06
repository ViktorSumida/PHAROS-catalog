PHAROS catalog FITS product
==============================================================================
Target: Xi Boo A / HD 131156 A
Version: v1.0
Created UTC: 2026-06-03T21:12:26.497955+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for Xi Boo A.
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
01. Chandra/LETG-HRC-S 2T APEC: 0.5201522-12.3996 nm, N=10501, type=model_fit_to_observation
02. Namekata/Sanz: 12.4-91.19 nm, N=3103, type=semiempirical_reconstruction
03. Namekata/Sanz 91.2-115 extension: 91.21-114.5 nm, N=778, type=semiempirical_reconstruction_transition
04. HST/STIS E140M: 115.0534-172.9363 nm, N=580, type=direct_observation
05. IUE/SWP LOW: 173.0593-197.8691 nm, N=112, type=observed_gapfill_bridge
06. IUE/LWP LOW: 185.1289-334.7601 nm, N=226, type=observed_gapfill_bridge
07. IUE/LWR LOW: 185.4642-334.9464 nm, N=274, type=observed_gapfill_bridge
08. HST/STIS E230M: 227.4831-311.9206 nm, N=453, type=direct_observation
09. HST/STIS E230M inferred: 228.2481-306.9496 nm, N=393, type=direct_observation
10. PHOENIX bridge: 334.9964-346.4464 nm, N=230, type=direct_observation
11. CFLIB optical PHOENIX-calibrated: 346.5-946.9 nm, N=15011, type=empirical_optical_observation_scaled
12. PHOENIX tail: 946.95-5000 nm, N=81062, type=direct_observation

Interpretation notes
--------------------
Chandra/LETG-HRC-S + APEC is a model fitted to an observed X-ray spectrum, exported as unabsorbed surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
HST and IUE provide the observed UV/NUV connection after the Namekata/Sanz segment.
PHOENIX is used as a short bridge to CFLIB and as the red/IR photospheric tail to 5000 nm.
CFLIB/Indo-US is an empirical optical spectrum scaled to the empirically scaled PHOENIX continuum.
No 1 AU, orbital-distance, TOA, or Photochem irradiance column is included in the FITS SED HDU.
Because Xi Boo is a binary, use the A-component extraction/calibration assumptions documented in the SED workflow.

Selected diagnostic checks
--------------------------
phoenix_scale_factor = 0.9740613680820742
phoenix_reference_window_nm = 320.0-335.0
cflib_scale_factor = 64454950.79958762
cflib_phoenix_overlap_window_nm = 500.0-850.0

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
