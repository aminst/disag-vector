# Disaggregated and Heterogeneous Computing Platform for Graph Processing Course Project (Winter 2024)

## Cloning the Repo
```
git clone --recursive git@github.com:aminst/disag-vector.git
```

## Running the Code
First, please generate the makefile with cmake using this command:
```bash
cmake \
    -B build \
    -DFAISS_ENABLE_GPU=OFF \
    -DFAISS_ENABLE_PYTHON=OFF \
    -DCMAKE_BUILD_TYPE=Release \
    -DFAISS_OPT_LEVEL=avx2 \
    .
```
Build the benchmark executable:
```
make
```
Running the benchmark:
```
./bench_hnsw.sh
```
you can change the parameters M and efConstruction in the bench_hnsw.sh. It stores the benchmark results in the results directory.

## Project Group
Sairaj Voruganti & Amin Setayesh
