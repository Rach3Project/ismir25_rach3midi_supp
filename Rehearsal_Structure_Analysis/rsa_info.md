## Rehearsal Structure Analysis Examples

To support the manuscript, we share: 
- 4 annotated file examples to demonstrate what is meant by equivalent fragments.
- Analysis insights and results of applying the rehearsal structure analysis pipeline on 2 of the files.
- Detailed walkthrough of the seach pipeline phases for 1 file.

The full set of annotated files and additional analysis of unnanotated rehearsal files will be made available after publication. 

### Annotation Files and Corresponding Results
#### Annotation File Format
Each annotation is provided as a midi file:
- track 0 is the performance.
- tracks 1-n are for the annotations of related fragment groups
    - each track includes the intervals of a group, where each interval is represented by the span of midi note #24
 
Although based on rehearsal files from the < Anonymized > MIDI dataset, they are all constructed to demonstrate interesting examples of what we consider equivalent musical fragments. 
Annotations were made using logic pro. 

#### Example Annotation Files

| File | Num Groups | Details |
|-----------|-------|-------------|
| Mozart Variations   | 2    |[Info and Results](./mozart_var_annotation_details.md)|
|  Ponce20Can  |  6   |[Info and Results: Detailed Walkthrough](./ponce_can_annotation_details.md)|
|  PonceGav  |  8   |[Info](./ponce_gav_annotation_details.md)|
|  Warmup  |  5   |[Info](./warmup_file_annotation_details.md)|

For each annotation file, a page is included with: 
- pianoroll plots with the time intervals of the annotated groups marked.

- Analysis insights of the phases of rehearsal segmentation pipeline phases described in the manuscript (for exact details, please refer to the [technical appendix](./technical_appendix.pdf))
  
- Selected Results with hyperparameter info.



  


