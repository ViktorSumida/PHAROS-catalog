# PHAROS-catalog

**PHAROS** — *Panchromatic Habitable-world Archive of Radiation from Observed Solar-like stars* — is a catalog of component-resolved panchromatic spectral energy distributions (SEDs) for nearby solar-like FGK stars.

The catalog is designed to provide traceable stellar irradiation inputs for exoplanet atmosphere, photochemistry, atmospheric escape, climate, and habitability studies. Each PHAROS SED combines observational, semiempirical, empirical-template, and model-atmosphere components into a continuous stellar spectrum while preserving the origin of each wavelength interval.

## Overview

The first PHAROS release covers **0.5–5000 nm** and includes nearby F-, G-, and K-type stars spanning young active solar analogs, intermediate-age stars, and solar-age or older solar-like targets.

The current target list is:

* EP Eri
* π¹ UMa
* ξ Boo A
* κ¹ Cet
* τ Boo A
* β Com
* 70 Oph A (fits file exceeding 50 MB. They are available upon request at viktor.sumida@outlook.com)
* 36 Oph B
* 18 Sco
* υ And
* λ Ser (fits file exceeding 50 MB. They are available upon request at viktor.sumida@outlook.com)
* 47 UMa

The SEDs are constructed from combinations of:

* archival **XMM-Newton** and **Chandra** high-energy constraints;
* X-ray coronal plasma models when the data support target-specific spectral modeling;
* semiempirical EUV reconstructions normalized to the adopted X-ray luminosity;
* empirical high-energy templates for weakly constrained targets;
* ultraviolet spectra from **HST** and **IUE**;
* optical spectrophotometry from **Gaia DR3 XP**, NGSL, and CFLIB when available;
* long-wavelength photospheric extensions based on scaled **PHOENIX** model atmospheres.

## Scientific motivation

The stellar SED is a fundamental boundary condition for modeling planetary atmospheres. For terrestrial and sub-Neptune planets, the wavelength-dependent irradiation field controls photolysis, ionization, atmospheric heating, upper-atmosphere escape, and surface UV environments.

PHAROS focuses on solar-like stars because FGK irradiation fields provide a natural context for studying how high-energy stellar evolution affects planetary atmospheres across a range of activity levels and evolutionary stages.

## Component-resolved design

PHAROS does not treat the final SEDs as uniformly observed spectra. Instead, each wavelength interval retains information about its origin. Depending on the target and wavelength range, a component may be classified as:

* observed;
* reconstructed;
* empirical-template based;
* bridge/interpolated;
* photospheric model;
* hybrid or target-specific.

This component-level provenance is essential for atmospheric and photochemical modeling, because the confidence level and physical interpretation of the SED vary strongly with wavelength.

## Data products

PHAROS products are intended to include:

* stitched stellar-surface flux SEDs;
* component/segment tables;
* provenance information;
* diagnostic files;
* wavelength-coverage summaries;
* FITS catalog products;
* analytic EUV uncertainty envelopes when available.

The FITS files are designed to preserve both the science-ready spectrum and the metadata needed to interpret how each SED was assembled.

## Citation

If you use PHAROS products, please cite the PHAROS catalog paper once available:

```text
Sumida et al., in preparation
```

A BibTeX entry and DOI will be added after publication or archival release.

## Contact

For questions about the catalog, please contact: viktor.sumida@outlook.com

**Viktor Sumida**
Center for Radio Astronomy and Astrophysics Mackenzie (CRAAM)
Mackenzie Presbyterian University


## FITS product format

Each PHAROS target is distributed as a catalog-style FITS file containing the final stitched stellar-surface flux SED and the metadata needed to interpret how the spectrum was assembled. The FITS products are designed to be directly usable in stellar irradiation, atmospheric, photochemical, and habitability studies while preserving the provenance of each wavelength interval.

The PHAROS FITS files store the SED in **stellar surface-flux units**. The main science table provides wavelength-dependent flux densities at the stellar surface, together with component identifiers that allow users to distinguish observed, reconstructed, empirical-template, bridge, hybrid, and model-dependent intervals.

### FITS extensions

A typical PHAROS FITS file contains the following extensions.

### `PRIMARY`

The primary header stores target and catalog metadata. This includes the target name, stellar identifiers, adopted distance, adopted stellar radius, wavelength limits, number of SED points, number of stitched segments, catalog version, release information, and checksum information.

This extension does not contain the science spectrum itself.

### `SED`

The `SED` extension contains the final stitched science-ready spectrum in a uniform wavelength and flux-density convention. This is the main table most users will read first.

Typical columns include:

* `WAVELENGTH_NM`: wavelength in nm;
* `WAVELENGTH_A`: wavelength in Angstrom;
* `F_SURF_NM`: stellar surface flux density in erg s$^{-1}$ cm$^{-2}$ nm$^{-1}$;
* `F_SURF_A`: stellar surface flux density in erg s$^{-1}$ cm$^{-2}$ \AA$^{-1}$;
* `SEGMENT_ID`: integer identifier linking each wavelength point to a stitched segment;
* `COMPONENT`: component label for the wavelength interval;
* `SOURCE`: source or model used for that interval;
* `DATA_TYPE`: broad classification of the data origin;
* `INSTRUMENT`: instrument, model, or reconstruction source;
* `IS_OBS`: true for directly observed intervals;
* `IS_MODEL`: true for model-atmosphere or plasma-model intervals;
* `IS_RECON`: true for reconstructed intervals;
* `IS_BRIDGE`: true for bridge or transition intervals;
* `IS_PHX`: true for PHOENIX photospheric-extension intervals;
* `IS_HYBRID`: true for hybrid intervals assembled from multiple constraints.

The `SED` table can therefore be used both as a continuous stellar-surface flux spectrum and as a component-resolved product in which each wavelength point retains its origin.

### `SEGMENTS`

The `SEGMENTS` extension summarizes the major wavelength intervals used to build the final SED. Each row corresponds to one stitched segment and records its wavelength range, source class, component name, instrument or model origin, scaling notes, and priority information.

This table is useful for quickly identifying which portions of the SED are observed, reconstructed, model-dependent, or used as bridge regions.

### `PROVENANCE`

The `PROVENANCE` extension records the main input files, literature constraints, models, and reconstruction choices used to build the SED. This extension is intended to make the construction of each target product traceable.

Users should consult this extension when they need to know which archival observations, high-energy constraints, photospheric models, or reconstruction methods were used for a given target.

### `DIAGNOSTICS`

The `DIAGNOSTICS` extension stores construction and validation notes line by line. These notes may include wavelength coverage checks, segment-boundary checks, scaling factors, luminosity-normalization checks, and target-specific caveats.

This extension is useful for understanding possible discontinuities, weakly constrained intervals, or special reconstruction choices.

### Optional EUV uncertainty extension

When an analytic EUV uncertainty envelope is available, the FITS file includes a method-specific uncertainty extension.

The extension name depends on the EUV reconstruction method:

* `NAMEKATA_UNCERT` for targets using a Namekata/Sanz EUV reconstruction;
* `FISM2_SANZ_UNCERT` for targets using a FISM2/Sanz EUV reconstruction.

These tables provide percentile spectra for the reconstructed EUV region. They are intended for sensitivity tests involving the unobserved EUV flux. The uncertainty envelope applies to the reconstructed EUV normalization and should not be interpreted as a full propagation of all observational and modeling uncertainties.

### Reading a PHAROS FITS file in Python

A PHAROS FITS product can be inspected with `astropy`:

```python
from astropy.io import fits
from astropy.table import Table

filename = "PHAROS_target_name_v1p0.fits"

with fits.open(filename) as hdul:
    hdul.info()

    sed = Table(hdul["SED"].data)
    segments = Table(hdul["SEGMENTS"].data)
    provenance = Table(hdul["PROVENANCE"].data)
    diagnostics = Table(hdul["DIAGNOSTICS"].data)

# Main wavelength and stellar surface-flux arrays
wavelength_nm = sed["WAVELENGTH_NM"]
flux_surface_nm = sed["F_SURF_NM"]

# Example: select directly observed wavelength points
observed = sed[sed["IS_OBS"] == True]

# Example: select reconstructed wavelength points
reconstructed = sed[sed["IS_RECON"] == True]
```

For most applications, the main arrays are `WAVELENGTH_NM` and `F_SURF_NM` from the `SED` extension. Users who need to track the origin of each wavelength point should also use `SEGMENT_ID`, `COMPONENT`, `SOURCE`, `DATA_TYPE`, and the boolean component flags.
