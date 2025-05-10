# روش های جایگزین نصب vina 

#### روش ۲: نصب از طریق pip

```bash
pip install -U numpy vina
```

#### روش ۳: نصب در محیط Conda

1. نصب Anaconda یا Miniconda:

   * [Anaconda](https://docs.continuum.io/anaconda/install)
   * [Miniconda](https://conda.pydata.org/miniconda.html)

2. ایجاد محیط مخصوص:

```bash
conda create -n vina python=3 -y
conda activate vina
conda config --env --add channels conda-forge
```

3. نصب وابستگی‌ها:

```bash
conda install -c conda-forge numpy swig boost-cpp libboost sphinx sphinx_rtd_theme
pip install vina
```

#### روش ۴: ساخت از سورس (پیشنهاد نمی‌شود)

**مرحله ۱: نصب کامپایلر**

```bash
sudo apt install build-essential
```

**مرحله ۲: نصب Boost و SWIG**

```bash
sudo apt install libboost-all-dev swig
```

**مرحله ۳: دریافت و ساخت سورس**

```bash
git clone https://github.com/ccsb-scripps/AutoDock-Vina
cd AutoDock-Vina/build/linux/release
make
```

**ساخت بایندینگ‌های پایتون:**

```bash
conda activate vina
cd ../../python
conda install -c conda-forge numpy boost-cpp swig
rm -rf build dist *.egg-info
python setup.py build install
```

حالا برمیگردیم به ادامه  
[نصب برنامه ها](Installation-Linux-fa.md)