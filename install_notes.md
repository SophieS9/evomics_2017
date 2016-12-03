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

## HIV-TRACE 
Install instructions were followed from [HIV Trace Github] (https://github.com/veg/hivtrace).

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

To install HIV-TRACE:
```
pip3 install https://github.com/veg/hivtrace/archive/0.2.0.tar.gz --process-dependency-links
```

## Jupyter Configuration for QIIME Workshop
Needed to set up the Jupyter configuration to allow the jupyter notebook to be viewed externally.

Whilst logged in as genomics, created the configuration file:
```
jupyter notebook --generate-config
```

Then edited the IP address lines to:
```
c.NotebookApp.ip='*'
```

## GATB (version 1.171)
Install instructions were followed from the [GATB Github] (https://github.com/GATB/gatb-minia-pipeline)

Dependencies:
```
sudo pip install mathstats
sudo pip install pysam==0.8.3
sudo pip install pyfasta
```

To install GATB:
```
wget http://gatb-pipeline.gforge.inria.fr/versions/bin/gatb-pipeline-1.171.tar.gz 
tar -xzvf gatb-pipeline-1.171.tar.gz
```
And then need to copy all of the directories and the binary to /usr/bin:
```
sudo cp gatb /usr/bin
sudo cp -r bloocoo/ /usr/bin
sudo cp -r BEEST/ /usr/bin
sudo cp -r tools/ /usr/bin
sudo cp -r minia/ /usr/bin
```

Finally whilst logged in as genomics:
```
su master
sudo pip install networkx
```

##Updating tbl2asn (for PROKKA)
Downloaded latest version, unpackaged, renamed and moved to /usr/bin/.
```
wget ftp://ftp.ncbi.nih.gov/toolbox/ncbi_tools/converters/by_program/tbl2asn/linux64.tbl2asn.gz
gunzip linux64.tbl2asn.gz
mv linux64.tbl2asn tbl2asn
sudo chmod +x tbl2asn
sudo mv tbl2asn /usr/bin/
```

##SRA toolkit (version 2.8.0)
Downloaded binaries for latest version, unpackaged and copied to /usr/bin/.
```
wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/2.8.0/sratoolkit.2.8.0-ubuntu64.tar.gz
tar -xzvf sratoolkit.2.8.0-ubuntu64.tar.gz
cd sratoolkit.2.8.0-ubuntu64
sudo cp bin/* /usr/bin/
```

##PILON (version 1.2.0)
Downloaded latest jar file and copied to /usr/bin/.
```
wget https://github.com/broadinstitute/pilon/releases/download/v1.20/pilon-1.20.jar 
sudo cp pilon-1.20.jar /usr/bin
```

##VCFannotator 
Downloaded, unpackaged and moved executable and dependencies to /usr/bin/.
```
wget https://sourceforge.net/projects/vcfannotator/files/vcfannotator_r2013-10-13.tgz/download
tar -xzvf download
cd vcfannotator_r2013-10-13
sudo cp VCF_annotator.pl /usr/bin/
sudo cp -r PerlLib /usr/bin
sudo cp Util/* /usr/bin
```

##Reducevcf (version 12)
Downloaded, unpackaced and moved jar files to /usr/bin.
```
wget http://www.genomeview.org/jenkins/reducevcf-nightly/reducevcf-12.zip
unzip reducevcf-12.zip
sudo mv ajt-2.10.jar /usr/bin/
sudo mv ark-43.jar /usr/bin/
sudo mv scala-library.jar /usr/bin/
sudo mv reducevcf.jar /usr/bin/
```
