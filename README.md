# HR-Attrition-Analytics-Dashboard-Excel-# HR Attrition Analytics Dashboard (Excel)

## Overview
An interactive Excel dashboard analyzing employee attrition across a workforce of **1,480 employees**. The workbook uses Power Query to load and shape the source data, Power Pivot (Data Model) to build relationships and DAX measures, and a 3-page PivotTable/PivotChart dashboard with slicers to explore attrition, overtime, satisfaction, and income patterns across departments, job roles, age groups, and demographics.

## Business Problem / Objective
HR teams need a clear, filterable view of **where and why attrition is happening** — by department, job role, age, tenure, and working conditions (overtime, travel frequency) — in order to prioritize retention efforts. This dashboard was built to answer questions such as:
- Which departments and job roles have the highest attrition?
- Does overtime correlate with higher attrition?
- How does attrition vary by age, years at company, and years in current role?
- Are there pay or satisfaction gaps by department, job role, or gender?

## Dataset Overview
- **Records:** 1,480 employees (loaded into the Data Model via a Power Query connection named "Fact")
- **Type/source:** Employee-level HR records. The field structure and values (departments — Research & Development, Sales, Human Resources; the 9 job roles; business travel categories, etc.) are consistent with the widely used **IBM HR Analytics Employee Attrition** dataset structure — the exact original source is not stated in the file, so this is a reasonable inference rather than a confirmed fact.
- **Key fields used in the model:** Attrition, Department, JobRole, Age / AgeGroup, Gender, MaritalStatus, BusinessTravel, EducationField, OverTime, SalarySlab, MonthlyIncome, JobLevel, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion
- **Raw data table:** not included as a separate flat sheet in this workbook — the data is loaded directly into the Data Model through the "Fact" Power Query connection.

## Tools & Technologies
- Microsoft Excel
- **Power Query** — data connection/query ("Fact") feeding the Data Model
- **Power Pivot / Data Model** — relationships and calculated measures
- **DAX** — custom measures (e.g., `DIVIDE`, `CALCULATE`) for rates and averages
- **PivotTables** (24) and **PivotCharts** (13 standard charts + 1 modern/"chartEx" chart) — bar, line, pie, and doughnut charts
- **Slicers** (Department, Age Group, Salary Slab, Business Travel, Marital Status, Education Field, Gender, OverTime, Attrition) for interactive filtering

## Data Preparation
- Source data was brought into Excel through a Power Query connection ("Query - Fact") and loaded to the Data Model rather than a worksheet, keeping the workbook lightweight and query-refreshable.
- Fields such as **AgeGroup** and **SalarySlab** were prepared as grouped/banded categories (e.g., 18–25, 26–35, 36–45, 46–55, 55+) to support cleaner visual breakdowns than raw continuous values.

## Data Modeling
- Data was loaded into Excel's **Data Model** (Power Pivot), with measures defined at the model level rather than as static worksheet formulas — visible in the pivot fields as `[Fact].[...]` (dimensions) and `[Measures].[...]` (DAX measures).
- **DAX measures built into the model:**
  - `total employee`
  - `Attration rate` (attrition rate)
  - `over time rate` / `overtime rate`
  - `count of employee with overtime`
  - `satsfaction score` (satisfaction score)
  - `monthly income` (average)
  - `Average of YearsAtCompany`
  - `Average of YearsInCurrentRole`
  - `Distinct Count of Department`
  - `Distinct Count of JobRole`

## Analysis / KPIs
Headline metrics surfaced on the dashboard:

| Metric | Value |
|---|---|
| Total Employees | 1,480 |
| Attrition Rate | 16% |
| Overtime Rate | 28% |
| Employees Working Overtime | 418 |
| Average Satisfaction Score | 2.73 (out of 4) |
| Average Monthly Income | $6,504.99 |
| Departments | 3 |
| Job Roles | 9 |

Attrition and other measures are broken down by: Department, Job Role, Age (and Age Group), Gender, Business Travel frequency, Marital Status, Years at Company, and Years in Current Role.

## Dashboard Overview
The workbook contains **three linked dashboard pages** (with page-to-page navigation buttons and "Clear Filters" controls):

1. **OverView** — Attrition Rate, Attrition Rate by Job Role, Average Monthly Income by Department, Overtime Rate, Average Monthly Income, Satisfaction Rate by Job Role, Attrition Rate by Age. Filterable by Age Group, Department, and Salary Slab.
2. **Department** — Number of Departments, Attrition Rate by Department, Employee Distribution by Department, Satisfaction Rate by Job Role, Average Years at Company by Job Role, Number of Job Roles, overall Attrition Rate. Filterable by Business Travel, Department, and Marital Status.
3. **Employee** — Overtime Employee count, Attrition Rate by Age, Total Employees, Satisfaction Score, Monthly Income by Age Group, Male vs. Female comparison, Attrition Rate by Years at Company. Filterable by Education Field and Gender.

## Key Insights
*(Based on the KPI values captured in the workbook's pivot tables)*
- Overall attrition sits at **16%**, against an **overtime rate of 28%** — a sizeable share of the workforce is working overtime.
- Attrition varies noticeably by job role, ranging from roughly **2.5% (Research Director)** up to **~39% (Sales Representative)** — front-line sales and lab/support roles show the highest attrition.
- **Sales** has the highest average monthly income by department, while overall average monthly income across the company is **$6,504.99**.
- Employees who **travel frequently** show higher attrition than those who travel rarely or not at all.
- Average satisfaction score sits at **2.73 out of 4**, a modest-but-not-low level that varies by job role.

## Project Outcome / Business Value
The dashboard gives HR and people-leadership a single, filterable view to identify **which roles, departments, and employee segments carry the highest attrition risk**, and to see how that risk relates to overtime, travel demands, tenure, and pay — supporting more targeted retention decisions instead of company-wide, one-size-fits-all interventions.

## Project Structure
| Sheet | Purpose |
|---|---|
| `meta and colors` | Workbook color palette / design reference |
| `pivot tables` | 24 supporting PivotTables that feed the dashboard visuals |
| `overView` | Dashboard page 1 — company-wide KPIs |
| `Department` | Dashboard page 2 — department-level breakdown |
| `Employee` | Dashboard page 3 — employee/demographic breakdown |

## Skills Demonstrated
- Data modeling with Power Pivot (star-schema-style Data Model)
- DAX measure development (`DIVIDE`, `CALCULATE`, aggregations)
- Power Query data loading
- Advanced PivotTable / PivotChart design
- Interactive dashboard design with slicers and cross-page navigation
- HR/People Analytics: attrition analysis, KPI definition, and segmentation
