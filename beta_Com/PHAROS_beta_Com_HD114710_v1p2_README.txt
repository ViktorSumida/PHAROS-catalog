PHAROS catalog FITS product
==============================================================================
Target: beta Com / HD 114710
Version: v1.2
Created UTC: 2026-05-29T01:33:51.991750+00:00

Main wavelength and flux convention
-----------------------------------
Wavelengths are in nm and Angstrom. Surface flux is stored as
erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
No 1 AU, TOA, orbital, or Photochem irradiance column is stored in this FITS.

Stitch segments
---------------
01. XMM/EPIC-pn 2T APEC: 0.526965-115.04 nm, N=3962, type=model_fit_to_observation
02. HST/STIS E140M: 115.058-173.395 nm, N=349, type=direct_observation
03. IUE/SWP bridge: 173.562-197.999 nm, N=168, type=observed_gapfill_bridge
04. IUE/LWP+LWR bridge: 198.006-219.994 nm, N=3625, type=observed_gapfill_bridge
05. HST/STIS E230: 220-319.999 nm, N=34577, type=direct_observation
06. IUE/LWP+LWR bridge #2: 320.005-329.998 nm, N=1648, type=observed_gapfill_bridge
07. Gaia DR3 XP sampled: 330.004-1049.92 nm, N=1503, type=direct_observation
08. PHOENIX: 1050-5000 nm, N=50212, type=photosphere_model_scaled

Interpretation notes
--------------------
XMM/APEC is a model fitted to an observed X-ray spectrum, exported as surface flux.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
The previous compact observed block is split here into detailed low-energy intervals:
HST/STIS E140M, IUE/SWP bridge, IUE/LWP+LWR bridge, HST/STIS E230, Gaia XP, and PHOENIX.
The split follows the beta Com low-energy workflow priority: HST > Gaia > IUE gap-fill > PHOENIX.

Selected diagnostic checks
--------------------------
Wavelength coverage = 0.52696457-5000 nm
Lx_XMM_0p2_2p0_keV_erg_s = 1.173770000000000e+28
Sanz_LEUV_erg_s = 8.706455500000000e+28
Namekata_Sanz_ratio_after_scaling = 1.000000000000000e+00
Namekata_uncertainty_extension_available = True
Namekata_uncertainty_method = analytic log-normal prediction scatter; no Monte Carlo

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
