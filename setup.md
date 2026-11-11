# Laboratory Setup

This guide explains how to set up a Python virtual environment for the **Digital Image Processing (CIMIT-5124)** laboratories using **Visual Studio Code (VS Code)** and **Jupyter notebooks**.

## 1. Install the prerequisites

Install the following software:

- [Python](https://www.python.org/downloads/) (version 3.10 or later)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Git](https://git-scm.com/downloads/)

Then install the **Python** and **Jupyter** extensions in VS Code:

1. Open VS Code and press `Ctrl + Shift + X` to open **Extensions**.
2. Search for **Python** (publisher: Microsoft) and click **Install**.
3. Search for **Jupyter** (publisher: Microsoft) and click **Install**.

## 2. Clone the repository

Open a terminal and run:

```bash
git clone https://github.com/mohaclasses/DIP_CIMIT_5124.git
cd DIP_CIMIT_5124
code .
```

> If `code .` is not recognized, open VS Code and select **File → Open Folder**, then choose `DIP_CIMIT_5124`.

## 3. Create and activate a virtual environment

Open the terminal in VS Code (**Terminal → New Terminal**).

**Windows (PowerShell):**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**Linux/macOS:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

> On Windows, if PowerShell blocks activation, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` in that terminal, then retry the activation command.

## 4. Install the required packages

With the virtual environment activated, run:

```bash
python -m pip install numpy matplotlib scipy pillow opencv-python scikit-image ipykernel
```

## 5. Select the Jupyter kernel in VS Code

1. Open or create a `.ipynb` notebook in the repository.
2. Click **Select Kernel** in the upper-right corner.
3. Choose **Python Environments** and select the Python interpreter inside `.venv`.

## 6. Verify the installation

Run the following code in a notebook cell:

```python
import numpy as np
import matplotlib.pyplot as plt

image = np.random.rand(100, 100)
plt.imshow(image, cmap="gray")
plt.axis("off")
plt.show()
```

If an image appears without errors, the setup is complete.

> **Note:** Use the `.venv` kernel for every laboratory notebook. Add `.venv/` to `.gitignore` to avoid committing the virtual environment.