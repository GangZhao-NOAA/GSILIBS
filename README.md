This repo is to temporarily provide bufrlib and wrfio lib for GSI at Github 

mkdir build; cd build

cmake -DBUILD_CORELIBS=ON ..

make -j8

The libraries will be under build/lib
