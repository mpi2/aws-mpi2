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
    "datasetId": "4c8064a66319bd31b365c587261ac70c",
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

- Add statisticalResultId

### Gene Statistical Results Service

Request pattern: /genes/<**mgiGeneAccessionId**>/statistical-results

Request example: GET /genes/MGI:1929293/statistical-results

Response datatype: JSON Array<JSON Object>

#### Example

```json
[
  {
    "datasetId": "27b657a688e59ab284d9e710ec66d721",
    "strainAccessionId": "MGI:2164831",
    "strainName": "C57BL/6NTac",
    "geneticBackground": "involves: C57BL/6NTac",
    "colonyId": "H-CIB2-D04-TM1B",
    "mgiGeneAccessionId": "MGI:1929293",
    "geneSymbol": "Cib2",
    "alleleAccessionId": "MGI:5548707",
    "alleleName": "targeted mutation 1b, Wellcome Trust Sanger Institute",
    "alleleSymbol": "Cib2<tm1b(EUCOMM)Wtsi>",
    "metadataGroup": "a8ee4a7178561c567069d111ea7338b8",
    "metadataValues": [
      "Anesthesia used for blood collection = Gas anaesthesia with Isofluorane|Anticoagulant = EDTA|Blood analysis experimenter ID = null|Blood collection experimenter ID = 1|Blood collection tubes = Kabe Labortechnik 200ul EDTA|Date and time of blood collection = 2012-10-16T00:00:00+0100|Date and time of sacrifice = 2012-10-16T00:00:00+0100|Equipment ID = Haematology analyser|Equipment manufacturer = Siemens Medical Solutions Diagnostics|Equipment model = Advia 2120|ID for blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Samples kept on ice between collection and analysis = No|Service-related calibration start date = 2011-09-13|Storage temperature from blood collection until measurement = 18-22",
      "Anesthesia used for blood collection = Gas anaesthesia with Isofluorane|Anticoagulant = EDTA|Blood analysis experimenter ID = 3641252|Blood collection experimenter ID = 1|Blood collection tubes = Kabe Labortechnik 200ul EDTA|Date and time of blood collection = 2012-10-09T00:00:00+0100|Date and time of sacrifice = 2012-10-09T00:00:00+0100|Equipment ID = Haematology analyser|Equipment manufacturer = Siemens Medical Solutions Diagnostics|Equipment model = Advia 2120|ID for blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Samples kept on ice between collection and analysis = No|Service-related calibration start date = 2011-09-13|Storage temperature from blood collection until measurement = 18-22",
      "Anesthesia used for blood collection = Gas anaesthesia with Isofluorane|Anticoagulant = EDTA|Blood analysis experimenter ID = 3641252|Blood collection experimenter ID = 1|Blood collection tubes = Kabe Labortechnik 200ul EDTA|Date and time of blood collection = 2012-10-16T00:00:00+0100|Date and time of sacrifice = 2012-10-16T00:00:00+0100|Equipment ID = Haematology analyser|Equipment manufacturer = Siemens Medical Solutions Diagnostics|Equipment model = Advia 2120|ID for blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Samples kept on ice between collection and analysis = No|Service-related calibration start date = 2011-09-13|Storage temperature from blood collection until measurement = 18-22"
    ],
    "lifeStageAcc": "IMPCLS:0005",
    "lifeStageName": "Early adult",
    "dataType": "unidimensional",
    "productionCenter": "MRC Harwell",
    "phenotypingCenter": "MRC Harwell",
    "projectName": "MRC",
    "resourceName": "IMPC",
    "resourceFullname": "IMPC",
    "pipelineStableKey": 8,
    "pipelineStableId": "HRWL_001",
    "pipelineName": "Harwell",
    "procedureStableKey": 675,
    "procedureStableId": "IMPC_HEM_002",
    "procedureName": "Hematology",
    "parameterStableKey": 29872,
    "parameterStableId": "IMPC_HEM_037_001",
    "parameterName": "Basophil cell count",
    "summaryStatistics": {
      "femaleControlCount": 205,
      "femaleControlMean": 0.0468780487804878,
      "femaleMutantCount": 6,
      "femaleMutantMean": 0.0616666666666667,
      "maleControlCount": 251,
      "maleControlMean": 0.0619123505976096,
      "maleMutantCount": 13,
      "maleMutantMean": 0.153846153846154
    },
    "status": "Successful",
    "testedSexes": ["male", "female"],
    "phenotypeSex": "male",
    "significant": true,
    "classificationTag": "With phenotype threshold value 1e-04 - Significant for males only",
    "reportedPValue": 0.604448492284445,
    "reportedEffectSize": 1.63786815120672,
    "statisticalMethod": {
      "name": "Linear Mixed Model framework, LME, not including Weight",
      "attributes": {
        "femaleKoEffectPValue": 0.6507057018595,
        "femaleKoEffectStderrEstimate": 0.0161151365129797,
        "femaleKoParameterEstimate": -0.00730816634092395,
        "femalePercentageChange": -1.79681770347269,
        "genotypeEffectPValue": 0.604448492284445,
        "genotypeEffectParameterEstimate": -0.0083742939959617,
        "genotypeEffectStderrEstimate": 0.0161394645007291,
        "group1Genotype": "control",
        "group1ResidualsNormalityTest": 6.98086813359277e-10,
        "group2Genotype": "experimental",
        "group2ResidualsNormalityTest": 0.254972243907827,
        "interactionEffectPValue": 0.00589816756855721,
        "interactionSignificant": true,
        "interceptEstimate": 0.066858382256446,
        "interceptEstimateStderrEstimate": 0.0103192729095486,
        "maleKoEffectPValue": 0.000085900013922149,
        "maleKoEffectStderrEstimate": 0.0116096232226678,
        "maleKoParameterEstimate": 0.0465937908267818,
        "malePercentageChange": 82.4136213110961,
        "sexEffectPValue": 0.756207236209936,
        "sexEffectParameterEstimate": 0.00193815579518393,
        "sexEffectStderrEstimate": 0.00623384035083421,
        "maleEffectSize": 2.11836375815516,
        "femaleEffectSize": 0.150037233659509
      }
    },
    "softWindowing": {
      "bandwidth": 110,
      "shape": 1.04133291282715,
      "peaks": [15622, 15629],
      "minObsRequired": 140,
      "totalObsOrWeight": 208,
      "threshold": 1.49011611938477e-7,
      "numberOfDoe": 2,
      "doeNote": "no note available"
    },
    "significantPhenotype": {
      "id": "MP:0002606",
      "name": "increased basophil cell number"
    },
    "intermediatePhenotypes": [
      {
        "id": "MP:0002422",
        "name": "abnormal basophil morphology"
      },
      {
        "id": "MP:0011180",
        "name": "abnormal hematopoietic cell number"
      },
      {
        "id": "MP:0000217",
        "name": "abnormal leukocyte cell number"
      },
      {
        "id": "MP:0000716",
        "name": "abnormal immune system cell morphology"
      },
      {
        "id": "MP:0013658",
        "name": "abnormal myeloid cell morphology"
      },
      {
        "id": "MP:0000322",
        "name": "abnormal hematopoietic system morphology/development"
      },
      {
        "id": "MP:0000218",
        "name": "increased hematopoietic cell number"
      },
      {
        "id": "MP:0002396",
        "name": "abnormal myeloid leukocyte morphology"
      },
      {
        "id": "MP:0011181",
        "name": "abnormal granulocyte number"
      },
      {
        "id": "MP:0008250",
        "name": "abnormal hematopoietic cell morphology"
      },
      {
        "id": "MP:0020201",
        "name": "abnormal basophil cell number"
      },
      {
        "id": "MP:0013656",
        "name": "abnormal granulocyte morphology"
      },
      {
        "id": "MP:0012442",
        "name": "abnormal leukocyte morphology"
      },
      {
        "id": "MP:0002441",
        "name": "abnormal blood cell morphology"
      },
      {
        "id": "MP:0008246",
        "name": "abnormal immune system morphology"
      },
      {
        "id": "MP:0013657",
        "name": "abnormal myeloblast morphology/development"
      },
      {
        "id": "MP:0000685",
        "name": "abnormal bone marrow cell morphology/development"
      },
      {
        "id": "MP:0002414",
        "name": "abnormal myeloblast morphology/development"
      },
      {
        "id": "MP:0002398",
        "name": "abnormal bone marrow cell morphology/development"
      }
    ],
    "topLevelPhenotypes": [
      {
        "id": "MP:0005387",
        "name": "immune system phenotype"
      },
      {
        "id": "MP:0005397",
        "name": "hematopoietic system phenotype"
      }
    ],
    "potentialPhenotypes": [
      {
        "id": "MP:0002606",
        "name": "abnormal basophil cell number"
      },
      {
        "id": "MP:0012442",
        "name": "increased basophil cell number"
      },
      {
        "id": "MP:0002607",
        "name": "decreased basophil cell number"
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

### Phenotype Summary Service

Request pattern: /phenotype/<**phenotypeId**>/summary/

Request example: GET /phenotype/MP:0002792/summary/

Response datatype: JSON Object

#### Example

```json
{
  "phenotypeId": "MP:0002792",
  "phenotypeName": "abnormal retina vasculature morphology",
  "phenotypeDefinition": "any anomaly of the structure or arrangement of blood vessels supplying the retina",
  "phenotypeSynonyms": ["abnormal retinal vasculature morphology"],
  "significantGenes": 216,
  "notSignificantGenes": 7155,
  "procedures": [
    {
      "pipelineStableId": "TCP_001",
      "pipelineName": "TCP Pipeline",
      "procedureStableId": "IMPC_EYE_002",
      "procedureName": "Eye Morphology",
      "procedureStableKey": 926,
      "description": "To detect abnormalities in eye morphology."
    },
    {
      "pipelineStableId": "JAX_001",
      "pipelineName": "JAX Pipeline",
      "procedureStableId": "IMPC_EYE_001",
      "procedureName": "Eye Morphology",
      "procedureStableKey": 563,
      "description": "To detect abnormalities in eye morphology."
    }
  ],
  "topLevelPhenotypes": [
    { "id": "MP:0005391", "name": "vision/eye phenotype" },
    { "id": "MP:0005385", "name": "cardiovascular system phenotype" }
  ]
}
```

## Image Services

## Data Services

### Statistical Results Metadata Service

Request pattern: /datasets/<**datasetId**>/

Request example: GET /datasets/4c8064a66319bd31b365c587261ac70c/

Response datatype: JSON Object

#### Example

```json
{
	"statisticalResultId": "17a32770bca0b39aafafe4ddd621228f",
	"strainAccessionId": "MGI:2159965",
	"strainName": "C57BL/6N",
	"geneticBackground": "involves: C57BL/6N",
	"colonyId": "MDZE",
	"mgiGeneAccessionId": "MGI:1344394",
	"geneSymbol": "Lamc3",
	"alleleAccessionId": "MGI:4364864",
	"alleleName": "targeted mutation 1a, Wellcome Trust Sanger Institute",
	"alleleSymbol": "Lamc3<tm1a(KOMP)Wtsi>",
	"metadataGroup": "d307adf61223cf1c546130cb9f701bdd",
	"metadataValues": [
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T09:40:00+01:00|Date and time of sacrifice = 2012-06-25T09:40:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 562|Blood collection experimenter ID = 463|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-08-15T09:43:00+01:00|Date and time of sacrifice = 2012-08-15T09:43:00+01:00|Date of measurement = 2012-08-15|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T09:48:00+01:00|Date and time of sacrifice = 2012-06-25T09:48:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-07-31T10:35:00+01:00|Date and time of sacrifice = 2012-07-31T10:35:00+01:00|Date of measurement = 2012-07-31|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T09:51:00+01:00|Date and time of sacrifice = 2012-06-25T09:51:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-07-31T10:40:00+01:00|Date and time of sacrifice = 2012-07-31T10:40:00+01:00|Date of measurement = 2012-07-31|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-07-31T10:31:00+01:00|Date and time of sacrifice = 2012-07-31T10:31:00+01:00|Date of measurement = 2012-07-31|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T09:31:00+01:00|Date and time of sacrifice = 2012-06-25T09:31:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 562|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-07-17T09:25:00+01:00|Date and time of sacrifice = 2012-07-17T09:25:00+01:00|Date of measurement = 2012-07-17|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T10:39:00+01:00|Date and time of sacrifice = 2012-06-25T10:39:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T10:48:00+01:00|Date and time of sacrifice = 2012-06-25T10:48:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-06-25T10:35:00+01:00|Date and time of sacrifice = 2012-06-25T10:35:00+01:00|Date of measurement = 2012-06-25|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 562|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-07-17T09:15:00+01:00|Date and time of sacrifice = 2012-07-17T09:15:00+01:00|Date of measurement = 2012-07-17|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22",
		"Anesthesia used for blood collection = Injection narcosis with Ketamine (100mg/kg)/Xylazine (10mg/kg)|Anticoagulant = Lithium Heparin|Blood analysis experimenter ID = 652|Blood collection experimenter ID = 307|Blood collection tubes = Kabe Labortechnik Lithium heparin coated tubes|Date and time of blood collection = 2012-07-31T10:37:00+01:00|Date and time of sacrifice = 2012-07-31T10:37:00+01:00|Date of measurement = 2012-07-31|Equipment ID = Olympus AU400|Equipment manufacturer = Olympus Diagnostics|Equipment model = AU 400|ID of blood collection SOP = ESLIM_024_001|Method of blood collection = Retro-orbital puncture|Sample dilution = Neat plasma|Sample status = Fresh|Samples kept on ice between collection and analysis = No|Storage temperature from blood collection till measurement = 18-22"
	],
	"lifeStageAcc": "IMPCLS:0005",
	"lifeStageName": "Early adult",
	"dataType": "unidimensional",
	"productionCentre": "WTSI",
	"phenotypingCentre": "WTSI",
	"projectName": "MGP",
	"resourceName": "IMPC",
	"resourceFullName": "IMPC",
	"pipelineStableKey": 15,
	"pipelineStableId": "MGP_001",
	"pipelineName": "MGP Select Pipeline",
	"procedureStableKey": 96,
	"procedureStableId": "IMPC_CBC_001",
	"procedureName": "Clinical Chemistry",
	"procedureGroup": "IMPC_CBC",
	"parameterStableKey": 2274,
	"parameterStableId": "IMPC_CBC_011_001",
	"parameterName": "Iron",
	"status": "Successful",
	"sex": null,
	"phenotypeSex": ["male", "female"],
	"significant": false,
	"classificationTag": "With phenotype threshold value 1e-04 - no significant change",
	"reportedPValue": 7.80678960971448e-4,
	"reportedEffectSize": 0.43943965117828,
	"significantPhenotype": null,
	"intermediatePhenotypes": [
		{ "id": "MP:0005636", "name": "abnormal mineral level" },
		{ "id": "MP:0001770", "name": "abnormal iron homeostasis" },
		{ "id": "MP:0000192", "name": "abnormal iron level" },
		{ "id": "MP:0009642", "name": "abnormal circulating iron level" },
		{ "id": "MP:0001764", "name": "abnormal blood homeostasis" },
		{ "id": "MP:0004152", "name": "abnormal ion homeostasis" },
		{ "id": "MP:0001765", "name": "abnormal circulating mineral level" },
		{ "id": "MP:0005637", "name": "abnormal homeostasis" },
		{ "id": "MP:0006357", "name": "abnormal mineral homeostasis" }
	],
	"topLevelPhenotypes": [
		{ "id": "MP:0005376", "name": "homeostasis/metabolism phenotype" }
	],
	"potentialPhenotypes": [
		{ "id": "MP:0004152", "name": "decreased circulating iron level" },
		{ "id": "MP:0004151", "name": "abnormal circulating iron level" },
		{ "id": "MP:0008810", "name": "increased circulating iron level" }
	],
	"id": "17a32770bca0b39aafafe4ddd621228f",
	"summaryStatistics": {
		"femaleControlCount": 2026,
		"femaleControlMean": 0.126436018905466,
		"femaleControlSd": 0.0161492934275664,
		"maleControlCount": 2048,
		"maleControlMean": 0.109283773241465,
		"maleControlSd": 0.0135672129450257,
		"femaleMutantCount": 7,
		"femaleMutantMean": 0.145857142857143,
		"femaleMutantSd": 0.016375068156892,
		"maleMutantCount": 7,
		"maleMutantMean": 0.103428571428571,
		"maleMutantSd": 0.00534967733784456,
		"bothMutantCount": null,
		"bothMutantMean": null,
		"bothMutantSd": null
	},
	"statisticalMethod": {
		"name": "Linear Mixed Model framework, LME, including Weight",
		"attributes": {
			"femaleKoEffectPValue": 7.80678960971364e-4,
			"femaleKoEffectStderrEstimate": 0.00613172825110546,
			"femaleKoParameterEstimate": 0.0206807754345856,
			"femalePercentageChange": 120.350232899946,
			"genotypeEffectPValue": 7.80678960971448e-4,
			"genotypeEffectStderrEstimate": 0.00613172825110546,
			"group1Genotype": "control",
			"group1ResidualsNormalityTest": 9.53172021487715e-6,
			"group2Genotype": "experimental",
			"group2ResidualsNormalityTest": 0.156987761349418,
			"interactionEffectPValue": 9.99103576744709e-4,
			"interactionSignificant": true,
			"interceptEstimate": 0.114262140583591,
			"interceptEstimateStderrEstimate": 0.00432035250644592,
			"sexEffectPValue": 0.0,
			"sexEffectParameterEstimate": -0.0186687737672265,
			"sexEffectStderrEstimate": 0.00135246737718949,
			"maleEffectSize": -0.504586474883906,
			"femaleEffectSize": 1.45924365924235
		}
	},
	"softWindowing": {
		"bandwidth": 275,
		"shape": 5.42604853784322,
		"peaks": [15516, 15538, 15552, 15567],
		"minObsRequired": 280,
		"totalObsOrWeight": 855,
		"threshold": 1.49011611938477e-7,
		"numberOfDoe": 4,
		"doeNote": "no note available"
	}
}
```
  
