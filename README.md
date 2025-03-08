# CUDA
This project compares the performance of sequential vs. parallel (CUDA + Thrust) approaches in counting purple pixels in an image. By leveraging GPU parallel processing, we demonstrate a significant speedup over traditional CPU-based methods. Results highlight the efficiency of CUDA in accelerating image processing tasks.

Overview
This project compares the performance of sequential and parallel (CUDA + Thrust) approaches for counting purple pixels in an image. The goal is to demonstrate the efficiency gains achieved by GPU parallelization over traditional CPU-based methods in image processing tasks.

Technologies Used
C++ for core implementation
CUDA & Thrust Library for parallel execution
Chrono Library for performance measurement

Project Structure
main.cpp: Implementation of the sequential and parallel approaches
cuda_code.cu: CUDA-specific implementation using Thrust
results/: Contains execution time logs and performance comparisons
docs/: Project documentation

Methodology
1 - Sequential Approach
Generates a 1000x1000 pixel image with random RGB values
Iterates through the matrix to count purple pixels (r > 150, g < 50, b > 150)
Measures execution time
2 - Parallel Approach (CUDA + Thrust)
Copies image data to GPU memory
Uses Thrust to apply a functor that checks for purple pixels
Utilizes thrust::transform_reduce to count pixels in parallel
Measures execution time

Performance Comparison
Method	Execution Time (µs)	Purple Pixels Count
Sequential (CPU)	18,416 µs	33,065
Parallel (CUDA)	1,758 µs	33,065
Result: Parallel execution is ~10x faster than sequential processing!

How to Run
Clone this repository:
bash

git clone https://github.com/yourusername/computer-networks-project.git
cd computer-networks-project
Compile and run the CUDA code:
bash

nvcc cuda_code.cu -o cuda_code
./cuda_code
📖 Key Takeaways
Parallel computing (CUDA) significantly reduces execution time
GPU acceleration is ideal for large-scale image processing tasks
Thrust simplifies parallel computation compared to raw CUDA kernels
