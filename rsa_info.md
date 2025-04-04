## Rehearsal Structure Analysis Examples

To support the manuscript (and in addition to the [technical appendix](./technical_appendix.pdf)), we share:

1. 3 of the 5 annotated file examples (+details), analysis insights, and results of applying the proposed approach for finding related fragments in a rehearsal. (The full set to be made available after publication. 

2. Additional analysis of unnannotated files for rehearsal structure insights. (here highlight the minimum length parameter sensitivity)


### Annotation Files and Corresponding Results
#### Annotation File Format
Each annotation is provided as a midi file:
- track 0 is the performance.
- tracks 1-n are for the annotations of related fragment groups
    - each track includes the intervals of a group, where each interval is represented by the span of a midi note (24)
 
Although based on rehearsal files from the < Anonymized> MIDI dataset, they are all constructed to demonstrate interesting examples of what we consider equivalent musical fragments. 
Annotations were made using logic pro. 

#### Example Annotation Files

For each annotation file, a page is included with: 
- pianoroll plots with the time intervals of the annotated groups marked.

- Analysis insights of the phases of rehearsal segmentation pipeline phases described in the manuscript (for exact details, please refer to the [technical appendix](./technical_appendix.pdf))
  
2. Result of the diagonal finding phase. 
| File | Num Groups | Download | Annot. and Results Info |
|-----------|-------------|----------|-------------|
| Mozart Variations   | 2 | [MIDI](./rsa_resources/example_annot/02_2024-08-02_Mozart_Var/02_2024-08-02_Mozart_Var_constructed_annot.mid) |[Info and Results](./rsa_resources/mozart_var_annotation_details.md)|
|  Ponce20Can  |  6  | [MIDI](./rsa_resources/example_annot/02_2024-08-02_Mozart_Var/02_2024-08-02_Mozart_Var_constructed_annot.mid) |[Info and Results](./rsa_resources/ponce_can_annotation_details.md)|
|  PonceGav  |  6  | [MIDI](./rsa_resources/example_annot/02_2024-08-02_Mozart_Var/02_2024-08-02_Mozart_Var_constructed_annot.mid) |[Info and Results](./rsa_resources/ponce_gav_annotation_details.md)|
|  Warmup  |  8  | [MIDI](./rsa_resources/example_annot/02_2024-08-02_Mozart_Var/02_2024-08-02_Mozart_Var_constructed_annot.mid) |[Info and Results](./rsa_resources/warmup_file_annotation_details.md)|


### Additional Analysis on Unannotated files
Comparision between results on consecutive takes of the same piece
  


