#/***************************************************************************
# *
# *  Copyright (C) Codeplay Software Ltd.
# *
# *  Licensed under the Apache License, Version 2.0 (the "License");
# *  you may not use this file except in compliance with the License.
# *  You may obtain a copy of the License at
# *
# *      http://www.apache.org/licenses/LICENSE-2.0
# *
# *  Unless required by applicable law or agreed to in writing, software
# *  distributed under the License is distributed on an "AS IS" BASIS,
# *  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# *  See the License for the specific language governing permissions and
# *  limitations under the License.
# *
# *  Codeplay's SYCL-For-CUDA-Examples
# *
# *  Makefile
# *
# *  Description:
# *    Makefile for CUDA interop
# **************************************************************************/

CUDACXX=clang++

CUDA_ROOT_DIR=/usr/local/cuda/

CUDAFLAGS=--cuda-gpu-arch=sm_86

CXXFLAGS=-std=c++17 ${CUDAFLAGS} -I${SYCL_ROOT_DIR}/include/ -I${SYCL_ROOT_DIR}/include/sycl/ -Wno-linker-warnings  -g

LIBS=-L${SYCL_ROOT_DIR}/lib -lOpenCL -lsycl -L${CUDA_ROOT_DIR}/lib64 -lcudart

default: mm_cuda

mm_cuda: mm_cuda.cu
	${CUDACXX} ${CXXFLAGS} $< ${LIBS} -o $@

clean:
	rm mm_cuda
 
