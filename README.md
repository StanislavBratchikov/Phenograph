# Phenograph
Phenograph algorithm implementation
## Motivation
Project aims at researching whether splenic macrophages maintain their population via local proliferation (which classifies 
them as resident) or require monocytes for their maintenance. 
## Intro 
More about Macrophages classification can be read [here](https://pubmed.ncbi.nlm.nih.gov/32187515/). Macrophages of intereset constitute of marginal zone macrophages (MZM), marginal zone metallophilic macrophages (MMM) and tingible body macrophages (TBM). Red pulp macrophages (RPM) are tissue resident. 
### Experiment data 
[Cx3cr1-ERCre x zsGreen mice](https://pubmed.ncbi.nlm.nih.gov/23273845/) were pulsed with tamoxifen on day ```0``` to label all Cx3cr1-expressing cells. Spleens were harvested on day ```7```, ```28```, ```35``` and ```42```. In addition, at day 28 some mice were infected with low dose of influenza virus to activate lymphoid follicles in the spleen. RPM do not express Cx3cr1 and should not be labeled with GFP. MMM, MZM and TBM do express Cx3cr1 and will be permanently labeled with GFP.
### General outline of the project 
Using dimensionality techniques and clustering approaches, we want to identify subset of cells of interest based on fluoroscent markers without using GFP. Once cells are clustered, the percentage of GFP expressing cells within the cluster over time will be computed. If the number of GFP+ cells per cluster remains the same between day 7 and day 42 this means that these cells are tissue-resident macrophages. If the number will drop, this will mean that cells require flux of monocytes for their maintenance.  
## Project plan 
- Install cytofkit/Rphenograph on quest, make sure it has enough memory, etc
- Chose a file and run Rphenograph on it. Try different transformations that fit data better. See if clusters can be obtained and whether these clusters make sense.
  - Review results with Sasha
- If the previous step is successful, concatenate all files and run Rphenograph on it to see if it can handle ~1M events
  - Review results with Sasha
- If the previoes step is successful, run clustering on all markers except GFP. Annotate those clusters (review it with Sasha). Estemate percentage of cells over time
- Reproduce the same analysis using downsampled original files with MerTK events (cells). This will illustrate loss of GFP_ cells in short living populations like monocytes and DCs. 
