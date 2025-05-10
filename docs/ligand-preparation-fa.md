[English](ligand-preparation-en.md) / [فارسی](ligand-preparation-fa.md)


## مراحل آماده‌سازی لیگاند برای داکینگ

---

### 1. **دانلود لیگاند (مثلاً Donepezil)**

از سایت [PubChem](https://pubchem.ncbi.nlm.nih.gov/) فایل لیگاند رو دانلود کن:

* جستجو: `Donepezil`
* گزینه **3D conformer** رو انتخاب کن.
* فرمت خروجی: `SDF` یا `Mol2`

> مثال: فایل ذخیره‌شده به اسم `donepezil.sdf`

---

### 2. **باز کردن فایل در Chimera**

* Chimera رو باز کن:

  ```bash
  chimera
  ```
* از منوی بالا:
  `File → Open` → فایل `donepezil.sdf` رو باز کن.
* بررسی کن که ساختار درست باشه و یکبار ذخیره‌اش کن به فرمت PDB:

  ```
  File → Save PDB → donepezil_clean.pdb
  ```

---

### 3. **افزودن هیدروژن‌های قطبی در Chimera**

در پنجره‌ی Chimera:

* از منوی بالا برو به:
  `Tools → Structure Editing → Add Hydrogens`
  → نوع pH رو انتخاب کن (مثلاً 7.4) → OK

---

### 4. **Minimize ساختار در Chimera**

* از منوی بالا:
  `Tools → Structure Editing → Minimize Structure`
* Force Field: AMBER یا GAFF
* Number of steps: 100
* بعد از Minimize، دوباره فایل رو ذخیره کن:

  ```
  File → Save PDB → donepezil_min.pdb
  ```

---

### 5. **باز کردن فایل در AutoDock Tools (ADT)**

* ترمینال:

  ```bash
  autodocktools
  ```
* داخل برنامه:

  * `File → Read Molecule` → باز کردن `donepezil_min.pdb`
  * سپس:

    * `Edit → Charges → Compute Gasteiger`
    * `Edit → Hydrogens → Add Polar Only`
    * `File → Save as PDBQT`
      → به‌صورت: `donepezil.pdbqt`

---

## فایل نهایی آماده‌شده برای داکینگ:

`donepezil.pdbqt`



- **[مرحله ۵: اجرای داکینگ](docking-execution-fa.md)**
