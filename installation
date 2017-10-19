https://github.com/snowflakedb/dplyr-snowflakedb/wiki/Configuring-R-rJava-RJDBC-on-Mac-OS-X
1. change   
curl -#ROL https://cran.rstudio.com/bin/macosx/R-3.2.3.pkg
open R-3.2.3.pkg. 
to  
curl -#ROL https://cran.rstudio.com/bin/macosx/R-3.4.1.pkg
open R-3.4.1.pkg

2. Since OpenMP is not supported on MacOS X, follow the link:  
http://thecoatlessprofessor.com/programming/openmp-in-r-on-os-x/#after-3-4-0. 
Then appears another error:  
ld: library not found for -lomp
Then I tried with it and found:

$ export LD_LIBRARY_PATH=/usr/local/opt/llvm/lib:$LD_LIBRARY_PATH
$ export LIBRARY_PATH=/usr/local/opt/llvm/lib:$LIBRARY_PATH
before running R CMD INSTALL works. 
From this [link](https://github.com/peterwittek/somoclu/issues/69). 

