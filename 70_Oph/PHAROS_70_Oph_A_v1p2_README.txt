PHAROS catalog FITS product
==============================================================================
Target: 70 Oph A / HD 165341 A
Version: v1.2
Created UTC: 2026-06-19T21:28:38.030790+00:00

Main wavelength and flux convention
-----------------------------------
Wavelengths are stored in nm and Angstrom.
Surface flux is stored in erg s^-1 cm^-2 nm^-1 and erg s^-1 cm^-2 Angstrom^-1.
No 1 AU, TOA, orbital-distance, or Photochem irradiance column is stored in this FITS.
Any Photochem/1 AU export remains a separate sidecar product from the SED workflow.

Important anchor note
---------------------
This 70 Oph product uses Chandra/LETG as the X-ray anchor, not XMM-Newton.
For visual and catalog-segment consistency, the Chandra/LETG 2T APEC segment is carried to the common X-ray/EUV boundary at 12.4 nm.
The Sanz luminosity normalization is still based on L_X(5-100 A), while the 10-12.4 nm Chandra contribution is accounted for separately in the residual Namekata/Sanz EUV normalization.

Stitch segments
---------------
01. Chandra/LETG 2T APEC: 0.500066-12.3999 nm, N=90000, type=model_fit_to_observation
02. Namekata UV+Sanz EUV: 12.4-91.19 nm, N=3103, type=semiempirical_reconstruction
03. Namekata UV+Sanz-to-HST transition: 91.21-114.5 nm, N=778, type=semiempirical_transition
04. HST/COS G130M: 115-145.5 nm, N=30471, type=direct_observation
05. HST/COS G160M: 145.5-171.03 nm, N=20915, type=direct_observation
06. HST/STIS E140M: 171.031-171.999 nm, N=519, type=direct_observation
07. HST/STIS E230M: 172.001-251.013 nm, N=42306, type=direct_observation
08. HST/STIS E230M #2: 253.485-299.974 nm, N=24892, type=direct_observation
09. PHOENIX bridge to CFLIB: 300.06-346.474 nm, N=591, type=photosphere_model_scaled_bridge
10. CFLIB HD 165341: 346.5-799.98 nm, N=11338, type=empirical_optical_observation_scaled
11. PHOENIX tail: 799.995-5000 nm, N=53390, type=photosphere_model_scaled

Interpretation notes
--------------------
Chandra/LETG 2T APEC is a phenomenological coronal model fitted to the observed Chandra spectrum.
Namekata/Sanz is a semiempirical EUV reconstruction, not a direct EUV observation.
For this target the Chandra/APEC model extends to 12.4 nm. The Namekata segment is normalized to the residual Sanz EUV luminosity over 12.4-91.2 nm and transitions to the HST UV scale over 91.2-115 nm.
The observed UV/NUV block is HST/COS and HST/STIS. CFLIB is used as an empirical optical segment from 346.5-800 nm in this test product. PHOENIX provides the short bridge and red photospheric extension. Gaia is not used in this no-Gaia product.

Selected diagnostic checks
--------------------------
Wavelength coverage = 0.50006611-5000 nm
Lx_Chandra_5_100A_erg_s = 1.156133825548435e+28
L_Chandra_0p5_12p4nm_erg_s = 1.198068894868148e+28
L_Chandra_10_12p4nm_erg_s = 4.190196089807777e+26
L_Namekata_12p4_91p2nm_erg_s = 8.551934602470324e+28
L_Combined_10_91p2nm_erg_s = 8.593836563368401e+28
Namekata_Sanz_final_ratio = 1.000000000000000e+00
Namekata_uncertainty_extension_available = True
Namekata_uncertainty_method = analytic log-normal prediction scatter; no Monte Carlo

Citation / catalog note
-----------------------
When using this product, cite the PHAROS catalog paper when available
and cite the underlying data/model sources listed in the PROVENANCE extension.
