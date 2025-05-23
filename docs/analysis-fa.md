[English](analysis-en.md) / [فارسی](analysis-fa.md)

حالا که مرحله داکینگ انجام شده و فایل‌های خروجی رو داریم، بریم سراغ **مرحله آنالیز، تفسیر نتایج و مستندسازی**. این بخش بسیار مهمه چون نشون می‌ده آیا لیگاند (مثلاً Donepezil) به خوبی به محل فعال پروتئین (مثلاً Acetylcholinesterase) متصل شده یا نه، و چقدر اتصالش قوی و منطقیه.

---

## مرحله آنالیز نتایج داکینگ

---

### 1. بررسی انرژی اتصال (Binding Affinity)

فایل `log.txt` که توسط Vina تولید شده، شامل انرژی اتصال هر مدل پیشنهادی هست. هرچه مقدار انرژی منفی‌تر باشه، اتصال قوی‌تره.

نمونه‌ای از خروجی:

```txt
Mode | Affinity (kcal/mol) | RMSD l.b. | RMSD u.b.
-----------------------------------------------------
   1       -10.3              0.000       0.000
   2       -9.8               1.214       2.003
   3       -9.5               1.897       2.874
```

**Affinity (kcal/mol)**: انرژی اتصال — مقادیر زیر -7 معمولاً قابل‌قبول و زیر -9 بسیار خوب محسوب می‌شن.

**RMSD** (Root Mean Square Deviation): تفاوت ساختاری بین حالات مختلف اتصال. مقدار پایین نشون می‌ده حالت‌ها مشابه هم‌ هستن.

---

### 2. مشاهده و بررسی محل اتصال

#### با PyMOL:

```bash
pymol protein.pdbqt output.pdbqt
```

1. بررسی کن لیگاند دقیقاً کجا به پروتئین متصل شده.
2. ابزار `Measurement Wizard` رو فعال کن تا فاصله‌ بین اتم‌ها یا باندهای هیدروژنی رو اندازه‌ بگیری.
3. بررسی کن که لیگاند در محل فعال پروتئین هست یا نه.

#### با Chimera:

* باز کردن فایل‌ها
* فعال کردن ابزار:

  ```
  Tools → Surface/Binding Analysis → FindHBond
  ```
* بررسی باندهای هیدروژنی، برهم‌کنش‌های آبگریز، و محل قرارگیری لیگاند

---

### 3. بررسی تعاملات (Interactions)

از ابزارهایی مثل **Chimera**، **Yasara** یا **PRAS** استفاده کن تا اطلاعاتی مثل موارد زیر به دست بیاری:

* باندهای هیدروژنی (Hydrogen Bonds)
* تعاملات آبگریز (Hydrophobic interactions)
* پیوندهای π–π یا π–کاتیون (مهم برای داروها)
* اتم‌های درگیر در اتصال (مثلاً Ser200, His440 در AChE)

> در Yasara یا PRAS معمولاً به‌صورت خودکار این اطلاعات استخراج می‌شن.

---

### 4. گزارش‌سازی

فایلی بساز و اطلاعات زیر رو بنویس:

* **پروتئین هدف:** (مثلاً Acetylcholinesterase - PDB ID: 1EVE)
* **لیگاند:** (Donepezil)
* **بهترین انرژی اتصال:** (مثلاً -10.3 kcal/mol)
* **تعداد باندهای هیدروژنی:** (مثلاً 3 عدد)
* **باقی‌مانده‌های درگیر در اتصال:** (مثلاً Ser203, Glu334, His447)
* **تصاویر اتصال:** از PyMOL یا Chimera عکس بگیر و ذخیره کن (می‌تونه به گزارش PDF اضافه بشه)

---

### 5. (اختیاری) بررسی دینامیک اتصال

اگر بخوای کار دقیق‌تری انجام بدی، می‌تونی از Yasara برای اجرای **energy minimization** و یا **docking refinement** استفاده کنی. این باعث می‌شه حالت اتصال بهینه‌تر بشه و نتایج واقعی‌تری بده.

---

### جمع‌بندی نهایی

| مورد                   | مقدار                          |
| ---------------------- | ------------------------------ |
| انرژی اتصال بهترین مدل | -10.3 kcal/mol                 |
| باقی‌مانده‌های فعال    | Ser203, His447, Glu334         |
| تعداد باندهای هیدروژنی | 3                              |
| تعاملات مهم            | هیدروژنی، π–π stacking، آبگریز |
| ابزارهای آنالیز        | PyMOL, Chimera, PRAS, Yasara   |


پیشنهاد میکنم اول با یسری مشکلات متداول و بهینه سازی ها اشنا بشید و بعد به مباحث پیشرفته تر وارد شیم

- **[مرحله ۷: رفع اشکال و بهینه‌سازی](troubleshooting-fa.md)**
- **[مرحله ۸: مباحث پیشرفته](advanced-fa.md)**
