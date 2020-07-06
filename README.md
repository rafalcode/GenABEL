GenABEL Project's last update was 2013
However, there's not too much in the way of gettingit approved for loading into R/3.5.0
offical respositories. Nevertheless the issue are farily easily surmountable:

```
Note: break used in wrong context: no loop is visible at PGC.R:67 
Note: break used in wrong context: no loop is visible at VIFGC.R:66 
Note: break used in wrong context: no loop is visible at VIFGC_ovdom.R:58 
```

Those line numbers only available if you have R_KEEP_PKG_SOURCE=yes 
exported as a environmental variable when you run R CMD INSTALL.

These are break but not with loops, rather within a function
so the guess is, they really should be returns or stops.

In any case, this fork corrects it so if you want to use it
all you need do is (devtools package must have been installed beforehand):

```
library(devtools)
install_github('rafalcode/GenABEL.data')
install_github('rafalcode/GenABEL')
```
