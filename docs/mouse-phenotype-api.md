# Mouse Phenotype API Reference

## Gene Services

### Gene Summary Service

Request pattern: /genes/<**mgiGeneAccessionId**>/summary

Request example: GET /genes/MGI:1929293/summary

Response datatype: JSON Object.

#### Example

```json
{
  "mgiGeneAccessionId": "MGI:1929293",
  "geneName": "calcium and integrin binding family member 2",
  "geneSymbol": "Cib2",
  "markerType": "Gene",
  "synonyms": ["calcium binding protein Kip2", "2810434I23Rik"],
  "humanGeneSymbols": ["CIB2"],
  "humanSymbolSynonyms": ["USH1J", "KIP2", "DFNB48"],
  "productionCentres": ["MRC Harwell"],
  "phenotypingCentres": ["MRC Harwell"],
  "alleleNames": [
    "targeted mutation 1a, Wellcome Trust Sanger Institute",
    "targeted mutation 1c, Wellcome Trust Sanger Institute",
    "targeted mutation 1, Aziz El-Amraoui",
    "targeted mutation 1.1, Aziz El-Amraoui",
    "targeted mutation 1.1, Zubair M Ahmed",
    "targeted mutation 1b, Wellcome Trust Sanger Institute"
  ],
  "isUmassGene": false,
  "isIdgGene": false,
  "hasEmbryoImagingData": false,
  "chrName": "9",
  "seqRegionStart": "54452078",
  "seqRegionEnd": "54467502",
  "chrStrand": "-",
  "seqRegionId": "9",
  "entrezgeneId": "56506",
  "ensemblGeneIds": ["ENSMUSG00000037493"],
  "ccdsIds": ["CCDS40642.1"],
  "ncbiId": "56506",
  "assignmentStatus": "Selected for production",
  "nullAlleleProductionStatus": "Genotype confirmed mice",
  "conditionalAlleleProductionStatus": "Genotype confirmed mice",
  "esCellProductionStatus": "ES Cells Produced",
  "phenotypeStatus": "Phenotyping data available",
  "phenotypingDataAvailable": true,
  "significantTopLevelPhenotypes": [
    "homeostasis/metabolism phenotype",
    "immune system phenotype",
    "nervous system phenotype",
    "hearing/vestibular/ear phenotype",
    "hematopoietic system phenotype",
    "behavior/neurological phenotype"
  ],
  "notSignificantTopLevelPhenotypes": [
    "reproductive system phenotype",
    "integument phenotype",
    "adipose tissue phenotype",
    "growth/size/body region phenotype",
    "muscle phenotype",
    "cardiovascular system phenotype",
    "craniofacial phenotype",
    "renal/urinary system phenotype",
    "pigmentation phenotype",
    "limbs/digits/tail phenotype",
    "vision/eye phenotype",
    "skeleton phenotype",
    "mortality/aging"
  ],
  "significantPhenotypesCount": 25,
  "adultExpressionObservationsCount": 46,
  "embryoExpressionObservationsCount": 42,
  "associatedDiseasesCount": 4,
  "hasLacZData": true,
  "hasImagingData": true,
  "hasViabilityData": true,
  "hasBodyWeightData": true
}
```

#### Changes

- geneAccessionId -> mgiGeneAccessionId
- humanGeneSymbol -> humanGeneSymbols
- humanSymbolSynonym -> humanSymbolSynonyms
- productionCentre -> productionCentres
- phenotypingCentre -> phenotypingCentres
- alleleName -> alleleNames
- ensemblGeneId -> ensemblGeneIds
- ccdsIds **DELETED**
- ccdsId -> ccdsIds

### Gene Significant Phenotypes Service

Request pattern: /genes/<**mgiGeneAccessionId**>/phenotype-hits

Request example: GET /genes/MGI:1929293/phenotype-hits

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "mgiGeneAccessionId": "MGI:1929293",
    "pipelineStableId": "HRWL_001",
    "procedureStableId": "IMPC_ACS_003",
    "procedureName": "Acoustic Startle and Pre-pulse Inhibition (PPI)",
    "parameterStableId": "IMPC_ACS_006_001",
    "parameterName": "Response amplitude - S",
    "alleleAccessionId": "MGI:5548707",
    "alleleName": "targeted mutation 1b, Wellcome Trust Sanger Institute",
    "alleleSymbol": "Cib2<tm1b(EUCOMM)Wtsi>",
    "zygosity": "homozygote",
    "phenotypingCentre": "MRC Harwell",
    "sex": "male",
    "projectName": "BaSH",
    "pValue": 4.42718461537162e-6,
    "lifeStageName": "Early adult",
    "effectSize": -1.45771957428109,
    "phenotype": {
      "id": "MP:0001489",
      "name": "decreased startle reflex"
    },
    "topLevelPhenotypes": [
      {
        "id": "MP:0005386",
        "name": "behavior/neurological phenotype"
      }
    ]
  }
]
```

#### Changes

- geneAccessionId -> mgiGeneAccessionId
- pValue datatype: string -> double
- lifeStageName datatype: array -> string
- effectSize datatype: string -> double
- topLevelPhenotype -> topLevelPhenotypes
- phenotypingCenter -> phenotypingCentre

### Gene Statistical Results Service

Request pattern: /genes/<**mgiGeneAccessionId**>/statistical-results

Request example: GET /genes/MGI:1929293/statistical-results

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "geneAccessionId": "MGI:1929293",
    "pipelineStableId": "HRWL_001",
    "procedureStableId": "IMPC_ACS_003",
    "procedureName": "Acoustic Startle and Pre-pulse Inhibition (PPI)",
    "parameterStableId": "IMPC_ACS_037_001",
    "parameterName": "% Pre-pulse inhibition - Global",
    "alleleAccessionId": "MGI:5548707",
    "alleleName": "targeted mutation 1b, Wellcome Trust Sanger Institute",
    "alleleSymbol": "Cib2<tm1b(EUCOMM)Wtsi>",
    "metadataGroup": "c91fba05bfb620a9c668ffb6477bda16",
    "zygosity": "homozygote",
    "phenotypingCentre": "MRC Harwell",
    "phenotypeSexes": ["male", "female"],
    "projectName": "BaSH",
    "maleMutantCount": 13,
    "femaleMutantCount": 8,
    "lifeStageName": "Early adult",
    "pValue": 5.09981628423167e-18,
    "effectSize": -1.87454844122216,
    "significant": true,
    "phenotype": {
      "id": "MP:0009142",
      "name": "decreased prepulse inhibition"
    },
    "topLevelPhenotypes": [
      {
        "id": "MP:0003631",
        "name": "nervous system phenotype"
      }
    ]
  }
]
```

#### Changes

- geneAccessionId -> mgiGeneAccessionId
- phenotypingCenter -> phenotypingCentre
- phenotypeSex -> phenotypeSexes
- maleMutantCount datatype: string -> int
- femaleMutantCount datatype: string -> int
- lifeStageName datatype: array -> string
- topLevelPhenotype -> topLevelPhenotypes
- phenotype datatype: Object -> Object | null

### Gene Expression Data Service

Request pattern: /genes/<**mgiGeneAccessionId**>/expression

Request example: GET /genes/MGI:1929293/expression

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "mgiGeneAccessionId": "MGI:1929293",
    "zygosity": "heterozygote",
    "parameterName": "Spinal cord",
    "parameterStableId": "IMPC_ALZ_020_001",
    "mutantCounts": {
      "expression": 2,
      "tissueNotAvailable": 1,
      "noExpression": 0,
      "imageOnly": 0,
      "ambiguous": 0
    },
    "controlCounts": {
      "expression": 0,
      "tissueNotAvailable": 0,
      "noExpression": 409,
      "imageOnly": 0,
      "ambiguous": 0
    },
    "expressionImageParameters": [
      {
        "parameter_stable_id": "IMPC_ALZ_076_001",
        "parameter_name": "LacZ Images Wholemount"
      }
    ],
    "lacZLifestage": "adult"
  }
]
```

#### Changes

- geneAccessionId -> mgiGeneAccessionId
- expressionImageParameters datatype: array | no show -> array | null

### Gene Images Service

Request pattern: /genes/<**mgiGeneAccessionId**>/images

Request example: GET /genes/MGI:1929293/images

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "mgiGeneAccessionId": "MGI:1929293",
    "strainAccessionId": "MGI:2164831",
    "procedureStableId": "IMPC_XRY_001",
    "procedureName": "X-ray",
    "parameterStableId": "IMPC_XRY_034_001",
    "parameterName": "XRay Images Whole Body Dorso Ventral",
    "count": 32,
    "thumbnailUrl": "//www.ebi.ac.uk/mi/media/omero/webgateway/render_birds_eye_view/63809",
    "fileType": "application/dicom"
  }
]
```

#### Changes

- mgiGeneAccessionId **ADDED**

### Gene Diseases Service

Request pattern: /genes/<**mgiGeneAccessionId**>/diseases

Request example: GET /genes/MGI:1929293/diseases

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "mgiGeneAccessionId": "MGI:1929293",
    "diseaseId": "ORPHA:77296",
    "phenodigmScore": 55.995,
    "associationCurated": false,
    "diseaseMatchedPhenotypes": "HP:0003124 Hypercholesterolemia,HP:0002345 Action tremor,HP:0002149 Hyperuricemia",
    "type": "disease_model_summary",
    "modelSource": "IMPC",
    "markerSymbol": "Cib2",
    "modelDescription": "Cib2<tm1b(EUCOMM)Wtsi> hom early",
    "diseaseModelAvgNorm": 24.92,
    "diseaseModelAvgRaw": 0.53,
    "markerLocus": "9:54452078-54467502",
    "modelMatchedPhenotypes": "MP:0001489 decreased startle reflex,MP:0001513 limb grasping,MP:0000745 tremors,MP:0001552 increased circulating triglyceride level,MP:0005178 increased circulating cholesterol level,MP:0001556 increased circulating HDL cholesterol level,MP:0001486 abnormal startle reflex",
    "modelId": "MGI:5548707#hom#early",
    "diseaseModelMaxRaw": 2.53,
    "diseaseModelMaxNorm": 87.07,
    "markerNumModels": 3,
    "diseaseTerm": "Morgagni-Stewart-Morel Syndrome",
    "modelGeneticBackground": "C57BL/6NTac"
  }
]
```

#### Changes

- mgiGeneAccessionId **ADDED**
- diseaseModelAvgNorm datatype: string -> double
- diseaseModelAvgRaw datatype: string -> double
- diseaseModelMaxRaw datatype: string -> double
- diseaseModelMaxNorm datatype: string -> double
- markerNumModels datatype: string -> int
- associationCurated datatype: string -> boolean

### Gene Publications Service

Request pattern: /genes/<**mgiGeneAccessionId**>/publications

Request example: GET /genes/MGI:1929293/publications

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "mgiGeneAccessionId": "MGI:1929293",
    "alleleSymbol": "Cib2<tm1a(EUCOMM)Wtsi>",
    "doi": "10.1016/j.biocel.2013.11.001",
    "monthOfPublication": 1,
    "yearOfPublication": 2014,
    "journalTitle": "The international journal of biochemistry & cell biology",
    "title": "Usher protein functions in hair cells and photoreceptors.",
    "pmcid": "PMC3971483"
  }
]
```

#### Changes

- mgiGeneAccessionId **ADDED**

### Gene Order Service

Request pattern: /genes/<**mgiGeneAccessionId**>/order

Request example: GET /genes/MGI:1929293/order

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "mgiGeneAccessionId": "MGI:1929293",
    "alleleSymbol": "Cib2<tm1a(EUCOMM)Wtsi>",
    "alleleDescription": "KO first allele (reporter-tagged insertion with conditional potential)",
    "productTypes": ["targeting_vector", "es_cell", "mouse"],
    "alleleMapUrl": "https://www.i-dcc.org/imits/targ_rep/alleles/11268/allele-image?simple=true.jpg"
  }
]
```

#### Changes

- mgiGeneAccessionId **ADDED**
- alleleMapUrl **ADDED**

### Gene Search Service

Request pattern: /search/genes

Request example: GET /search/genes

Response datatype: JSON Array

```json
[
  {
    "mgiGeneAccessionId": "MGI:1333864",
    "geneName": "mitochondrial ribosomal protein L14",
    "geneSymbol": "Mrpl14",
    "synonyms": ["Rpml32", "MRP-L32", "1110006I11Rik"],
    "humanGeneSymbols": ["MRPL14"],
    "humanSymbolSynonyms": ["MRP-L32", "RPML32"],
    "esCellProductionStatus": null,
    "mouseProductionStatus": null,
    "phenotypeStatus": null,
    "phenotypingDataAvailable": false
  },
  {
    "mgiGeneAccessionId": "MGI:2442934",
    "geneName": "membrane integral NOTCH2 associated receptor 2",
    "geneSymbol": "Minar2",
    "synonyms": ["A730017C20Rik"],
    "humanGeneSymbols": ["MINAR2"],
    "humanSymbolSynonyms": ["KIAA1024L"],
    "esCellProductionStatus": "ES Cells Produced",
    "mouseProductionStatus": "Mice Produced",
    "phenotypeStatus": "Phenotyping finished",
    "phenotypingDataAvailable": true
  }
]
```

## Allele Services

### Allele Products Service

Request pattern: /alleles/<**mgiGeneAccessionId**>/<**alleleName**>

Request example: GET /alleles/MGI:1929293/tm1a(EUCOMM)Wtsi

Response datatype: JSON Object

#### Example

```json
{
  "mgiGeneAccessionId": "MGI:1929293",
  "geneSymbol": "Cib2",
  "alleleName": "tm1a(EUCOMM)Wtsi",
  "alleleDescription": "KO first allele (reporter-tagged insertion with conditional potential)",
  "alleleMapUrl": "https://www.i-dcc.org/imits/targ_rep/alleles/11268/allele-image?simple=true.jpg",
  "genbankFileUrl": "https://www.i-dcc.org/imits/targ_rep/alleles/11268/escell-clone-genbank-file",
  "emsembleUrl": "http://www.ensembl.org/Mus_musculus/Location/View?g=ENSMUSG00000037493",
  "miceProducts": [
    {
      "colonyName": "MRC - Harwell-EPD0337_2_D04-1",
      "geneticBackground": "C57BL/6NTac",
      "productionCentre": "Harwell",
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/mouse/MRC%20-%20Harwell-EPD0337_2_D04-1/",
      "esCellParentColony": "EPD0337_2_D04",
      "orderLink": "https://www.infrafrontier.eu/search?keyword=Cib2"
    }
  ],
  "esCellProducts": [
    {
      "esCellClone": "EPD0337_2_B03",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_B03/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_H04",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_H04/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_D02",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_D02/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_G04",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_G04/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_G03",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_G03/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_F03",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_F03/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_G01",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_G01/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_D04",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_G01/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_B02",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_D04/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "esCellClone": "EPD0337_2_F02",
      "esCellStrain": "C57BL/6N-A/a",
      "parentalCellLine": "JM8A1.N3",
      "ikmcProject": 41713,
      "qcDataUrl": "https://www.mousephenotype.org/data/alleles/qc_data/es_cell/EPD0337_2_B02/",
      "targetingVector": "PG00073_Z_5_H01",
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    }
  ],
  "targetingVectorProducts": [
    {
      "designOligos": null,
      "targetingVector": "PRPGS00073_A_H01",
      "cassette": "L1L2_Bact_P",
      "backbone": "L3L4_pD223_DTA_spec",
      "ikmcProject": 41713,
      "genbankFile": null,
      "vectorMap": null,
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "designOligos": null,
      "targetingVector": "PG00073_Z_5_H01",
      "cassette": "L1L2_Bact_P",
      "backbone": "L3L4_pD223_DTA_spec",
      "ikmcProject": 41713,
      "genbankFile": null,
      "vectorMap": null,
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "designOligos": null,
      "targetingVector": "PG00073_Z_3_H01",
      "cassette": "L1L2_Bact_P",
      "backbone": "L3L4_pD223_DTA_spec",
      "ikmcProject": 41713,
      "genbankFile": null,
      "vectorMap": null,
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "designOligos": null,
      "targetingVector": "PG00073_Z_6_H01",
      "cassette": "L1L2_Bact_P",
      "backbone": "L3L4_pD223_DTA_spec",
      "ikmcProject": 41713,
      "genbankFile": null,
      "vectorMap": null,
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    },
    {
      "designOligos": null,
      "targetingVector": "PG00073_Z_7_H01",
      "cassette": "L1L2_Bact_P",
      "backbone": "L3L4_pD223_DTA_spec",
      "ikmcProject": 41713,
      "genbankFile": null,
      "vectorMap": null,
      "order": "https://www.eummcr.org/order?add=MGI:1929293&material=es_cells"
    }
  ]
}
```

#### Changes

- mgiGeneAccessionId **ADDED**
- alleleName **ADDED**
- geneSymbol **ADDED**

## Phenotype Services

## Image Services

## Data Services
