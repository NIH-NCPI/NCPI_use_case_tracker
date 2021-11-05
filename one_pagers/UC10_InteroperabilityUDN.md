## UC10. Interoperability between Kids First/CAVATICA and SRA’s copy of the Undiagnosed Diseases Network (UDN)

**Title:** Interoperability between Kids First/CAVATICA and SRA’s copy of the Undiagnosed Diseases Network (UDN)

**Scientific Question/Use Case:** Interpreting genetic variants from clinical sequencing data is challenging. The number of rare variants in the human genome is vast, and the overwhelming majority of variants are not well understood in terms of their phenotypic impact. This poses a challenge for interpreting clinical sequencing data. To address the challenge of Variants of Unknown Significance (VUS), we have developed a pipeline to assess variants found on clinical sequencing using biobank cohorts with linked phenotyped data.

Our pipeline creates a phenotype risk score (PheRS) of the proband based on their clinical presentation described in human phenotype ontology terms (HPO). We then apply the PheRS to the biobank cohort, such that individuals with many overlapping features have a high PheRS, and those with no or few overlapping features have a low score. We then identify variant matched individuals (VGIs) present in the biobank cohort, and test if the VGIs have unexpectedly elevated phenotype risk scores. 

We have been using this pipeline to analyze Undiagnosed Disease Network (UDN) patients, using a biobank cohort called BioVU. Vanderbilt UDN patients have an average of 24 candidate variants identified on their research whole exome or whole genome sequencing. Using the PheRS pipeline, we “downgrade” an average three variant per proband, based on the finding that VGIs in BioVU do not have overlapping features with the proband.  

**Platform contact:**  Michele Mattioni, Kurt Rodarmer and Anne Deslattes Mays

**Researcher contact:** Lisa Bastarache

**Dataset:** [Clinical and Genetic Evaluation of Individuals with Undiagnosed Disorders Through the Undiagnosed Diseases Network (UDN](https://www.ncbi.nlm.nih.gov/projects/gap/cgi-bin/study.cgi?study_id=phs001232.v3.p2) and [insert Kids First datasets once determined, listed here: https://commonfund.nih.gov/kidsfirst/x01projects] 

**Goals:**

1. **Structuring phenotype data in Seven Bridges CAVATICA**.  This requires:

* *Discovery*: search/finding the dataset (within CAVATICA and/or in the Kids First Portal?),

2. **CAVATICA using RAS for authentication/authorization (v1.1)***

3. **pointing to data objects via dbGaP’s DRS**

4. **pulling phenotypic data from dbGaP on FHIR**

5. **running workflows and interactive analysis** (e.g., JupyterLab Notebooks and/or R studio tools) with these data within CAVATICA. Researcher may port/launch/share tools to CAVATICA to support her analysis.  

6. **Moving BAMS to hot storage in SRA** Yuriy Skripchenko (NCBI) will assess next steps within NCBI. As long as the data are hosted in an SRA AWS (US East1) bucket, there should be no egress (CAVATICA also uses US East1). It is easier if this is not a “requestor pays” account. In SRA, the signed urls go through DRS which do not return a “requestor pays” bucket. It could take several weeks to move the full 3886 genomes.  

7. **WGS File type**  BAMs are strongly preferred over SRA format because CAVATICA workflows, including those developed for Kids First, which already know how to consume BAM format and this will facilitate co-analysis with Kids First BAMs and CRAMs. These are also the same format that the UDN consortium uses for their own analyses. We want to lower the barrier to entry to the use case.  

8. **RAS: dbGaP has no v1.0 spec, must present a v1.1 RAS passport (CAVATICA to get directly from RAS) to dbGaP DRS server** There has been a lot of confusion in the community about this but recently confirmed. Agreement would be needed if someone creates new passports because DRS needs to understand the provenance. Gen3’s endpoint only has visas (not a passport, cannot use that in dbGaP).  

**What should be returned?:** 

**Which repositor(ies):**  Kids First Data Resource, NCBI SRA, NCBI dbGaP

**Which search portal:**  Kids First Data Resource Portal, NCBI SRA, NCBI dbGaP

**Which compute platform(s):** CAVATICA

**Which workflows/tools/apps/code:** PheRS

**NCPI use case link(s):** [FHIR UC3](https://github.com/NIH-NCPI/NCPI_use_case_tracker/issues/18)

**Status:**  *Proposal Stage*

**Presentation:** [KidsFirst & Undiagnosed Disease Network (UDN) Data via dbGaP/SRA](https://github.com/NIH-NCPI/NCPI_use_case_tracker/blob/main/assets/UDN%20Interop.pdf)


