# 📊 Deriving the Input-Output Table (IOT) from the Supply and Use Table (SUT)

This project aims to derive the **Input-Output Table (IOT)** from the **Supply and Use Table (SUT)**. The procedure is based on interindustry economic models and can be used for macroeconomic analysis, general equilibrium modeling, and industrial policy design.

## 🧠 Theoretical Background

There are two main approaches to deriving the IOT from the SUT:

1. **Model B: Product-by-Product**, based on the **Industry Technology Assumption (ITA)**
2. **Model D: Industry-by-Industry**, based on the **Commodity Sales Structure Assumption (CSSA)**

This notebook implements **Model B**.

## 📁 Data Used

Data is read from an Excel file with two main sheets:

### 1. Supply Table (`make_tbl_for_sym`)
- \\( V^T \\): Transposed supply matrix (products by industries, \\(109 \\times 100\\))
- \\( g^T \\): Total supply of each product (row sums)
- \\( x \\): Gross output of products
- \\( m \\): Imports
- \\( q \\): Gross output at market prices

### 2. Use Table (`use_tbl_for_sym`)
- \\( U_d \\): Intermediate consumption of products by industries
- \\( Y_d \\): Final demand matrix
- \\( W \\): Value added by industry
- \\( w \\): Total value added
- \\( y \\): Total final demand

## 🧮 Steps for Constructing the Input-Output Table

### 1. Compute the Industry Technology Matrix \\( T \\)

$$
T = V^T \\cdot \\text{diag}(g^T)^{-1}
$$

### 2. Compute Intermediate Demand Matrix \\( Z \\)

$$
Z = T \\cdot U_d
$$

### 3. Compute Final Demand Vector \\( f \\)

$$
f = T \\cdot Y_d
$$

### 4. Compute the Technical Coefficients Matrix \\( A \\)

$$
A = Z \\cdot \\text{diag}(x)^{-1}
$$

### 5. Compute the Leontief Inverse Matrix \\( L \\)

$$
L = (I - A)^{-1}
$$

where \\( I \\) is the identity matrix.

## ✅ Outputs

- Input-Output table (\\( Z \\))
- Final demand vector (\\( f \\))
- Technical coefficients matrix (\\( A \\))
- Leontief inverse matrix (\\( L \\))

## 📚 Theoretical References

- Eurostat Manual of Supply, Use and Input-Output Tables
- United Nations SNA 2008
- Ten Raa, Thijs (2005). *The Economics of Input-Output Analysis*



