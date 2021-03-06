

# HDF5

**Hierarchical Data Format**

???+ abstract "In short"
    Proprietary legacy format for tabular data.

item | info
--- | ---
types | [Database](../dataTypes/database.md)
preferred | ❌ no
extensions | [`.hdf5`](../extensions/hdf5.md)
related formats | [Access](../fileFormats/access.md), [CSV](../fileFormats/csv.md), [dbase](../fileFormats/dbase.md), [SIARD](../fileFormats/siard.md), [SQL](../fileFormats/sql.md), [XML](../fileFormats/xml.md)
wikipedia | [`Hierarchical_Data_Format`]({{wikipedia}}/Hierarchical_Data_Format)

## Description

HDF (version 5, not compatible with earlier versions) is a
common dataset format with the ability to store data in multidimensional arrays,
grouped into collections and/or hierarchies. Relationships between data in the
arrays can be saved, but the format does not allow for storing structured
(descriptive) metadata.

## Recommendation

The format is open and can be read in a variety of
applications, but it is very difficult to process without the use of HDF5
software.

Use one of the tools on
[HDF Group Support (legacy)]({{hdf5tools}})
to convert data to [SQL](../fileFormats/sql.md) or [CSV](../fileFormats/csv.md).


## See also
*   [`{{hdf5}}`]({{hdf5}})



