# Dataset Description: Healthcare Services Cost Analysis

## Data Source

The dataset used for this analysis was obtained from the Health Information System at Almadina Clinic. The data export range covers transactions from 2019 to 2020. It includes information related to healthcare services provided to Health Maintenance Organization (HMO) enrollees.

Here's a preview of the dataset:

| Date       | Patient Name           | HMO CODE | HMO NAME                            | HMO CATEGORY | Services Rendered       | Location/Department | 10% Co-payment | Value of Transaction | Covered by Cap | Not Covered By Cap | PRODUCT ID | CATEGORY       |
|------------|------------------------|----------|-------------------------------------|--------------|-------------------------|---------------------|-----------------|----------------------|----------------|--------------------|------------|----------------|
| 01/01/2019 | YUNUSA, ZAINAB         | 080A     | CUSTOMS SERVICES NHIS MONITORED     | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | SULEIMAN, BARAATU      | 023A     | UNITED COMPREHENSIVE HEALTH MANAGERS LTD | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | ABDULLAHI, ALHASSAN    | 017A     | PRINCETON HEALTH GROUP               | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | DIKKO MARYAM           | 019A     | WISEHEALTH SERVICES LIMITED          | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | MUHAMMAD, ABDULRAZAK   | 013B     | SONGHAI HEALTH TRUST LTD             | PRIVATE      | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | GARBA, HAUWA'U         | 019A     | WISEHEALTH SERVICES LIMITED          | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | UMAR, Nana-Aisha       | 015A     | PREMIER MEDICAID                    | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | IBRAHAM, NURADDEEN     | 019A     | WISEHEALTH SERVICES LIMITED          | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | ALI, UMAR              | 004B     | HEALTHCARE INTERNATIONAL LIMITED     | PRIVATE      | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | null           | 1,000.00           | CL0084     | Medical Service|
| 01/01/2019 | NURA, TASIU            | 054A     | SALUS TRUST HMO                     | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | null           | 1,000.00           | CL0084     | Medical Service|
| 01/01/2019 | JIBRIL, MARJANATU SANI | 019A     | WISEHEALTH SERVICES LIMITED          | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | JIBRIL, NUJAHID        | 019A     | WISEHEALTH SERVICES LIMITED          | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|
| 01/01/2019 | JIBRIN, ABUBAKAR       | 019A     | WISEHEALTH SERVICES LIMITED          | PUBLIC       | GP Consultation - (NHIS) | Almadina Clinic     | null            | 1,500.00             | 1,500.00       | null               | CL0084     | Medical Service|

## Data Summary
The columns contain data of different types, including dates, text, integers, and currency values.

* **Number of rows:** 204502
* **Number of columns:** 18
* **Minimum value for columns with cost associations:**
    * 10% Co-payment: 0.9
    * Value of Transaction: 5
    * Covered by Cap: 8.1
    * Not Covered by Cap: 14
* **Maximum value for columns with cost associations:**
    * 10% Co-payment: 7636.5
    * Value of Transaction: 6276253
    * Covered by Cap: 6276253
    * Not Covered by Cap: 760000
* **Mean for columns with cost associations:**
    * 10% Co-payment: 118.3271112
    * Value of Transaction: 1867.100215
    * Covered by Cap: 1247.869532
    * Not Covered by Cap: 2679.120633
* **Median for columns with cost associations:**
    * 10% Co-payment: 99
    * Value of Transaction: 1125
    * Covered by Cap: 1380
    * Not Covered by Cap: 1500
* **Standard deviation for columns with cost association:**
     * 10% Co-payment: 107.7169484
    * Value of Transaction: 14927.79893
    * Covered by Cap: 18853.76686
    * Not Covered by Cap: 9324.376856

## Data Dictionary

Here's a brief data dictionary for the columns:

- Date: Date of the healthcare service transaction (Date/time format).
- Patient Name: Name of the patient receiving the service (Text).
- HMO CODE: Code assigned to the Health Maintenance Organization (Integer).
- HMO NAME: Name of the Health Maintenance Organization (Text).
- HMO CATEGORY: Category of the HMO (Text).
- Services Rendered: Description of the healthcare service provided (Text).
- Location/Department: Department or location where the service was rendered (Text).
- 10% Co-payment: The 10% co-payment paid by the enrollee (Currency).
- Value of Transaction: Total healthcare service value (Currency).
- Covered by Cap: Amount covered by the capitation payment from the HMO (Currency).
- Not Covered By Cap: Amount not covered by the capitation payment (Currency).
- PRODUCT ID: Unique identifier for the healthcare service product (Text).
- CATEGORY: Category of the healthcare service (Text).

## Data Cleaning and Preprocessing

The dataset underwent a thorough cleaning and preprocessing steps to ensure its suitability for analysis. Missing values were handled, and data inconsistencies were addressed. Synthetic data were generated to mimic the characteristics of the original dataset, ensuring the privacy and confidentiality of sensitive information. The main cleaning and preprocessing operations are as follows:

1. **Data Loading:** The data was loaded from a folder containing monthly transactions for the year 2019 to 2020.

2. **Data Extraction:** Unnecessary columns were removed, leaving only the "Content" column.

3. **Excel Workbook Extraction:** The "Content" column was converted into Excel workbooks to access the data in a structured format.

4. **Data Transformation:** The data was transformed by promoting headers to create meaningful column names and expanding the table.

5. **Filtering:** Only records related to NHIS patients were selected for the analysis.

6. **Data Splitting:** The "HMO Name(Code)" column was split to separate the HMO Code, HMO Name, and HMO Category.

7. **Text Transformation:** The text values in the "HMO Name(Code)" column were standardized to uppercase, and specific phrases were replaced with consistent categories.

8. **Data Joining:** The dataset was merged with a product items table to include additional information about the healthcare services provided.

9. **Data Cleanup:** Null values in the "PRODUCT ID" and "CATEGORY" columns were replaced with appropriate default values.

10. **Data Type Conversion:** The "10% Co-payment," "Value of Transaction," "Covered by Cap," "Not Covered By Cap," and "Date" columns were converted to the appropriate data types.

The cleaned and preprocessed dataset is now ready for analysis.

For more details, you can check the raw dataset file [Dataset](https://docs.google.com/spreadsheets/d/1dEK3mo-xPwsMboUCSEvhyibJBreFr1Uh/edit?usp=sharing&ouid=106517304862390569506&rtpof=true&sd=true)

