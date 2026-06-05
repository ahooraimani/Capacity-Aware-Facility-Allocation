# Capacity-Aware Facility Allocation
### تخصیص ظرفیت‌محور تسهیلات شهری

This project implements a capacity-aware spatial allocation workflow for assigning residential parcels to school facilities using Python and ArcPy.

این پروژه یک فرایند تخصیص فضایی ظرفیت‌محور را برای اختصاص واحدهای مسکونی به مدارس با استفاده از Python و ArcPy پیاده‌سازی می‌کند.

---

## 📌 Project Overview / معرفی پروژه

**English:**  
In many urban planning and service-area analysis problems, simple proximity-based allocation is not sufficient. Facilities such as schools have different capacities, and allocation should consider both distance and capacity.

This project uses an iterative Binary Search approach to find a service radius for each school. The selected radius is the one whose covered residential population is closest to the school's capacity. In this implementation, capacity is used as an optimization target rather than a strict upper limit.

**فارسی:**  
در بسیاری از مسائل برنامه‌ریزی شهری و تحلیل حوزه خدمات‌رسانی، تخصیص صرفاً بر اساس نزدیکی کافی نیست. تسهیلاتی مانند مدارس دارای ظرفیت‌های متفاوت هستند و فرایند تخصیص باید هم فاصله و هم ظرفیت را در نظر بگیرد.

در این پروژه از یک روش تکرارشونده مبتنی بر جستجوی دودویی استفاده شده است تا برای هر مدرسه یک شعاع خدماتی مناسب پیدا شود. شعاع انتخاب‌شده، شعاعی است که جمعیت واحدهای مسکونی تحت پوشش آن بیشترین نزدیکی را به ظرفیت مدرسه دارد. در این پیاده‌سازی، ظرفیت به‌عنوان یک مقدار هدف برای بهینه‌سازی استفاده می‌شود، نه به‌عنوان یک محدودیت سختگیرانه.

---

## ✨ Key Features / ویژگی‌های کلیدی

- **Capacity-Aware Allocation:** Uses school capacity as a target value in the allocation process.  
  **تخصیص ظرفیت‌محور:** استفاده از ظرفیت مدرسه به‌عنوان مقدار هدف در فرایند تخصیص.

- **Binary Search Optimization:** Searches for the best service radius through an iterative Binary Search process.  
  **بهینه‌سازی با جستجوی دودویی:** جست‌وجوی بهترین شعاع خدماتی از طریق یک فرایند تکرارشونده مبتنی بر Binary Search.

- **Nearest Practical Service Radius:** Allocates residential parcels based on a radius that best balances distance and capacity.  
  **شعاع خدماتی بهینه:** تخصیص واحدهای مسکونی بر اساس شعاعی که تعادل مناسبی میان فاصله و ظرفیت ایجاد می‌کند.

- **Unallocated Parcel Identification:** Parcels that are not assigned to any school remain with `Service_ID = 0`, allowing service gaps to be identified.  
  **شناسایی واحدهای تخصیص‌نیافته:** واحدهایی که به هیچ مدرسه‌ای اختصاص داده نمی‌شوند با مقدار `Service_ID = 0` باقی می‌مانند و امکان شناسایی شکاف‌های خدماتی را فراهم می‌کنند.

- **ArcGIS Integration:** Designed to run in an ArcGIS/ArcPy environment using shapefile inputs.  
  **یکپارچگی با ArcGIS:** طراحی‌شده برای اجرا در محیط ArcGIS/ArcPy با استفاده از فایل‌های Shapefile.

---

## 🧠 Methodology / روش‌شناسی

For each school, the algorithm performs the following steps:

برای هر مدرسه، الگوریتم مراحل زیر را انجام می‌دهد:

1. Sorts schools based on capacity and area.
2. Selects one school at a time.
3. Tests different service radii using Binary Search.
4. Calculates the total population of unassigned residential parcels within each radius.
5. Compares the covered population with the school's capacity.
6. Selects the radius with the minimum absolute difference:

\[
\min |Population - Capacity|
\]

7. Assigns selected residential parcels to the current school using its `Service_ID`.

---

## 🗺️ Visualization / نمایش بصری

The final map illustrates the spatial allocation results. Each residential parcel receives a `Service_ID` corresponding to the school it is assigned to. Parcels with `Service_ID = 0` remain unallocated.

نقشه نهایی نتایج تخصیص فضایی را نشان می‌دهد. هر واحد مسکونی مقدار `Service_ID` مدرسه‌ای را دریافت می‌کند که به آن اختصاص داده شده است. واحدهایی که مقدار `Service_ID = 0` دارند، تخصیص‌نیافته باقی می‌مانند.

![Final Map Output](Images/Capacity-Aware-Facility-Allocation.png)

---

## 🛠️ Requirements / پیش‌نیازها

- ArcGIS Desktop or ArcGIS Pro with ArcPy support
- Python environment compatible with ArcPy
- Input shapefiles:
  - a Residential Shapefile with population field.
  - a School Shapefile with capacity field.

---

## 🚀 How to Use / راهنمای اجرا

1. Clone or download this repository.  
   این ریپازیتوری را دانلود یا کلون کنید.

2. Open the notebook file:  
   فایل نوت‌بوک را باز کنید:
```text
   Capacity-Aware-Facility-Allocation.ipynb
   
