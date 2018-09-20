GenABEL Project's last update was 2013
Howeverm there; not too much int he way of clearing it for loading into R/3.5.0
just the little matter of

```
Note: break used in wrong context: no loop is visible at PGC.R:67 
Note: break used in wrong context: no loop is visible at VIFGC.R:66 
Note: break used in wrong context: no loop is visible at VIFGC_ovdom.R:58 
```

Those line number only available if you have R_KEEP_PKG_SOURCE=yes 
exported as a environmental variable when you run R CMD INSTALL.

These are break but not with loops, rather within a function
so the guess is, they really should be returns or stops.
