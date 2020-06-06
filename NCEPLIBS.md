# Build libraries for GSI from the NCEPLIBS repository

**It is recommend to follow instructions provided by UFS to build NCEPLIBS**

The following is to share our experiences on building only parts of NCEPLIBS to meet the GSI requirement.
*this method may avoid to compile NCEPLIBS-external if your system already have the following libraries installed: MPI zlib HDF5 NetCDF4 libpng Jasper*

### 1. Clone NCEPLIBS from Github
```
git clone -b ufs-v1.0.0 --recursive https://github.com/NOAA-EMC/NCEPLIBS
cd NCEPLIBS
```

### 2. Modify CMakeLists.txt
  Make sure the following 6 lines are commented out in the CMakeLists.txt
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

### 3. Build NCEPLIBS and install libraries
```
 mkdir build;  cd build
 cmake ..
 make -j8
 
 make install
```
### 4. make links
This is to remove version nubmers in the filename.

Assuming GSILIBS/ and NCEPLIBS/ are under the same parent directory.
```
cd build/install/lib
../../../../GSILIBS/linklibs
```

All done!

