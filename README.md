# ESN-CLVs

ESN-CLVs is a python tool written in numpy and based on the Echo State Network (ESN). It trains M independent ESNs with data from chaotic attractors, which are independently initialized. Then it computes the Lyapunov exponents and the Covariant Lyapunov Vectors of the surrogate model. This implemention includes four prototypical chaotic systems for testing, and it is straightforward to implement additional ones in the Functions.ipynb notebook. Please refer to [1] for the preprint of this work.

## Requirements
The code requirements are:
- numpy
- matplotlib
- h5py
- scipy
- skopt
- mpl_toolkits

All can be found in requirements.txt, which can be installed via:

```pip install -r requirements.txt```

## Datasets
A sample data are provided in lorenz63 folder. The target data are in target_data_N_3/CLV_results/ESN_target_CLV_dt_0.005_noise_0_ens_0.h5. The model data are saved in lorenz63/data_N_100_dim_3/CLV_results. Here N_100 implies a reservoir of size 100. 

## Usage
To get a feel for how the code works, you can run it directly in a Jupyter Notebook. First, make sure you have Jupyter installed on your system. If you don't already have it installed, you can install it by running pip install jupyter in a terminal window.

Once Jupyter is installed, you can open the ESN_Validation.ipynb notebook by running the following command in a terminal window:

```jupyter notebook ESN_Validation.ipynb```

This will launch the Jupyter Notebook server and open the ESN_Validation.ipynb notebook in a web browser window. You can then execute the code cells in the notebook to see how it works.

The code in the ESN_Validation.ipynb notebook performs the following tasks:

1. Generates data from the Lorenz 63 system with a small amount of noise added.
2. Trains and validates the networks using Recycle Validation Chaotic (RVC; see [2] for more details).
3. Runs the code in autonomous close-loop mode to produce a test dataset.
4. Runs on unseen data to produce a stored dataset that is compared with the target.


## Acknowledgments
This is a joint work with Luca Magri. The core ESN was implemented by Alberto Racca and the code can be found in https://github.com/alberacca/Echo-State-Networks based on [2].

## Literature
1. Margazoglou, G. and Magri, L., 2023. Stability analysis of chaotic systems from data. Nonlinear Dynamics, 111(9), pp.8799-8819. https://doi.org/10.1007/s11071-023-08285-1
2. Racca, A. and Magri, L., 2021. Robust Optimization and Validation of Echo State Networks for learning chaotic dynamics. Neural Networks, 142, pp.252-268. https://doi.org/10.1016/j.neunet.2021.05.004

The implementation of CLVs follows:

3. Ginelli, F., Poggi, P., Turchi, A., Chaté, H., Livi, R. and Politi, A., 2007. Characterizing dynamics with covariant Lyapunov vectors. Physical review letters, 99(13), p.130601. https://doi.org/10.1103/PhysRevLett.99.130601

## Contact info
For any questions or to get in contact with us, please refer to the following:

    Email: g.margazoglou@imperial.ac.uk; l.magri@imperial.ac.uk    
    Website: https://magrilab.ae.ic.ac.uk/

