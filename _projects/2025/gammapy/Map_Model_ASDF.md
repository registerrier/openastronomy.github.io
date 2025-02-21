---
name: Serialisation of Map and Model classes into ASDF format
# Add a short one line description of your project
desc: This projects aims at adding ASDF format serialization of `Map` and `Model` classes
# Student requirements:
requirements:
 - Experience with python
difficulty: medium to high
# Related issues (if any)  to this project.
# Ideally you want at least one
issues:
 - https://github.com/gammapy/gammapy/issues/5709
mentors:
# First person in contact; mentors may change before project starts.
# GitHub or GitLab handles
 - registerrier
 - Astro-Kirsty
# The programme under this project wish to run.
initiatives:
 - GSOC
project_size:
 - 350 h (Large)
# Different technologies needed
tags:
 - python
 - gammapy
# suborganisation(s) to which this project belongs.
collaborating_projects:
 - gammapy
---

## Description
Gammapy is a community-developed, open-source Python package for gamma-ray astronomy built on Numpy, Scipy and Astropy. It is the core library for the CTAO Science Tools but can also be used to analyse data from existing imaging atmospheric Cherenkov telescopes (IACTs), such as H.E.S.S., MAGIC and VERITAS. It also provides some support for Fermi-LAT and HAWC data analysis.

Gammapy is built on a the `Map` framework [(see documentation)](https://docs.gammapy.org/1.3/user-guide/maps/index.html) which allow to represent pixelized N-dimension data  with at least two spatial dimensions representing coordinates on a sphere (e.g. an image in celestial coordinates). For now, `Map` serialization is performed following the gamma-astro-data-format [specifications](https://gamma-astro-data-formats.readthedocs.io/en/v0.3/skymaps/index.html), `Dataset` objects are serialized as several FITS HDUs in a given file. List of `Dataset` objects (or `Datasets`) are serialized as yaml file with FITS filenames. This is not ideal as this introduces a diversity of formats, and proper metadata serialization within FITS is cumbersome.  

The [asdf format](https://www.asdf-format.org/en/latest/overview.html) would alleviate some of these difficulties and gammapy should provide a way to seriliaze its products in ASDF.

## Project Milestones

### Setup and community Bonding Period

* Familiarize yourself with gammapy data structures and development environment.
* Familiarize yourself with asdf extensions, Converters and schemas.

### First evaluation: Implement ASDF serialization for Maps 

* Write Converters, schemas and associated tests for MapAxis, MapAxes.
* Write Converters, schemas and associated tests for Geom classes.

### Final evaluation

* Write Converters, schemas and associated tests for Map classes.
* Write Converters, schemas and associated tests for MapDataset classes.
* Write Converters, schemas and associated tests for Datasets class.
* Finally, addition of converters for `Model` objects could be explored. 
