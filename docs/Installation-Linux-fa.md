[English](Installation-Linux-en.md) / [فارسی](Installation-Linux-fa.md)



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

[روش های جایگزین](Adv-other-installation-fa.md)
---

### ۳.۳. AutoDock Tools (ADT)
اینو هنوز نمیدونم چجوری نصب کنم
بعدا اضافه میکنم 
xxxx
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

حالا تا اینجا این برنامه هارو نصب کردیم:

1. **Open Babel** – برای تبدیل فرمت‌های مولکولی
2. **AutoDock Vina** – موتور داکینگ مولکولی
3. **AutoDock Tools (ADT)** – هنوز نصب نشده (به صورت یادداشت درج شده)
4. **PyRx** – رابط گرافیکی ساده برای Vina
5. **UCSF Chimera** – برای نمایش ساختارهای مولکولی
6. **LigPlot+** – تحلیل دو بعدی تعاملات مولکولی
7. **SwissADME** *(ابزار آنلاین)* – پیش‌بینی ویژگی‌های دارویی
8. **pkCSM** *(ابزار آنلاین)* – پیش‌بینی سمیت و ویژگی‌های دارویی
9. **Mendeley Desktop** – مدیریت منابع علمی
10. **Avogadro** – ویرایش ساختارهای شیمیایی

بریم بخش بعدی یعنی آماده سازی پروتئین، البته فعلا خیلی ساده این کار رو انجام میدیم و بعدا تخصصی تر بهش می‌پردازیم 

- **[مرحله ۳: آماده‌سازی پروتئین](protein-preparation-fa.md)**
