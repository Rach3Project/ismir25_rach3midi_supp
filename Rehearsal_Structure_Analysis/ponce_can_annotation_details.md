
### Annotation File 2
- **Filename**: 2024-08-27_18-16_03_ponce_20Can-part2_annot.mid
- **Download**: [MIDI](./annotated_files/2024-08-27_18-16_03_ponce_20Can/2024-08-27_18-16_03_ponce_20Can-part2_annot.mid)
- **Groups**: 6
- **Description**: A longer example of an intermediate level repertoire with some overlaps between groups (specifically, some groups are subsets of others). There are several note mistakes and note repetitions. The most challenging aspect are compositional variations between intervals of the same group, where the rh is the same but the lh is different. Furthermore, some groups have 2 related intervals only. 

#### Visual Overview

<table>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group1.png" width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group2.png" width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group3.png"width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group4.png" width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group5.png" width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group6.png" width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  
</table>

#### Challenges per group
- Group 1: The intervals are around 7 bins long,
  - so despite occuring as a diagonal without interruptions, the group's first interval pair would be undetected unless the minimum_length value is set to be very low.
  - Its second interval pair would also not result in a diagonal due to the latter interval being a variation with a different left hand.

- Group 2: this group relates intervals that are based on variants. When this happens, then even in the case of no extra or missing notes, the intervals belonging to a variant will include a different number of bins than those of the other.

- Group 3: challenges are similar to group 2

- Groups 4, 5, and 6: The intervals are longer and they are not variants; the differences between them are due to rehearsal elements.

A closer look at the similarity matrixes between intervals of a group can demonstrate the above traits.

<table>
  <tr>
    <td align="center" width="50%">
      <a href="./figures/ponce_can/ponce20can_group2_intcomb1.png">
        <img src="./figures/ponce_can/ponce20can_group2_intcomb1.png" width="250px" alt="Annotation Example 1">
      </a>
      <br>
      <em>Group 2 Example showing diagonal shifting due to compositional variations</em>
    </td>
    <td align="center" width="50%">
      <a href="./figures/ponce_can/ponce20can_group4_intcomb2.png">
        <img src="./figures/ponce_can/ponce20can_group4_intcomb2.png" width="250px" alt="Annotation Example 2">
      </a>
      <br>
      <em>Group 4 Example showing relatively long diagonals with some gaps and a shift towards the end</em>
    </td>
  </tr>
    <tr>
    <td align="center" width="50%">
      <a href="./figures/ponce_can/ponce20can_group5_intcomb2.png">
        <img src="./figures/ponce_can/ponce20can_group5_intcomb2.png" width="250px" alt="">
      </a>
      <br>
      <em> Group 5 example</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/ponce20can_group6_intcomb1.png" width="250px" alt="">
      </a>
      <br>
      <em>Group6 Example</em>
    </td>
  </tr>
</table>

*The tick indices reflect the bin numbers within the SSM of the whole rehearsal.*

### Walkthrough of the Rehearsal Structure Analysis Pipeline

#### Diagonal Finding (Step 1):

This phase is very important because these diagonals are the only information passed from the SSM onto the subsequent pipeline phases. For the diagonal finding approach to pick all necessary diagonals for further grouping and filtering, our initial hypothesis is that there needs to be a balance between the following tradeoffs:

- Groups 1, 2, and 3 need shorter min_length settings
- Groups 4, 5, and 6 could rely on longer minimum length settings, although shorter settings could also help in identifying the smaller shifted diagonals for later grouping.

The light blue lines indicate the diagonals found using:
- minimum length = 10
- gap tolerance = 5 (gap tolerance must be less than min length)
- similarity threshold = 0.2

<table>
  <tr>
    <td align="center" width="70%">
      <a href=./figures/ponce_can/diagonalsearch_10_0-2_5.png">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5.png" width="600 px" alt="Diagonal Search">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
</table>


<table>
  <tr>
    <td align="center" width="70%">
      <a href="./figures/ponce_can/ponce20can_diagonaldist_10_0-2_5.png">
        <img src="./figures/ponce_can/ponce20can_diagonaldist_10_0-2_5.png" width="400 px" alt="Diagonal Length Distribution">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
</table>

One way to understand the effectiveness of these settings is to see how the diagonals relate to the retrieval of group information. Below are the self similarity matrixes overlayed with interval information and the retrieved set of diagonals above. The intersection between the green horizontal and vertical rectangles represents the similarity matrix between 2 intervals of that group (for example, one of such intersections would a similarity matrix as shown for the intra-group fragment pairs above)

<table>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5_group1.png" width="450px" alt="">
      </a>
      <br>
      <em>Group 1</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5_group2.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 2</em>
    </td>
  </tr>
    <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5_group3.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 3</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5_group4.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 4</em>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5_group5.png" width="450px" alt="">
      </a>
      <br>
      <em>Group 5</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_10_0-2_5_group6.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 6</em>
    </td>
</table>

From the plots above we can see the following:
- As initially thought, this search does not yield enough diagonals in the intersecting boxes of the first 3 groups.
- For the last 3 groups it would be possible to postprocess this search meaningfully, although the recall is also not perfect. 

In contrast, we use different settings and observe their effect:

- minimum length = 7
- gap tolerance = 4 (gap tolerance must be less than min length)
- similarity threshold = 0.15


<table>
  <tr>
    <td align="center" width="70%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4.png" width="600 px" alt="Diagonal Length Distribution">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
</table>

<table>
  <tr>
    <td align="center" width="70%">
      <a href="./figures/ponce_can/diagonaldist_7_0-15_4.png">
        <img src="./figures/ponce_can/diagonaldist_7_0-15_4.png" width="400 px" alt="Diagonal Length Distribution">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
</table>

This is the observed effect on the groups

<table>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4_group1.png" width="450px" alt="">
      </a>
      <br>
      <em>Group 1</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4_group2.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 2</em>
    </td>
  </tr>
    <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4_group3.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 3</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4_group4.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 4</em>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4_group5.png" width="450px" alt="">
      </a>
      <br>
      <em>Group 5</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/ponce_can/diagonalsearch_7_0-15_4_group6.png" width="450px" alt="">
      </a>
      <br>
      <em> Group 6</em>
    </td>

</table>

There are several things to note:

- These settings mean that we want to retrieve diagonals of length 7 permitting up to 4 mismatches. This is too permissive to apply for certain types of compositions which would involve periodically repeating bins.

- Furthermore, despite being permissive settings, they still do not perfectly retrieve peaks in the intersections of groups 1, 2 and 3. However, this is likely the effect of grouping intervals that are variations of one another, where even in the case of perfect matches there would be variations between bins (let alone mistakes or repetitions).

- However, the short diagonals from these settings would allow some information pertaining to the first 3 groups to be passed to the next pipeline phases. 


### Grouping and Merging
As shown in the technical appendix, the found diagonals are grouped based on horizontal and vertical overlaps, followed by a final merging phase is simply to merge the horizontal and vertical groups based on overlapping diagonals. 

Examples of diagonal length distributions based on multiple settings (interval_overlap_ratio = 0.85)

<table>
  <tr>
    <td align="center" width="10%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em>params</em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em>horizontal</em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em>vertical </em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em>merged</em>
    </td>
  </tr>
    <tr>
    <td align="center" width="10%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em> </em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
  <tr>
    <td align="center" width="10%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em> </em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
  <tr>
    <td align="center" width="10%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em> </em>
    </td>
    <td align="center" width="30%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
</table>


### Interval Results

We share 

