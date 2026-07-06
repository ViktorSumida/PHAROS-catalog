PHAROS catalog FITS product
==============================================================================
Target: upsilon And / HD 9826
Version: v1.2
Created UTC: 2026-05-29T21:30:40.689142+00:00

Purpose
-------
This FITS file contains a panchromatic hybrid SED for upsilon And / HD 9826.
It is intended for exoplanet-atmosphere photochemistry and PHAROS catalog release.

Main wavelength and flux convention
-----------------------------------
Wavelengths are stored in nm and Angstrom.
The main SED table stores stellar surface flux only:
  erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
No 1 AU / orbital irradiance / Photochem flux column is stored in this FITS file.
Photochem/orbital-distance files should be distributed as separate sidecar products.

FITS extensions
---------------
PRIMARY: target and catalog metadata.
SED: science-ready stitched SED with per-row component flags; surface flux only.
SEGMENTS: wavelength ranges, source class, and scaling notes for each stitch segment.
PROVENANCE: input files and method notes.
DIAGNOSTICS: original final diagnostics text preserved line-by-line.
NAMEKATA_UNCERT: optional Namekata/Sanz uncertainty envelope, if available.
README: this text, preserved inside the FITS file.

Component table used
--------------------
Input components table: C:\Users\vikto\OneDrive\PhD_Mackenzie\Stellar Spectra\upsilon And\Outputs\upsilon_And_XMM_Namekata_detailed_components.csv
The detailed components table was used to preserve internal Gaia/PHOENIX/HST/IUE labels.

Stitch segments
---------------
01. XMM/EPIC-pn quiet 1T APEC: 0.5203437-12.39181 nm, N=2400, type=model_fit_to_observation
02. Namekata/Sanz: 12.4-115 nm, N=2400, type=semiempirical_reconstruction
03. HST spectral product: 115.0004-170.9597 nm, N=26896, type=direct_observation
04. IUE bridge: 171.0489-185.2978 nm, N=86, type=observed_gapfill_bridge
05. IUE bridge: 185.475-256.725 nm, N=476, type=observed_gapfill_bridge
06. HST spectral product: 256.8763-284.5386 nm, N=22662, type=direct_observation
07. PHOENIX scaled: 284.55-335.9493 nm, N=655, type=direct_observation
08. Gaia DR3 XP sampled: 336-1010 nm, N=338, type=direct_observation
09. PHOENIX scaled: 1020.015-5000 nm, N=50642, type=direct_observation

Interpretation notes
--------------------
XMM/APEC is a model fitted to an observed quiet X-ray spectrum and exported as unabsorbed surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
For upsilon And, Namekata is normalized to Sanz over 12.4-91.2 nm.
The 91.2-115 nm Namekata tail is retained for continuity but is not used in the Sanz integral.
Gaia XP is forced from the local XP_SAMPLED FITS in the final workflow.
PHOENIX is retained as near-UV/optical gap fill and red optical/IR tail where needed.

Selected diagnostic checks
--------------------------
XMM_Lx_0p2_2p0_unabsorbed_erg_s = 7.5565152962e+27
Sanz_L_EUV_erg_s = 5.9615137035e+28
Namekata_L_EUV_before_erg_s = 6.8303432415e+29
Namekata_L_EUV_after_erg_s = 5.9615137035e+28
Namekata_Sanz_ratio_before = 1.1457397536e+01
Namekata_Sanz_ratio_after = 1.0000000000e+00
Namekata_to_Sanz_scale_factor = 8.7279855386e-02
Gaia_forced_N = 3.3800000000e+02
Observed_compact_Gaia_window_330_1000_N = 4.1400000000e+02
PHOENIX_gap_fill_N = 6.5500000000e+02
PHOENIX_red_tail_N = 5.0642000000e+04

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
Until the catalog paper is public, treat this file as an internal/pre-release product.
