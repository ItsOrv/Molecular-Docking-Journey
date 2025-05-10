## ۱. به‌روزرسانی سیستم

ابتدا سیستم را به‌روزرسانی کنید تا آخرین نسخه از بسته‌ها نصب شود:

```bash
sudo apt update && sudo apt upgrade
```

---

## ۲. نصب پیش‌نیازهای پایه

نصب ابزارها و کتابخانه‌های ضروری:

```bash
sudo apt install build-essential cmake git curl wget unzip zlib1g-dev libglu1-mesa libxi-dev libxmu-dev libpng-dev libfreetype6-dev default-jre
```

---

## ۳. نصب نرم‌افزارها

### ۳.۱. Open Babel (تبدیل فرمت‌های مولکولی)

نصب از APT:

```bash
sudo apt install openbabel
obabel -V  # بررسی نصب
```

---

### ۳.۲. AutoDock Vina (موتور داکینگ)

#### روش ۱: دانلود نسخه باینری

1. از [صفحه GitHub AutoDock Vina](https://github.com/ccsb-scripps/AutoDock-Vina/releases) نسخه مناسب را دانلود کنید.
2. فایل باینری را اجرا کنید:

```bash
./vina_<version>_<os>_<arch> --help
```
حالا اینو به /usr/local/bin انتقال میدیم
اگه با همین روش نصب کردین دیگه نیازی به انجام دادن روش های دیگه نیست

#### روش های بعدی
اگه این روش جواب نداد روش های بعدی رو چک کنید
advfilelink
---

### ۳.۳. AutoDock Tools (ADT)
xxxx این بخش هنوز مشکل داره xxxx

به دلیل نیاز به Python 2.7، توصیه می‌شود در محیط Conda نصب شود:

```bash
conda create -n adt-env python=2.7 -y
conda activate adt-env
conda install -c bioconda autodocktools -y
```

یا دانلود از [سایت رسمی AutoDock](http://autodock.scripps.edu)

---

### ۳.۴. PyRx (رابط گرافیکی ساده برای Vina)

دانلود از [sourceforge](https://sourceforge.net/projects/pyrx/)

نصب:

```bash
tar -xzvf pyrx-?????-linux-x86_64.tar.gz 
cd PyRx
./run.sh 
```

---

### ۳.۵. UCSF Chimera (نمایش ساختارهای مولکولی)

دانلود از [وب‌سایت رسمی UCSF Chimera](https://www.cgl.ucsf.edu/chimera/download.html)

نصب:

```bash
chmod +x chimera-????.bin
./chimera-????.bin
```

---

### ۳.۶. LigPlot+ (تحلیل دو بعدی تعاملات)

دانلود از [وب‌سایت LigPlot+](https://www.ebi.ac.uk/thornton-srv/software/LigPlus/)

نصب:

```bash
tar -xzvf LigPlus_????.tar.gz
cd LigPlus
./ligplot.sh
```

---

### ۳.۷. SwissADME و pkCSM (پیش‌بینی ویژگی‌های دارویی)

ابزارهای آنلاین:

* [SwissADME](https://www.swissadme.ch/)
* [pkCSM](https://biosig.lab.uq.edu.au/pkcsm/)

---

### ۳.۸. Mendeley Desktop (مدیریت منابع علمی)

دانلود از [لینک رسمی](https://desktop-download.mendeley.com/download/linux/)

نصب:

```bash
tar -xvjf mendeleydesktop-????.tar.bz2
cd mendeleydesktop-????/
./bin/mendeleydesktop
```

---

### ۳.۹. Avogadro (ویرایش ساختارهای شیمیایی)

نصب مستقیم:

```bash
sudo apt install avogadro
```
