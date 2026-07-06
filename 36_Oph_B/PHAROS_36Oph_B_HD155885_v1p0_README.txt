PHAROS catalog FITS product
==============================================================================
Target: 36 Oph B / HD 155885 / GJ 663 B
Version: v1.0
Created UTC: 2026-06-02T03:25:18.208446+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for 36 Oph B.
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
01. Chandra/LETG 3T APEC B: 0.517789-12.39723 nm, N=5000, type=model_fit_to_observation
02. Namekata/Sanz B: 12.4-114.5 nm, N=3881, type=semiempirical_reconstruction
03. IUE/SWP B HST-A calibrated: 115.058-197.7866 nm, N=329, type=observed_proxy_calibrated_uv_bridge
04. IUE/LWR B HST-A calibrated: 198.2194-332.9985 nm, N=130, type=observed_proxy_calibrated_uv_bridge
05. Gaia DR3 XP B: 336-1020 nm, N=343, type=direct_observation_lowres_spectrophotometry
06. PHOENIX red extension: 1020.021-5000 nm, N=100547, type=direct_observation_lowres_spectrophotometry

Interpretation notes
--------------------
Chandra/LETG + APEC is a model fitted to an observed X-ray spectrum, exported as unabsorbed surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
IUE/SWP and IUE/LWR are 36 Oph B UV/NUV segments calibrated using HST/STIS A as a proxy template.
Gaia DR3 XP is the main low-resolution observed optical/red-optical block.
PHOENIX is a photospheric model extension used only after the Gaia red end.
No 1 AU, orbital-distance, TOA, or Photochem irradiance column is included in the FITS SED HDU.
Because 36 Oph is a multiple system, document the component extraction/calibration assumptions when using this product publicly.

Selected diagnostic checks
--------------------------
drop_last_n_points = 2

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
