<img src="docs/images/formats.png" width="100" align="right"/>
<img src="docs/images/DANS.png" width="200" align="right"/>

# About

[DANS](https://www.dans.knaw.nl)
is developing normative guidelines about data and file types for the purpose
of long-term archiving in its self-service repository
[EASY](https://easy.dans.knaw.nl).

# Disclaimer

All texts you find here are work in progress.
The currently authoritative texts can be found on the
[preffered formats](https://dans.knaw.nl/en/deposit/information-about-depositing-data/before-depositing/file-formats?set_language=en)
web page of DANS.

# Purpose

The purpose of this repository is to open up the discussion of which formats are preferred and which are not.

There are two important kinds of criteria for a format to be preferred:

*   is it technically suitable for long-term preservation?
    I.e. will it still be usable and/or understandable if most software that we have now is out of business? 
*   is it practically usable by depositors and other users of the archive?
    We do not want to introduce unnecessary hurdles for researchers that submit their data to us.

Archiving for research is always unfinished business. 
Formats evolve, and new formats emerge. 
Here at DANS we do not pretend to know all formats and we are open to learn about new ones.

# Getting started

If you have comments on our current preferred format specifications, or if you want to introduce
new formats, you can start by filing an issue.

Please, browse through the
[list of issues](https://github.com/Dans-labs/formats/issues)
first in order to see if your topic is already being dealt with.

# Overview

The folder
[dataTypes](docs/dataTypes) contains a collection of data types, such as *text*, *spreadsheet*, *database*, etc.

A data type is a way of organizing raw data for specific modelling applications: image, sound,
text, structured data, etc. 

The folder 
[fileTypes](docs/fileFormats) contains a collection of file formats, such as *pdf*, *xlsx*, *siard*, etc.

A file format is a way to serialize the data of a specific data type to a file.
Applications that deal with that data are programmed in such a way that they can read
one or more file formats for that type.

There are usually several file formats associated with one data type.

# Contact

[Dirk Roorda](mailto:dirk.roorda@dans.knaw.nl)
