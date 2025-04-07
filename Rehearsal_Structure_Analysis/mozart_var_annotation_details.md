
### Annotation File 1
- **Filename**: 02_2024-08-02_Mozart_Var_constructed_annot.mid
- **Download**: [MIDI](./annotated_files/02_2024-08-02_Mozart_Var/02_2024-08-02_Mozart_Var_constructed_annot.mid)
- **Groups**: 2
- **Description**:
This example is the shortest and most straightforward from the annotated set. It is constructed from a rehearsal of Mozart’s Twelve
Variations on "Ah vous dirai-je, Maman"

#### Visual Overview

<table>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="" width="500px" alt="">
      </a>
      <br>
      <em>Group 1</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="" width="500px" alt="">
      </a>
      <br>
      <em>Group2</em>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/mozart_var/mozart_var_group1.png"width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="./figures/mozart_var/mozart_var_group2.png" width="500px" alt="">
      </a>
      <br>
      <em></em>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="" width="500px" alt="">
      </a>
      <br>
      <em>Between instances of group 1 there are no note order variations.</em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="" width="500px" alt="">
      </a>
      <br>
      <em>Between instances of group 2, there are note variations due to the execution of a trille towards the end of the fragment. The trille exists in the 2nd and 4th fragment instance.
We keep the fragments part of the same group because the goal is to allow for note error variations that could occur in music instrument practice</em>
    </td>
  
</table>

### Similarity Matrixes of intra-group fragment pairs
The tick indexes reflect the bin numbers within the SSM of the whole rehearsal. 

<table>
  <tr>
    <td align="center" width="50%">
      <a href="./figures/mozart_var/mozart_var_group1_intcomb1.png">
        <img src="./figures/mozart_var/mozart_var_group1_intcomb1.png" width="250px" alt="Annotation Example 1">
      </a>
      <br>
      <em></em>
    </td>
    <td align="center" width="50%">
      <a href="./figures/mozart_var/mozart_var_group2_intcomb0.png">
        <img src="./figures/mozart_var/mozart_var_group2_intcomb0.png" width="250px" alt="Annotation Example 2">
      </a>
      <br>
      <em>Annotation Example 2</em>
    </td>
  </tr>
    <tr>
    <td align="center" width="50%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em> Group 1 Example: since the consecutive bins maintain almost identical pitch information with the exception of a short break that does not result in an offset of the diagonal's continuation </em>
    </td>
    <td align="center" width="50%">
      <a href="">
        <img src="" width="250px" alt="">
      </a>
      <br>
      <em>Group 2 Example: Fragment on the y-axis is executed with a trille. So, in addition to low similarity regions, the diagonal is offset by the number of extra notes </em>
    </td>
  </tr>
</table>

#### Diagonal Finding:

The light blue lines indicate the diagonals found using:
- minimum length = 10
- gap tolerance = 5
- similarity threshold = 0.2

The green lines represent group2 intervals, which we show to demonstrate the aforementioned challenges of this group specifically and how it affects the results. The intersections of the green lines is where we would (ideally) want to find a diagonal.


![preview](./figures/mozart_var/mozart_var_diagonalsearch_group2annot_10_0-2_5.png)


- For group 0:
3 long diags with enough coverage 
however, another diagonal subset is included which will likely lead to an irrelevant grouping, (the 3 short diagonals at the bottom). 
It could be avoided by increasing the minimum length parameter, or for it to be later discarded later based on improved filtering approaches. 

- As for group 1, there are 5 diagonals we would have wanted to find, only 2 of which actually have diagonals. The trille example
The example with the trille will be impossible to get a proper diagonal for. Not only is the number of events different, which makes the diagonal non exact even if the endings would be the same. and the notes are different (it is not repetition of the same note) [this is mozart var group 2 - 1 and 2

### Interval Results

- interval_overlap_ratio = 0.85

[Download](./annotated_files/02_2024-08-02_Mozart_Var/results/10_0-2_5.zip)