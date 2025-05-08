## 1. System Update

Start by updating your system to install the latest package versions:

```bash
sudo apt update && sudo apt upgrade
```

---

## 2. Install Basic Dependencies

Install essential development tools and libraries:

```bash
sudo apt install build-essential cmake git curl wget unzip zlib1g-dev libglu1-mesa libxi-dev libxmu-dev libpng-dev libfreetype6-dev default-jre
```

---

## 3. Software Installation

### 3.1. Open Babel (Molecular Format Conversion)

Install via APT:

```bash
sudo apt install openbabel
obabel -V  # Verify installation
```

---

### 3.2. AutoDock Vina (Docking Engine)

#### Method 1: Download Precompiled Binary

1. Download the appropriate version from the [AutoDock Vina GitHub Releases](https://github.com/ccsb-scripps/AutoDock-Vina/releases).
2. Run the binary:

```bash
./vina_<version>_<os>_<arch> --help
```

#### Method 2: Install via pip

```bash
pip install -U numpy vina
```

#### Method 3: Install in a Conda Environment

1. Download and install [Anaconda](https://docs.continuum.io/anaconda/install) or [Miniconda](https://conda.pydata.org/miniconda.html).

2. Create a dedicated environment:

```bash
conda create -n vina python=3 -y
conda activate vina
conda config --env --add channels conda-forge
```

3. Install dependencies:

```bash
conda install -c conda-forge numpy swig boost-cpp libboost sphinx sphinx_rtd_theme
pip install vina
```

#### Method 4: Build from Source (Not Recommended)

**Step 1: Install Compiler**

```bash
sudo apt install build-essential
```

**Step 2: Install Boost and SWIG**

```bash
sudo apt install libboost-all-dev swig
```

**Step 3: Clone and Build Source**

```bash
git clone https://github.com/ccsb-scripps/AutoDock-Vina
cd AutoDock-Vina/build/linux/release
make
```

**Build Python Bindings:**

```bash
conda activate vina
cd ../../python
conda install -c conda-forge numpy boost-cpp swig
rm -rf build dist *.egg-info
python setup.py build install
```

---

### 3.3. AutoDock Tools (ADT)

Since it requires Python 2.7, it's best installed in a Conda environment:

```bash
conda create -n adt-env python=2.7 -y
conda activate adt-env
conda install -c bioconda autodocktools -y
```

Or download from the [official AutoDock website](http://autodock.scripps.edu).

---

### 3.4. PyRx (GUI for Vina)

Download the `PyRx-????.AppImage` from the [PyRx GitHub Releases](https://github.com/mvina/PyRx/releases).

Install and run:

```bash
chmod +x PyRx-????.AppImage
./PyRx-????.AppImage
```

---

### 3.5. UCSF Chimera (Molecular Visualization)

Download the `chimera-????.bin` installer from the [official UCSF Chimera website](https://www.cgl.ucsf.edu/chimera/download.html).

Install:

```bash
chmod +x chimera-????.bin
./chimera-????.bin
```

---

### 3.6. LigPlot+ (2D Interaction Analysis)

Download from the [LigPlot+ website](https://www.ebi.ac.uk/thornton-srv/software/LigPlus/).

Install:

```bash
tar -xzvf LigPlus_????.tar.gz
cd LigPlus
./ligplot.sh
```

---

### 3.7. SwissADME and pkCSM (Drug-Likeness Prediction)

Online tools — no installation required:

* [SwissADME](https://www.swissadme.ch/)
* [pkCSM](https://biosig.lab.uq.edu.au/pkcsm/)

---

### 3.8. Mendeley Desktop (Reference Manager)

Download the archive from [Mendeley’s official Linux download page](https://desktop-download.mendeley.com/download/linux/).

Install:

```bash
tar -xvjf mendeleydesktop-????.tar.bz2
cd mendeleydesktop-????/
./bin/mendeleydesktop
```

---

### 3.9. Avogadro (Molecule Editor)

Install via APT:

```bash
sudo apt install avogadro
```
