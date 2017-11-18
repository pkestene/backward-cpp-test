# purpose

Illustrate issue #82 of backward-cpp (https://github.com/bombela/backward-cpp/issues/82)

## get sources

git clone git@github.com:pkestene/backward-cpp-test.git
git submodule init
git submodule update

## build with backward-cpp (upstream version)

mkdir build_upstream
cd build_upstream
cmake -DUSE_BACKWARD_UPSTREAM=ON ..
make VERBOSE=1

it should failed to build

## build with backward-cpp (local version)

mkdir build_local
cd build_local
cmake -DUSE_BACKWARD_UPSTREAM=OFF ..
make VERBOSE=1

build should be successfull, notice the compile command line is different, because cmake macro add_backward is correctly expanded.

