# Core Hunter 3 R package

### Latest release

[![Coverage Status](http://img.shields.io/coveralls/corehunter/corehunter3-r/master.svg)](https://coveralls.io/r/corehunter/corehunter3-r)
[![Build Status](https://img.shields.io/travis/corehunter/corehunter3-r/master.svg)](https://travis-ci.org/corehunter/corehunter3-r)

### Development snapshot

[![Coverage Status](http://img.shields.io/coveralls/corehunter/corehunter3-r/develop.svg)](https://coveralls.io/r/corehunter/corehunter3-r)
[![Build Status](https://img.shields.io/travis/corehunter/corehunter3-r/develop.svg)](https://travis-ci.org/corehunter/corehunter3-r)

Core Hunter 3 is a flexible tool for multi-purpose core subset selection. Version 3 has been recoded from scratch using the [JAMES framework](http://www.jamesframework.org) which provides the applied optimization algorithms. A lot of new features have been added such as the ability to sample cores based on multiple types of genetic marker data, phenotypic traits or a precomputed distance matrix. New and improved evaluation measures were also included, that can be separately or simultaneously optimized.

Requirements
------------

A [Java Runtime Environment] (http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) (JRE) version 8 or later is required to run Core Hunter.

Getting started
---------------

The package `corehunter` can be installed from CRAN with

```R
> install.packages("corehunter")
```

Afterwards, load the package

```R
> library(corehunter)
```

and your data, e.g.

```R
> my.genotypes <- genotypes(file = "path/to/file")
```

and sample a core collection with

```R
> sampleCore(my.genotypes)
```

There are numerous options when sampling a core. For example, you can change the size of the core (20% by default), optimize a specific measure (average entry-to-nearest-entry distance by default) or maximize a weighted index including multiple measures, change stop conditions of the algorithm, etc. All functions have detailed documentation, for example try

```R
> ?sampleCore
> ?objective
> ?genotypes
> ?phenotypes
> ?distances
> ?coreHunterData
```


Supported data types
--------------------

Core Hunter 3 supports multiple types of genetic marker data, phenotypic traits and precomputed distance matrices. See http://www.corehunter.org for more details.

Evaluation measures
-------------------

Core Hunter 3 can optimize the following measures, either separately or simultaneously as part of a weighted index.

#### Distance based measures

- Average entry-to-nearest-entry distance (diversity)
- Average accession-to-nearest-entry distance (representativeness)
- Average entry-to-entry distance (provided for historical reasons, not preferred)

Gower's distance is used to compute distances from phenotypic traits, and both the Modified Roger's as well as Cavalli-Sforza & Edwards distances are supported for genetic marker data. Alternatively, a precomputed distance matrix can be used.

#### Allelic richness

- Shannon's index
- Expected heterozygosity
- Allele coverage

Available for genetic marker data only.
