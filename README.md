[![DOI](https://zenodo.org/badge/68692395.svg)](https://zenodo.org/badge/latestdoi/68692395)

# Benchmark for the FVCA8 Conference

## :warning: News (update on January 2, 2017)

#### Small corrections on the LaTeX Template

A new version of the LaTeX has been released [ZIP archive](benchmark_FVCA8_template.zip)

  * Few style corrections to improve the readability of the tables : the only modified LaTeX file is  `macros.tex` 
  * **Lid driven cavity tests:** Correction of a typo concerning the suggested abscissas where the mid-line *vertical* velocity `v` should be reported. The corresponding `data/*.dat` files were updated

|Old values | New values |
|:---------:|:----------:|
|~~0.0~~    |   0.0      |
|~~0.0625~~ |   0.0703   |
|~~0.1016~~ |   0.0938   |
|~~0.2813~~ |   0.2266   |
|~~0.5~~    |   0.5      |
|~~0.7344~~ |   0.8594   |
|~~0.9531~~ |   0.9453   |
|~~0.9688~~ |   0.9609   |
|~~1.0~~    |   1.0      |

   **Nota bene:** The ordinates where the mid-line *horizontal* velocity `u` are unchanged


## News (update on December 4, 2016)


#### LaTeX Template

 The template for preparing your benchmark contribution is now available in the [ZIP archive](benchmark_FVCA8_template.zip).  Instructions are given in the [PDF Userguide](benchmark_FVCA8_userguide.pdf).
 
#### Important informations

 * **Extended Deadline:**  January 31, 2017.

 * Due to the maximum number of allowed pages you may not be able to include all your results in the final PDF version of the proceedings. In this case, you will need to comment out some lines in the source LaTeX template.
 
  However, you are kindly invited to send **all the plain text files containing your results** to the organisers. They could be very useful to perform comparisons between all the contributions. 
  
 * Templates for all the results files (for any possible test case in the benchmark) ar provided in the subdirectory `data` in the archive. Please do not change the names of the files, nor their format. They should look as follows
 
    
        | mesh | errgu | ordgu | erru | ordu | errp | ordp | errdivu | orddivu | nuu | npu | nnzu | nnzp | nnzup |
        |    1 |       |       |      |      |      |      |         |         |     |     |      |      |       |
        |    2 |       |       |      |      |      |      |         |         |     |     |      |      |       |
        |    3 |       |       |      |      |      |      |         |         |     |     |      |      |       |
        |    4 |       |       |      |      |      |      |         |         |     |     |      |      |       |
        |    5 |       |       |      |      |      |      |         |         |     |     |      |      |       |

 with your results in each cell or a `NaN` keyword if the data is not avaible.
 
 You can change the order of the columns (but they should all be present in the file with the correct name). You can also remove or add some rows.


 * In case of any problem with those instructions, in particular with the format imposed for the result `.dat` files, please contact the organisers.
 




## News (update on October 28, 2016)

 * Some people have experienced problems with some of the 3D meshes due to the presence of unexpected `EOL`. The files have been corrected now
 * We now also provide the 3D meshes in the GMSH format

## Presentation

This benchmark aims at comparing the accuracy, robustness, complexity of modern finite volume methods on unstructured grids in the context of viscous incompressible flows computations (Stokes and/or Navier-Stokes equations).

It is proposed in the occasion of the [Eighth Conference on Finite Volumes for Complex Applications - FVCA8](https://indico.math.cnrs.fr/event/1299/) to be held in Lille (France) from June 12th to June 16th 2017.

## Definition of the benchmark

All the necessary informations on the proposed test cases and the expected outputs are given in the [PDF file](Benchmark.pdf)

The 2D and 3D meshes are available in the [Meshes folder](Meshes). The formats of the mesh files are described in the `README.md`.

You can download the whole repository by clicking on the green button **Clone or download** above and then on **Download ZIP** (or you can `git clone` the repository if you are using git)

## Contributions

The contributions to the benchmark will be published, after reviewing, in [Springer proceedings in Mathematics and Statistics](http://www.springer.com/series/10533).

## Contacts

Any people who whishes to participate is strongly encouraged to contact [the organizers](mailto:fvca8-benchmark@univ-lille1.fr)

