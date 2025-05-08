اول سیستم رو آپدیت میکنیم تا آخرین نسخه از پکیج هارو نصب کنه
```bash
sudo apt update && sudo apt upgrade
````
حالا پکیج های پایه و ضروری رو نصب میکنیم
```bash
sudo apt install build-essential cmake git curl wget unzip zlib1g-dev libglu1-mesa libxi-dev libxmu-dev libpng-dev libfreetype6-dev default-jre
````

---

## مراحل نصب نرم‌افزارها

### ۱. Open Babel (تبدیل فرمت‌های مولکولی)

نصب با APT:

```bash
sudo apt install openbabel
obabel -V  # بررسی نصب
```

---

### ۲. AutoDock Vina (موتور اصلی داکینگ)

دانلود از GitHub:

[https://github.com/ccsb-scripps/AutoDock-Vina/releases](https://github.com/ccsb-scripps/AutoDock-Vina/releases)

نصب به‌صورت معمول با استخراج فایل و افزودن مسیر به `PATH`.

---

### ۳. AutoDock Tools (ADT)

نیاز به Python 2.7 دارد، پیشنهاد می‌شود در محیط Conda نصب شود:

```bash
conda create -n adt-env python=2.7 -y
conda activate adt-env
conda install -c bioconda autodocktools -y
```

در صورت تمایل می‌توانید از سورس در سایت زیر نصب کنید:
[http://autodock.scripps.edu](http://autodock.scripps.edu)

---

### ۴. PyRx (رابط گرافیکی ساده برای Vina)

دانلود فایل `PyRx-????.AppImage` از GitHub:

[https://github.com/mvina/PyRx/releases](https://github.com/mvina/PyRx/releases)

نصب:

```bash
chmod +x PyRx-????.AppImage
./PyRx-????.AppImage
```

---

### ۵. UCSF Chimera (نمایش و ویرایش ساختارهای مولکولی)

دانلود فایل `chimera-????.bin` از سایت رسمی:

[https://www.cgl.ucsf.edu/chimera/download.html](https://www.cgl.ucsf.edu/chimera/download.html)

اجرا:

```bash
chmod +x chimera-????.bin
./chimera-????.bin
```

---

### ۶. LigPlot+ (نقشه تعاملات دو بعدی لیگاند و پروتئین)

دانلود از سایت رسمی:

[https://www.ebi.ac.uk/thornton-srv/software/LigPlus/](https://www.ebi.ac.uk/thornton-srv/software/LigPlus/)

نصب:

```bash
tar -xzvf LigPlus_????.tar.gz
cd LigPlus
./ligplot.sh
```

---

### ۷. SwissADME و pkCSM (پیش‌بینی ویژگی‌های دارویی)

ابزارهای آنلاین – بدون نیاز به نصب:

* [https://www.swissadme.ch/](https://www.swissadme.ch/)
* [https://biosig.lab.uq.edu.au/pkcsm/](https://biosig.lab.uq.edu.au/pkcsm/)

---

### ۸. Mendeley Desktop (مدیریت منابع مقاله)

دانلود فایل `mendeleydesktop-????.tar.bz2` از سایت آرشیو:

[https://desktop-download.mendeley.com/download/linux/](https://desktop-download.mendeley.com/download/linux/)

نصب:

```bash
tar -xvjf mendeleydesktop-????.tar.bz2
cd mendeleydesktop-????/
./bin/mendeleydesktop
```

---

### ۹. Avogadro (ویرایش ساختارهای شیمیایی)

نصب با APT:

```bash
sudo apt install avogadro
```
