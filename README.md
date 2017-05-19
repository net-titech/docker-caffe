Caffe Build for Docker for Murata Laboratory's TitanX server. This allows reproducible environment using Caffe.

# How to Use
1. To build docker-caffe do a git clone then `cd Docker` folder and run `make all`
2. run `./run.sh` located at the root folder to launch caffe in Bash environment
3. Finally, simply type `jupyter notebook --allow-root --ip="*"` in the virtual environment to launch a jupyter notebook. You should be able to access the notebook from the host environment.

# Notes
* Feel free to modify `run.sh` as you see fit. The default parameters mounts a pre-defined Data Volume previously used by me.
* `/mnt/data/` contains ImageNet 2012's full training and test data (~500 GB)
* `caffe_models` data volume consists of some caffe models predownloaded from Caffe Model Zoo
* `caffe_examples` data volume consists of example scripts. Any changes made in this folder will be saved and reused in the next container instantiation. Please be wary when modifying previous person's work. If you wish to have your own personal copy, it is highly advisable to create your own data volume. Refer to Docker's documentation for further instruction or you can simply replace `caffe_examples` with `<yourname>_caffe_examples`. Docker will automatically copy existing files from the caffe image into this data volume.
* `caffe_data` data volume consists of caffe's data. Again, create your own data volume if you wish.
* Your host's home folder will be automatically mounted to `/home/<yourusername>/mnt` to prevent any conflict with your host's environment init files. Feel free to modify this as you see fit.
