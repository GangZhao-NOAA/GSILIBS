# Build libraries for GSI from the NCEPLIBS repository

** NOTE ** It is recommend to follow the instructions provided by UFS to build NCEPLIBS

The following is to share our experience on building only part of NCEPLIBS to satisfy the GSI requirement.
Using this method, these  is no need to compile NCEPLIBS-external

1.
```
git clone -b ufs-v1.0.0 --recursive https://github.com/NOAA-EMC/NCEPLIBS
cd NCEPLIBS
```
2. Modify CMakeLists.txt
  Make sure the following 6 lines are commented out 
```
#add_subdirectory(NCEPLIBS-bufr)
...
#add_subdirectory(NCEPLIBS-landsfcutil)
....
#add_subdirectory(NCEPLIBS-grib_util)
#add_subdirectory(NCEPLIBS-prod_util)
#add_subdirectory(UFS_UTILS)
#add_subdirectory(NCEPLIBS-post)
```
3.
```
 mkdir build;  cd build
 cmake ..
 make -j8
```
4. 
`make install`

5. 
```
cd build/install/lib
../../../../../GSILIBS/linklibs
```

All done!
```
