# Supplementary Materials for  "Enabling Empirical Analysis of Piano Performance Rehearsal with the *Anonymized* MIDI Dataset".

## Abstract

Piano performance analysis is a well-studied field in MIR, owing to the availability of open datasets of piano performance.
However, pianists spend more time rehearsing than performing, and the process of piano rehearsals remains understudied. 
The study of piano rehearsals can offer interesting insights into the strategies adopted by a pianist in order to learn, interpret and eventually perform musical pieces.
Studying the process of rehearsal requires computational methods that differ from those used for piano performance, due to challenges like mistakes, repetitions of musical segments, or forward and backward skips to sections in the piece.
The scarcity of publicly available rehearsal data limits the empirical understanding of these challenges. 

We release the *Anonymized* MIDI Dataset, an openly available collection of MIDI files containing more than 750 hours of recordings of piano rehearsals by four pianists (3 advanced, 1 beginner), collected over a period of more than 4 years. 
This dataset records the progression of pianists learning new repertoire, as well as practicing familiar pieces, all in the Western Classical tradition.

This paper further introduces possible avenues of using this dataset for the computational analysis of piano practice such as rehearsal structure analysis, rehearsal-to-score alignment and mistake identification.
We also discuss the challenges and limitations of using state of the art methods for piano performance analysis for this type of data.
In addition, we provide the code that was used to preprocess and analyze the recorded rehearsals.


### Resources

- For detailed information about the Fingerprinting and Rehearsal Structure Analysis algorithms, please refer to the [technical annex](./technical_annex.pdf)

- For annotations and results of the Rehearsal Structure Analysis pipeline phases, please refer to the [Rehearsal Structure Analysis](./Rehearsal_Structure_Analysis/rsa_info.md) section.