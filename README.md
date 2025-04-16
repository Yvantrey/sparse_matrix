# Sparse Matrix Implementation

## Overview
This repository contains an implementation of a sparse matrix data structure in JavaScript. The implementation is designed to efficiently handle matrices where most elements are zero by only storing non-zero elements in memory. This approach optimizes both memory usage and computational efficiency for operations like addition, subtraction, and matrix multiplication.

## File Structure
- `./dsa/sparse_matrix/code/src/main.js` - Main program/file implementing the SparseMatrix class and operations.
- `./dsa/sparse_matrix/sample_inputs/` - Directory containing example matrix files.
- `./dsa/sparse_matrix/sample_inputs/outputs.txt` - Output file where results are stored & modified overtime.

## Features
- Efficient sparse matrix representation using a Map data structure
- Matrix operations: addition, subtraction, and multiplication
- File I/O for loading matrix data and saving results
- Comprehensive error handling

## The SparseMatrix Class
The core of the implementation is the `SparseMatrix` class which includes:

### Data Structure
The sparse matrix uses a JavaScript Map where:
- Keys are strings in the format `"row,col"` representing element coordinates
- Values are the non-zero numerical values at those coordinates


## Matrix Format
Input and output matrices follow this format:
```
rows=<number_of_rows>
cols=<number_of_columns>
(<row_index>, <column_index>, <value>)
(<row_index>, <column_index>, <value>)
...
```

Where:
- First line specifies the number of rows
- Second line specifies the number of columns
- Subsequent lines list non-zero elements as `(row, column, value)` triplets

## These are the main Matrix Operations

### Addition
- Requires matrices of the same dimensions
- Adds corresponding elements
- Time complexity: O(n+m) where n and m are the number of non-zero elements

### Subtraction
- Requires matrices of the same dimensions
- Subtracts corresponding elements
- Time complexity: O(n+m) where n and m are the number of non-zero elements

### Multiplication
- Requires the number of columns in the first matrix to equal the number of rows in the second
- Follows standard matrix multiplication algorithm
- Optimized to only consider non-zero elements
- Time complexity: O(n*p*q) where:
  - n = non-zero elements in first matrix
  - p = average non-zero elements per row in first matrix
  - q = average non-zero elements per column in second matrix

## How to Run

1. Navigate to the directory containing by writting `cd /dsa/sparse_matrix/code/src/main.js`; This is where my main code is placed 

2. Run the program using Node.js:
   ```
   node main.js
   ```
3. Follow the interactive prompts:
   - Select first matrix from the list (1)
   - Select second matrix from the list (2)
   - Choose an operation (addition, subtraction, or multiplication)
4. The result will be displayed and automatically saved to `/dsa/sparse_matrix/sample_inputs/` as `outputs.txt`

## Examples

### Sample Input Files

Example of my `matrix1.txt`:
```
rows=5
cols=5
(0, 0, 5)
(1, 1, 8)
(2, 2, 3)
(3, 1, 6)
(4, 4, 9)
```

Example of my `matrix2.txt`:
```
rows=5
cols=5
(0, 4, 7)
(1, 3, 2)
(4, 0, 1)
```

### Take a look of My Subtraction
```
SparseMatrix(5x5):
5 0 0 0 -7
0 8 0 -2 0
0 0 3 0 0
0 6 0 0 0
-1 0 0 0 9
```

### Error Handling
The implementation includes robust error handling for:
- Invalid file formats
- File not found errors
- Matrix dimension mismatches for operations
- Out-of-bounds indices

