## مرحله داکینگ با AutoDock Vina

---

### 1. ایجاد فایل پیکربندی (config.txt)

در یک ویرایشگر متنی (مثل `nano` یا `gedit`) فایل زیر را بساز:

```txt
receptor = protein.pdbqt
ligand = ligand.pdbqt

center_x = X.XXX
center_y = Y.YYY
center_z = Z.ZZZ

size_x = 20
size_y = 20
size_z = 20

out = output.pdbqt
log = log.txt
```

مقادیر `center_*` باید مرکز جعبه‌ای باشد که محل فعال پروتئین را در بر می‌گیرد. این مقادیر را از AutoDock Tools استخراج می‌کنی.

---

### 2. اجرای داکینگ

در ترمینال و در مسیر فایل‌ها، دستور زیر را اجرا کن:

```bash
vina --config config.txt
```

این دستور فرایند داکینگ را آغاز کرده و فایل‌های خروجی زیر را تولید می‌کند:

* `output.pdbqt`: بهترین حالت‌های اتصال لیگاند به پروتئین
* `log.txt`: شامل انرژی اتصال (Binding Affinity) و اطلاعات مربوط به هر حالت

---

### 3. مشاهده نتایج

#### در PyMOL:

```bash
pymol protein.pdbqt output.pdbqt
```

#### یا در Chimera:

* `File → Open → protein.pdbqt`
* سپس: `File → Open → output.pdbqt`

→ حالا می‌توانی اتصال لیگاند را در محل فعال پروتئین بررسی و تحلیل کنی.