# Live Repetition Counting

## Requirements
Python 2.7.7+  

##### Python modules  
* theano 0.8.1  
* h5py  
* tornado  
* nose
* opencv-python

#### Troubleshooting
* When installing theano, tornado, nose if you come across the error that a package is already installed use the `--ignore-installed` flag e.g. `pip install --ignore-installed theano`.
* To install the specific version of theano, please run `pip install theano==0.8.1`.

## To run live repetition counting
Weights can be found [at this link](https://drive.google.com/drive/folders/16ePm6wrQ7DtBKpMEzFfYCKwR8z0Kyfp_?usp=sharing). Save the latest epoch (200) as `weights.save` in the `live_count` directory.  
To open the camera and do exercises in real-time, run `python live_rep.py`.  
To use an existing video file, run `python live_rep.py -i <videofile>`.  

## To train the model
* Train model by running `python2.7 rep_train_main.py` in the `trainNet` directory. Please create empty directory `weights` in root directory of the repository before starting.

## Data
Please find the data [at this link](https://drive.google.com/drive/folders/1rIpNklYtOh1l6HWvtakMvCndkMB7M_kI?usp=sharing). This is the simulated data generated by the Matlab scripts in the `syn_data` directory. Please have the `out` directory in the root directory of the repository. You only need the `h5` directory for training the data, but we have included the `mat` unprocessed data for reference.

## Major changes from original implementation
* Input data is in files with extension `.h5` not `.gzip.h5`.
* Input to CNN is of type `theano.tensor.tensor4` not `theano.tensor.matrix`.
* Input and output directories of data, specifically train_dir, valid_dir, weights_dir in `rep_train_main.py`.


## Original Implementation Citation
Theano implementation by the authors of the original work can be found [here](https://github.com/tomrunia/DeepRepICCV2015).

```
@inproceedings{levy2015live,
  title={Live Repetition Counting},
  author={Levy, Ofir and Wolf, Lior},
  booktitle={Proceedings of the IEEE International Conference on Computer Vision},
  pages={3020--3028},
  year={2015}
}
```