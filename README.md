# Math Problem Set Generator for Kids

An easy-to-use, dynamic R Markdown tool designed to generate clean, printable math worksheets for elementary students. Whether you need focused practice on a single operation or a comprehensive review, you can instantly customize a problem set to suit any learning level.

---

## 🚀 Features

* **Dynamic Operations:** Choose from **Addition**, **Subtraction**, **Multiplication**, **Division**, or a shuffled **Mixture** of problem sets.
* **Highly Parameterized:** Adjust digit thresholds, problem counts, and operation types effortlessly.
* **Kid-Friendly Layouts:** Smart rendering automatically stacks multi-digit arithmetic vertically, while formatting division cleanly as horizontal equations ($20 \div 5 = \text{\_\_\_}$).
* **Print Ready:** Includes an elegant right-aligned Name/Date header block and splits the presentation into a dual-column layout maximizing paper workspace.
* **No Negative Answers:** Built-in validation limits subtraction configurations so young learners don't run into negative results.
* **Perfect Integer Division:** Generates quotients without decimal remainders, keeping division approachable.

---

## 🛠️ Repository Structure

* `Math.Rmd` — The core logic, parameter definitions, and template engine framework.
* `Math.Rnw` — Minimalist header injection script handling advanced accessible document wrappers (`\AccTool`) and layout settings.

---

## ⚙️ Configuration & Customization

Open `Math.Rmd` and locate the configuration parameters near the top of the file to configure your desired outputs:

```r
# ---- CONFIGURATION ----
num_problems  <- 12     # Total number of questions to generate
max_digit     <- 99     # Ceiling cap threshold for arithmetic values
min_digit     <- 10     # Floor base threshold for arithmetic values
type_problems <- "mix"  # Options: "add", "subtract", "multiply", "divide", "mix"
# -----------------------
```

#### Supported Operation Rules:

| **Parameter Value** | **Behavior** | **Layout Style** |
| :--- | :--- | :--- |
| `"add"` | Multi-digit addition arrays | Vertical Grid Stack |
| `"subtract"` | Multi-digit bounded subtraction arrays | Vertical Grid Stack |
| `"multiply"` | Standard multiplication fact exercises | Vertical Grid Stack |
| `"divide"` | Exact integer division configurations | Horizontal Vector Equation |
| `"mix"` | Shuffled compilation of addition & subtraction elements | Adaptive Layouts |

## 📦 Getting Started

#### Prerequisites
Make sure you have an environment containing an R distribution along with a working LaTeX installation (like `TinyTeX`):

```r
install.packages(c("rmarkdown", "knitr", "dplyr"))
tinytex::install_tinytex() # If you don't have a LaTeX system installed
```

#### Execution
1. Open this project directory inside your console/RStudio instance.
2. Adjust your variables inside the `Math.Rmd` setup configuration block.
3. Hit the Knit button in RStudio or trigger generation via the terminal console:
```r
rmarkdown::render("Math.Rmd")
```

The rendering engine will output a beautifully typeset, printable Math.pdf math sheet within seconds!


## 📝 License

This project is open source and available under the [MIT License](./LICENSE).