# Install Notes Specific to Harvard Workshop 2016
Software installed (and commands run) specific for the Harvard Workshop 2016. 

## ANVI'O
Install instructions were followed from [ANVI'O WEBSITE] (http://merenlab.org/software/anvio/).

Dependencies:
*Prodigal (installed already)
*HMMER (installed already)
*sqlite (installed already)
*numpy (installed)
*GSL
*Cython
*hdf5

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
