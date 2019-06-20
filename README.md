# Clock synchronization over networks — Identifiability of the sawtooth model

This GitHub repository contains the code and explanations that complement the paper "Clock synchronization over networks — Identifiability of the sawtooth model" [[6]](#ourpaper).
### Pol del Aguila Pla [[1]](https://poldap.github.io/#/), Lissy Pellaco [[2]](https://www.kth.se/profile/pellaco), Satyam Dwivedi [[3]](https://www.researchgate.net/profile/Satyam_Dwivedi2), Peter Händel [[4]](https://www.kth.se/profile/ph/) and Joakim Jaldén [[5]](https://www.kth.se/profile/jalden/)

In this repository you will find the code used to implement the different estimation strategies in our paper [[6]](#ourpaper), i.e., the intuitive periodogram and correlation peaks (PCP) technique and the local and global grid search (LGS/GGS) procedures for the sawtooth model. Similiarly, you will also find the code used for their evaluation and the generation of the empirical results in [[6]](#ourpaper). Additionally, you can also find the code used to simulate an ideal physical system implementing the round-trip time (RTT) protocol described in Section II-A of our paper [[6]](#ourpaper), summarized here by [Fig.1](#Fig.1).

 <a id='Fig.1'></a>![RTT_measurement_scheme](/fig/RTT-measurement-scheme.png)

## Computation Environment
In order to run our code successfully and in a moderate time, you will need access to a powerful computer. For reference, all our experiments have been run on a computer equipped with [Intel(R) Xeon (R) CPU E5-2630 v4 @ 2.20GHz](https://ark.intel.com/content/www/us/en/ark/products/92981/intel-xeon-processor-e5-2630-v4-25m-cache-2-20-ghz.html) and 32 GB of RAM. In case you do not have access to a powerful CPU and to at least as much RAM, we recommend skipping the intensive-to-compute cells and we suggest to directly load the data to generate the plots from the `*.npz` files, as set by default in [empirical_results.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/empirical_results.ipynb). This will simply re-render the plots in the selected format, loading the results that we obtained. To run the code locally instead, in order to reproduce our results, change the corresponding flags in each computation cell to `True`, which will replace the `*.npz` files.


## Reading the code and our explanations
The simplest way to read through the annotated code is to open the relevant `*.ipynb` 'notebook' files through [nbviewer.jupyter.org](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/tree/master/). You can use [nbviewer.jupyter.org](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/tree/master/) from any modern browser, without any further installation requirements. Note that this option only allows you to visualize the notebooks, and it is not possible to execute the code or reproduce the results from the paper in this manner.

## Executing the code
If you would like to execute the code on your own computation environment and fully replicate our results, the software requirements are:
1. Python 3 (for reference, we used `python 3.5.2`), along with the packages `numpy`, `operator`, `numba`, `tabulate`, `matplotlib`,`plotly`, and `matplotlib2tikz`.
2. Jupyter (for reference, we used `jupyter 5.2.2`).

To execute our code, you will need to be familiar with Jupyter notebooks running Python code. For that, you can refer to any of the several freely available tutorials, like [this one](https://codingthesmartway.com/getting-started-with-jupyter-notebook-for-python/). After installation of the required packages, navigate to the folder where this repository has been cloned and execute Jupyter notebook to launch the Jupyter notebook server in that folder. Then, a simple click to any of the `*.ipynb` files listed in the Jupyter notebook website loads it on a new tab, where controls for running our code are available. 

In the following, we go through the different notebooks included and explain what each of them contains. **Note that you do not need to run the Jupyter notebooks in any specific order.** Each notebook automatically imports all the required dependencies. In particular, if you are interested in the numerical results, i.e., the plots in Section V of our paper [[6]](#ourpaper), we suggest to directly look at [empirical_results.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/empirical_results.ipynb). If you are interested in the set-up used to simulate a physical system of two nodes that operate following the protocol described in [Fig.1](#Fig.1) and Section II-A of [[6]](#ourpaper), see [Simulated nodes.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/simulated_nodes.ipynb)

1. [imports_and_library_of_basic_functions.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/imports_and_library_of_basic_functions.ipynb):
In this notebook we provide the basic imports and self-defined functions needed for the implementation of the different concepts and results considered in our paper [[6]](#ourpaper).
2. [estimation_strategies_with_examples.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/estimation_strategies_with_examples.ipynb):
In this notebook we implement our reference estimation strategies (see Section IV-B of our paper [[6]](#ourpaper)) and showcase them by simple examples.
3. [Cramer-Rao_and_Monte-Carlo.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/Cramer-Rao_and_Monte-Carlo.ipynb): 
In this notebook we implement 1) the computation of the CRLBs for an unwrapped model (see Section IV-A of our paper [[6]](#ourpaper)), and 2) the basic machinery to run Monte Carlo experiments with our proposed estimation approaches (see Section IV-B of our paper [[6]](#ourpaper) and [estimation_strategies_with_examples.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/estimation_strategies_with_examples.ipynb) for their implementation) with respect to the different parameters of interest in the clock synchronization and ranging problem. 
4. [empirical_results.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/empirical_results.ipynb): This notebook complements Section V of our paper [[6]](#ourpaper). Here, we implement the experiments that yield the numerical results we report in Section V and generate the figures shown there.
5. [simulated nodes.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/simulated_nodes.ipynb): 
In this notebook an ideal physical system is simulated according to the protocol described in [Fig.1](#Fig.1) and in Section II-A of [[6]](#ourpaper). 
    1. [real_parameters_for_simulated_nodes.ipynb](https://nbviewer.jupyter.org/github/poldap/clock_sync_and_range/blob/master/real_parameters_for_simulated_nodes.ipynb): In this notebook it is shown how the real parameters for the simulated nodes are computed. However, such real values lead to an unrealistic computation time, namely around three years. Therefore, we decided to run the simulation of the physical system with toy parameters instead.

## References
[[1]](https://poldap.github.io/#/): Pol del Aguila Pla's research website<br/>
[[2]](https://www.kth.se/profile/pellaco): Lissy Pellaco's research profile at KTH<br/>
[[3]](https://www.researchgate.net/profile/Satyam_Dwivedi2): Satyam Dwivedi's researchgate profile<br/>
[[4]](https://www.kth.se/profile/ph/): Peter Händel's research profile at KTH<br/>
[[5]](https://www.kth.se/profile/jalden/): Joakim Jaldén's research profile at KTH<br/>
<a id='ourpaper'></a>[[6]](http://arxiv.org/abs/1906.08208): Pol del Aguila Pla, Lissy Pellaco, Satyam Dwivedi, Peter Händel and Joakim Jaldén, "Clock synchronization over networks — Identifiability of the sawtooth model", Preprint, submitted to IEEE Transactions on Automatic Control, 2019.
