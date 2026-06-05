# ResourcePool Model Comparison: Gemma 4 12b Qat vs Qwopus 3.5 9b Coder

This repository contains an HTML report comparing **Gemma 4 12b Qat** and **Qwopus 3.5 9b Coder** on their implementation of a thread-safe C++ `ResourcePool` class.

## Overview

The models were tasked with creating a modern C++ resource pool (C++17/20) that manages heavy resources using smart pointers. The core requirement was to ensure automatic resource return to the pool upon smart pointer destruction, adhering to strict RAII principles and thread-safety constraints.

### Key Technical Points
*   **Task:** Implement `ResourcePool` with `acquire()` returning a smart pointer (`std::unique_ptr` with custom deleter or `std::shared_ptr`).
*   **Constraints:** Thread-safe (`std::mutex`), no raw pointers in public interface, minimized lock scope.
*   **Analysis:** The report includes side-by-side code reviews, architectural analysis of the smart pointer choices, and full source code outputs.
*   **Performance:** Generation speed (tokens/sec) and total inference time are benchmarked.

## Hardware & Models

| Component | Specification |
| :--- | :--- |
| **CPU** | AMD Ryzen 7 7800X3D (8-Core) |
| **RAM** | 32 GB |
| **VRAM** | 16 GB |
| **Model 1** | `google/gemma-4-12b-qat` (Q4_0 quantization) |
| **Model 2** | `Jackrong/qwopus3.5-9b-coder` (Q8_0 quantization) |
