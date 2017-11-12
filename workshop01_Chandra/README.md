# Chandra data processing 
This workshop is a brief introduction to the data processing from Chandra X-ray observatory.  
## Install HEASOFT 
Follow the manual here if you want to download from [NASA pages](https://heasarc.gsfc.nasa.gov/lheasoft/download.html).

Download source code from ftp://matuskocka.com/
user: `workshop` password: `chandra2017`
Follow the heasoft [install guide](https://heasarc.gsfc.nasa.gov/lheasoft/install.html).
```
      tar -xvzf heasoft-6.22.1src.tar.gz
      cd heasoft-6.22.1/BUILD_DIR/
      ./configure  > config.out 2>&1 &
      make > build.log 2>&1 &
      tail -f build.log
      make install > install.log 2>&1 &
```
Insert alias to heasoft to `.bashrc`
```
      HEADAS=/path/to/your/installed/heasoft-6.22.1/(PLATFORM)
      export HEADAS
      alias heainit=". $HEADAS/headas-init.sh"
```
## Install CIAO 
Go to CIAO [installation page](http://cxc.harvard.edu/ciao/download/) and hit button 'Standard Install with the base CALDB'

Do not forget to **run** smoke tests. 

### Some other tools
* Local copies of dfits/dtfits/fitsort for [Linux](http://astro.vigan.fr/tools/dfits_linux64.tar.gz)
* http://www.astropy.org/
* http://www.stsci.edu/institute/software_hardware/pyfits

### Get data 
From ftp://matuskocka.com/ get all_tycho.tar.gz *9.7G*. 

### Simple color image 
Unpack your data, enable heasoft and ciao. You can find more info [here](http://cxc.harvard.edu/ciao/threads/combine/).

Lets reproject 5 observations: 
```
reproject_obs 10093,10094,10095,10096,10097 merget1/
```
You can find [True color images manual here](http://cxc.harvard.edu/ciao/threads/true_color/). We are going to do similar thing. 
