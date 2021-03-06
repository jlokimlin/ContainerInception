
## Outcomes

By the end of this tutorial, the reader will have a working knowledge of packaging reusable workflows. The example in our use cases involve a typical quality control and mapping of RNA-seq data of Sorghum bicolor. 

## Use case 0: No containers and no CWL. [Click here!](use\_case\_0/README.md)

![alt text](generate_flowchart/flowChartImages/useCase0.png)

- Most users fall in this categories. 
- It is difficult to update the modules, it does not scale, and reproducibility is not maintained. 
- Some people run them as bash script while others run them as individual software.

## Use case 1: Container(s) with no CWL [Click here!](use\_case\_1/README.md)

![alt text](generate_flowchart/flowChartImages/useCase11.png)

- Docker users fall under this category.
- Docker is supposed to be using one thing at a time. For example one of the authors uses 1,000 lines to create a docker. 
- Difficult to swap in the wrapper script.
- Sometimes you have multiple containers but you have to string them together using bash script but it’s not easy stitch them and will mostly be hardcoded

## Use case 2: Both container(s) and CWL [Click here!](use\_case\_2/README.md)

![alt text](generate_flowchart/flowChartImages/useCase2.png)

- It’s difficult to write them or no clear standard and everyone uses cwl. 
- It’s difficult to write but easier to edit them or swap them 
- Create docker container with tools to run the pipelines.
- Define modularity layers
- Launch/Run via CWLTool/Rabix

## Use case 3: Interacting workflows with CWL 
- Two interacting workflows, that is, one workflow (current one) and two other workflows (SNP calling and differential expression analysis)
- TODO

### Requirements
Docker
cwltool=1.0.20180330141240

### To run the workflow
cwltool --non-strict pipeline_name.cwl pipeline_name.cwl.json

### To modify modules
Edit pipeline_name.cwl to describe specific steps (in our case pipelines) and the json that pertains to the module. ( NOTE: Ideally this should be done via rabix, and a more simple experience should be available to the user)

## System requirements
To run the examples in our tutorial, you machine must meet the following requirements
python=2.7
GNU bash=
fastqc=0.11.7
trimmomatic=0.36
bowtie=2.3.4.1
tophat=2.1.1
