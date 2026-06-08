# DataTransSimple: Simple Data Transformation and Aggregation in R



`DataTransSimple` is a lightweight R package engineered to streamline data transformation and statistical normalization workflows. Built natively with R development tools (`devtools`), the package offers modular preprocessing tools specifically tailored for engineering features prior to statistical or regression modeling.

---

## 🚀 Key Features & Implemented Functions

The package contains seven foundational transformation and aggregation functions:

1. **Logarithmic Transformation (`log_transform`)**: Calculates the natural logarithm for mathematical normalization. *Includes automated guards against non-positive numbers ($x \le 0$)*.
2. **Box-Cox Transformation (`boxcox_transform`)**: Power transformation ($\lambda$) to stabilize variance and approximate normality across continuous variables.
3. **Min-Max Normalization (`minmax_normalization`)**: Rescales continuous vector values linearly down to a closed interval between 0 and 1.
4. **Z-Score Standardization (`zscore_transform`)**: Re-centers data distributions to have a mean of 0 and a standard deviation of 1.
5. **Polynomial Transformation (`polynomial_transform`)**: Generates an orthogonal basis matrix up to a user-defined degree for expanding non-linear structural terms.
6. **Weighted Aggregation (`weighted_aggregation`)**: Calculates matching weighted sums and weighted averages across arrays.
7. **Moving Average (`moving_average`)**: Computes a directional right-aligned moving average filter to smooth time-series or sequential datasets.

---

## 🛠️ Tech Stack & Requirements

The script dynamically manages package construction and relies on the following standard R libraries:
* **`devtools`**: Programmatic R package build system scaffolding.
* **`roxygen2`**: Inline namespace documentation and structural compilation.
* **`readxl`**: Excel file import engine (`.xls` and `.xlsx` support).
* **`stats`**: Native R numerical array computing and time-series filtering operations.

---

## 📦 Package Pipeline Architecture

The source script steps through a clean end-to-end package generation and verification pipeline:

### Step 1: Structural Scaffolding
Clears historical build versions, automatically sets up your project directory structure, and builds isolated `/R` and `/man` document repositories.

### Step 2: Meta-Specification (`DESCRIPTION` & `NAMESPACE`)
Writes package details, assigns a GPL-3 open-source license, sets dependencies, and builds the tracking definitions needed to export functions cleanly.

### Step 3: Deployment Testing & Execution
Loads data from a sample engineering dataset (`turbine_thrust.XLS`), validates column profiles, and processes the thrust variable (`y`) through error-handled execution tests using `tryCatch` blocks to guarantee runtime stability.

---

## 🏃‍♂️ How to Run the Pipeline

### 1. Prerequisites
Ensure you place your dataset named exactly **`turbine_thrust.XLS`** inside your working directory alongside the project script.

### 2. Execution
Open your R environment or RStudio, load the `.Rmd` or `.R` script, and execute the workspace blocks. The system will automatically build the package, install it to your local library, map the variables, and output an verification report:

```r
# Load and run the setup
library(readxl)
library(DataTransSimple)

# The package will compile and output validation tests like:
# Min-Max normalization
# Moving Averages (Window=3)
# Z-Score Standardization metrics
