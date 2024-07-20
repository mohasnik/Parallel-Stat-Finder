# Parallel Stat Finder

## Overview

This repository contains the parallel implementation of finding the standard deviation of a very large array using different parallel computing techniques, including OpenMP, POSIX threads, and SIMD (Single Instruction, Multiple Data). The project demonstrates how parallelism can significantly improve the performance of basic algorithms.

## Table of Contents

1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
3. [Implementation Details](#implementation-details)
   - [OpenMP](#openmp)
   - [POSIX](#posix)
   - [SIMD](#simd)
4. [Results](#results)
5. [Usage](#usage)
6. [License](#license)

## Introduction

This project demonstrates the implementation of a parallel algorithm to find the minimum value in a large array. The implementation uses three different parallel computing techniques: OpenMP, POSIX threads, and SIMD instructions. Each technique showcases the performance improvements that can be achieved through parallelism.

## Project Structure

The project is organized into three main directories, each containing the implementation of the algorithm using a different parallel computing technique:

- `OpenMP/`: Contains the implementation using OpenMP.
- `POSIX/`: Contains the implementation using POSIX threads.
- `SIMD/`: Contains the implementation using SIMD instructions.

Each directory contains a `main.cpp` file with the implementation.

## Implementation Details

### OpenMP

The OpenMP implementation utilizes the OpenMP library to parallelize the standard deviation calculation across multiple CPU cores. OpenMP provides an easy way to parallelize loops and manage threads.

**File:** `OpenMP/main.cpp`

### POSIX

The Pthread implementation uses POSIX threads to manually manage thread creation, synchronization, and workload distribution. This approach offers fine-grained control over parallel execution.

**File:** `POSIX/main.cpp`

### SIMD

The SIMD implementation uses SIMD instructions to process multiple data points simultaneously, leveraging the parallelism within a single CPU core. This method is efficient for operations that can be vectorized.

**File:** `SIMD/main.cpp`

## Results

The performance of each implementation is measured by the execution time and the speedup achieved compared to the serial version. The results are printed to the console, showing the serial and parallel run times, speedup, and the standard deviation found by each method.

## Usage

To compile and run the programs, navigate to the respective directory and use the following commands:

### OpenMP

```sh
g++ -fopenmp -o ompStatFinder main.cpp
./ompStatFinder
```

### POSIX 

```sh
g++ -pthread -o POSIXStatFinder main.cpp
./POSIXStatFinder
```

### SIMD 

```sh
g++ -msse -o SIMDStatFinder main.cpp -march=native
./SIMDStatFinder
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
