# Complex modeling using ColabFold

This page is prepared to model the complex of phage G3P and E. Coli TolA coreceptor using ColabFold.
<img width="423" alt="image" src="https://user-images.githubusercontent.com/64282221/160210381-96574697-cbaf-4d00-83f5-8fb528f7a501.png">

## Biological Investigation:
- **Monomer 1:** Attachment protein G3P, Escherichia phage If1 (Bacteriophage If1)

Uniprot ID: O80297 https://www.uniprot.org/uniprot/O80297 

- **Monomer 2:** Cell envelope integrity inner membrane protein TolA, E. Coli

Uniprot ID: Q8X965 https://www.uniprot.org/uniprot/Q8X965 

<img width="888" alt="image" src="https://user-images.githubusercontent.com/64282221/160210555-3e735b3b-c3ba-4600-8d0e-f1591585cd2c.png">

- It is known that N1 domain of G3P (17-81 res.) binds to CT domain of TolA (268-394 res.), so we will use these domains to model the complex structure. You can read the [relevant paper](https://reader.elsevier.com/reader/sd/pii/S002228361001260X?token=DB99DA48FE133670DABFD590C40756BE90D947E4CA2B329B42FF134E7FFB0BE337C2564EC5BDDC81D801D603AC2F793E&originRegion=us-east-1&originCreation=20220325214322).


## ColabFold
Website Link: https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/AlphaFold2.ipynb 

<img width="960" alt="image" src="https://user-images.githubusercontent.com/64282221/160210520-9fd16dd2-577d-4a59-bdb9-f27fc517afd5.png">


## Preparing input fasta files
- Input file should be provided as one line.
- There should be **:** sign between sequences.

<img width="828" alt="image" src="https://user-images.githubusercontent.com/64282221/160210349-cf4a6bbd-879d-4766-862f-a48b3bc7131c.png">

- **Final input sequence in ColabFold format:** Let's select the interacted domains from the input sequences and prepare the input file for ColabFold as below:

TTDAECLSKPAFDGTLSNVWKEGDSRYANFENCIYELSGIGIGYDNDTSWNGHWTPVRAAD:SGADINNYAGQIKSAIESKFYDASSYAGKTCTLRIKLAPDGMLLDIKPEGGDPALCQAALAAAKLAKIPKPPSQAVYEVFKNAPLDFKPA

- Please copy and paste the above sequence to the **_query_sequence_** section, give a job name and please run all.

<img width="850" alt="image" src="https://user-images.githubusercontent.com/64282221/160210642-22030ce5-0a3f-4987-b840-64560c1b84b8.png">

- You can follow the progression of your run in **_Run Prediction_** section.

<img width="578" alt="image" src="https://user-images.githubusercontent.com/64282221/160209726-22bc1b24-9c42-4b13-b95f-6bccc969cac4.png">

-  When the run is completed you see the results in **_Display 3D structure_** section.

<img width="451" alt="image" src="https://user-images.githubusercontent.com/64282221/160210061-a31412ed-c091-4ce3-89bd-5411c4ed63ab.png">

- The results are ranked according to pLDDT score between 0-100; higher score means better confidence. You read more on it from [here](https://alphafold.ebi.ac.uk/faq#faq-5).

- If you are using Chrome, the results are automatically downloaded to your computer as zip file. Otherwise you can download manually from the left section as zip file.

- Now, you can download the result file from [here](https://github.com/BurcuOzden/CSB-WS/blob/main/Workshoprunsample_c21f2.result.zip).

## Comparison of the generated models with the experimental structure

- Download the experimental structure from Protein Data Bank (PDB): https://www.rcsb.org/
- Name of complex: crystal structure of g3p from phage IF1 in complex with its coreceptor, the C-terminal domain of TolA
- PDB ID: **[2X9A](https://www.rcsb.org/structure/2X9A)**

<img width="743" alt="image" src="https://user-images.githubusercontent.com/64282221/160210788-758c6c4f-9bc0-4426-af36-d02d6dcc5633.png">

- Open both the crystal structure and the generated models in PyMOL.
- Let's go deeper in PyMOL!
- Useful PyMOL tips:
To show the structures as cartoon: _as cartoon_

To align one structure to the another: _align model_name, target_name_

To color the structure according to the B-factor column which contains lDDT scores similar to the AF2 colors: _spectrum b, rainbow_rev, model_name_


