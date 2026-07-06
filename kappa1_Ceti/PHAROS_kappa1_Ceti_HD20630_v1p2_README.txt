PHAROS catalog FITS product
==============================================================================
Target: kappa1 Ceti / HD 20630
Version: v1.2
Created UTC: 2026-05-29T01:38:22.574209+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for kappa1 Ceti / HD 20630.
It is intended for exoplanet-atmosphere photochemistry and PHAROS catalog release.

Main wavelength and flux convention
-----------------------------------
Wavelengths are stored in nm and Angstrom.
The main SED table stores stellar surface flux only:
  erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
No 1 AU / orbital irradiance / Photochem flux column is stored in this FITS file.
Photochem/orbital-distance files should remain as separate sidecar products.

FITS extensions
---------------
PRIMARY: target and catalog metadata.
SED: science-ready stitched SED with per-row component flags; surface flux only.
SEGMENTS: wavelength ranges, source class, and scaling notes for each stitch segment.
PROVENANCE: input files and method notes.
DIAGNOSTICS: final diagnostics text preserved line-by-line, if available.
NAMEKATA_UNCERT: optional analytic Namekata/Sanz uncertainty envelope, if available.
README: this text, preserved inside the FITS file.

Component table used
--------------------
Input components table: C:\Users\vikto\OneDrive\PhD_Mackenzie\Stellar Spectra\kappa1 Ceti\Outputs\kappa1_Ceti_XMM_Namekata_components.csv
The low-energy block is stored compactly in the final components table as an observed/hybrid source.
Because the compact source label contains the word Gaia but the instrument-colored workflow shows HST/COS, IUE/SWP, HST/STIS E230, STIS NGSL, and PHOENIX, this FITS packager splits the compact block by wavelength and does not create a Gaia segment unless Gaia is explicitly labeled in the input table.

Stitch segments
---------------
01. XMM/EPIC-pn 2T APEC: 0.5200601-12.39448 nm, N=4990, type=model_fit_to_observation
02. Namekata/Sanz EUV: 12.5-91.19 nm, N=3102, type=semiempirical_reconstruction
03. Namekata/Sanz-to-UV transition: 91.21-114.5 nm, N=778, type=semiempirical_reconstruction
04. HST/COS: 115.01-169.8746 nm, N=15356, type=direct_observation
05. IUE/SWP: 170.0422-197.3667 nm, N=164, type=observed_gapfill_bridge
06. HST/STIS E230: 197.5-251.0631 nm, N=20037, type=direct_observation
07. HST/STIS E230 #2: 253.5172-319.7411 nm, N=17489, type=direct_observation
08. HST/STIS NGSL: 320.0154-999.9983 nm, N=1792, type=direct_observation
09. PHOENIX: 1000.077-5000 nm, N=51063, type=photosphere_model_scaled

Interpretation notes
--------------------
XMM/APEC is a model fitted to an observed X-ray spectrum and exported as unabsorbed surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
The full Sanz-normalized EUV region is 12.4-91.2 nm; the 91.2-115 nm part is the transition to the observed UV block.
The low-energy kappa1 Ceti workflow used HST/COS, IUE/SWP, HST/STIS E230, STIS NGSL, and PHOENIX for the displayed instrument-colored product.
IUE/LWP+LWR was intentionally not used in the low-energy workflow by default because it was noisy for this target.
Gaia XP is not assigned by fallback wavelength rules here; a Gaia segment appears only if it is explicitly present as a detailed input label.

Selected diagnostic checks
--------------------------
Wavelength coverage = 0.52006008-5000 nm
Packaged_L_X_0p52_12p4nm_erg_s = 5.933403308838605e+28
Packaged_L_EUV_12p4_91p2nm_erg_s = 3.158932284994692e+29
Workflow_Sanz_LEUV_erg_s = 3.161499962319000e+29
Workflow_Namekata_Sanz_ratio = 1.000000000000000e+00
Namekata_uncertainty_extension_available = True

Namekata/Sanz uncertainty
-------------------------
The uncertainty envelope, when available, is analytic and uses no Monte Carlo.
It is a log-normal prediction scatter in the integrated EUV normalization, with the Namekata shape fixed.
The full uncertainty is applied over 12.4-91.2 nm and smoothly tapered to zero from 91.2 to 115 nm.

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
