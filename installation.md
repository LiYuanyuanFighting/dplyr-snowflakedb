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

3. setup R following the [link](https://ahoyyangbai.wordpress.com/2013/08/24/setup-r-in-eclipse-on-mac-osx/)
to install R packages in R console, following this   
(install.packages(c("rj", "rj.gd"), repos="http://download.walware.de/rj-1.0", type="source"))  

4. When install rj and rj.gb packages in R console, meet problems:  
ld: library not found for -lomp   
Solve: 1st use 2 exporting commands mentioned in 2, 2nd download rj and rj.gd packages from WalWare(2.1 version), 
put in desktop, 3rd in terminal write: R CMD INSTALL --no-test-load rj_2.1.0-13.tar, then write   
R CMD INSTALL --no-test-load rj.gd_2.1.0-2.tar to install the 2 packages from desktop
