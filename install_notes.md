# Install Notes Specific to Harvard Workshop 2016
Software installed (and commands run) specific for the Harvard Workshop 2016. 

## ANVI'O (version 2.0.2)
Install instructions were followed from [ANVI'O WEBSITE] (http://merenlab.org/software/anvio/).

Dependencies:
* Prodigal (installed already)
* HMMER (installed already)
* sqlite (installed already)
* numpy (installed)
* GSL
```
wget ftp://ftp.gnu.org/gnu/gsl/gsl-latest.tar.gz
tar -xzvf gsl-latest.tar.gz
cd gsl-2.2.1
./configure && make && sudo make install
```
* Cython
```
sudo pip install cython
```
* hdf5
```
wget https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.8.17/src/hdf5-1.8.17.tar.bz2 
tar -jxvf hdf5-1.8.17.tar.bz2
cd hdf5-1.8.17 
./configure && make && sudo make install
```

To install ANVI'O:
```
sudo pip install anvio
```

Install tested with
```
anvi-self-test
```
 
## HyPhy (version 2.3.0)
Install instructions were followed from [HyPhy Github] (https://github.com/veg/hyphy). Installed pthreads option for multiprocessing. This still needs testing with data. 

Commands run:
```
wget https://github.com/veg/hyphy/archive/2.3.0-alpha.tar.gz
tar -xzvf 2.3.0-alpha.tar.gz
cd hyphy-2.3.0-alpha
cmake ./
make MP2
sudo make install
```

To launch:
```
HYPHYMP
```

## HIV Trace 
Install instructions were followed from [HIV Trace Github] (https://github.com/veg/hivtrace). This is currently not working.

Dependencies:
* tn93
```
wget https://github.com/veg/tn93/archive/v1.0.3.tar.gz
tar -xzvf v1.0.3.tar.gz
cd tn93-1.0.3
cmake [-DCMAKE_INSTALL_PREFIX=/install/path DEFAULT /usr/local/] ./
sudo make install
```
* pip3
```
sudo apt install python3-pip
```
* numpy
```
pip3 install numpy
```
* biopython
```
pip3 install biopython
```

To install HIV Trace (this fails):`
```
pip3 install https://github.com/veg/hivtrace/archive/0.2.0.tar.gz --process-dependency-links
```
