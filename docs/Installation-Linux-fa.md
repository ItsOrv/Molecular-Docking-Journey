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
```
حالا با دستور زیر مطمئن میشیم که درست نصب شد
```bash
obabel -V
```

---

### ۳.۲. AutoDock Vina (موتور داکینگ)

#### روش ۱: دانلود نسخه باینری

1. از [GitHub AutoDock Vina](https://github.com/ccsb-scripps/AutoDock-Vina/releases) نسخه مناسب را دانلود کنید.
2. فایل باینری را اجرا کنید:

```bash
./vina_<version> --help
```
حالا اینو به /usr/local/bin انتقال میدیم

#### روش های بعدی
اگه این روش جواب نداد روش های بعدی رو برای نصب 
چک کنید.

####[روش های جایگزین](Adv-other-installation-fa.md)
---

### ۳.۳. AutoDock Tools (ADT)
اینو هنوز نمیدونم چجوری نصب کنم
بعدا اضافه میکنم 
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

دانلود از [LigPlot+](https://www.ebi.ac.uk/thornton-srv/software/LigPlus/)

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

دانلود از [Mendeley](https://desktop-download.mendeley.com/download/linux/)

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
