**Project Overview: Activity Analysis for Cost Efficiency of Healthcare Services to Health Maintenance Organizations**

## Introduction

Welcome to the Cost Efficiency Analysis project focused on evaluating and estimating the cost of healthcare services provided by Almadina Clinic to Health Maintenance Organizations (HMOs). This project aims to gain valuable insights into the cost structure, identify cost drivers, and make data-driven decisions to mitigate or minimize cost implications, thereby improving the overall financial efficiency of the healthcare services provided to HMOs.

## Project Background

The rising cost of healthcare services has become a significant concern in the healthcare industry. Over the past 13 years, health providers have received the same capitation amount from the National Health Insurance Scheme (NHIS). However, during this time, the cost of providing these essential healthcare services to HMOs has significantly increased, posing challenges in maintaining standards and effectively managing the organization. As responsible healthcare providers, we remain steadfast in our commitment to delivering the highest quality of care while ensuring cost-effectiveness for our HMO partners. The initiation of the Activity Analysis Project is aimed at gaining profound insights into resource utilization, identifying inefficiencies, and making well-informed, data-driven decisions to enhance the overall healthcare experience for the esteemed enrollees within the HMOs.

## Project Objectives

1. **Cost Evaluation:** Conduct a comprehensive evaluation of the cost incurred for each healthcare activity. We will analyze the cost drivers and assess the proportion of the total cost attributed to each activity.

2. **Service Efficiency:** Evaluate the efficiency of various healthcare services in terms of cost per patient, wait times, and patient outcomes. Identify any bottlenecks and recommend process improvements to streamline service delivery.

3. **Enrollee Satisfaction:** Correlate cost and resource allocation with enrollee satisfaction. Understand the impact of cost-effective healthcare on enrollee experience and loyalty.

4. **Cost Estimation:** Utilize statistical methods and regression models to estimate the cost for different healthcare services based on historical data. This will allow us to forecast expenses for future periods and assess the impact of potential changes.

5. **Cost Mitigation Strategies:** Based on the cost evaluation and estimation results, we will identify strategies to mitigate or reduce cost implications while maintaining the quality of care.

6. **Recommendations:** The final step involves providing data-backed recommendations to Almadina Clinic's management. These recommendations will focus on cost-saving measures, process improvements, and strategies for achieving enhanced cost efficiency for HMOs.

## Data Source

The data used for this Cost Efficiency Analysis project does not contain sensitive company information. To ensure data privacy and confidentiality, actual data from the organization has not been utilized. Instead, synthetic data that closely mimic the characteristics and statistical properties of the original dataset has been generated for the purpose of demonstrating the analysis techniques. The synthetic data maintains the structure and complexity of the actual data, allowing us to conduct a comprehensive evaluation and estimation without exposing any sensitive information.

The generation of synthetic data follows rigorous data anonymization and privacy-preserving procedures, ensuring that individual identities, financial details, and any proprietary information remain completely protected. As a result, the analysis and conclusions derived from this project are based solely on the simulated data and are not reflective of any specific individuals, entities, or actual financial figures.

By adopting this approach, we maintain a commitment to safeguarding the privacy and confidentiality of all stakeholders involved while still effectively showcasing the potential benefits of cost-efficiency analysis in the healthcare industry. Synthetic data also ensures compliance with relevant data protection regulations and best practices within the healthcare sector. Rest assured that the insights and recommendations drawn from this analysis will be of value to Almadina Clinic and other healthcare providers in their pursuit of enhanced financial efficiency and quality healthcare services.

## Methodology

1. **Data Collection:** Gather comprehensive data on healthcare service costs, resource utilization, enrollee feedback, and other relevant metrics from various sources within the organization.

2. **Data Cleaning and Preparation:** Thoroughly clean and preprocess the data to ensure its accuracy and consistency. Convert raw data into a format suitable for analysis.

3. **Exploratory Data Analysis (EDA):** Perform EDA to gain initial insights into the data. Identify trends, outliers, and potential relationships between variables.

4. **Activity-Based Costing (ABC) Analysis:** Implement Activity-Based Costing methodology to allocate costs to specific healthcare activities and services. This will provide a more accurate understanding of the cost structure.

5. **Statistical Analysis:** Utilize various statistical techniques and models to uncover patterns and relationships within the data.

6. **Data Visualization:** Create informative visualizations to present the findings in a clear and concise manner. Visualizations will aid in communicating complex information to stakeholders effectively.

## Analysis Steps Taken

1. **Data Extraction:** The transaction table (fact table) was exported from the Health Information System, covering the period from 2019 to 2020. It includes essential fields such as Date, Patient Name, HMO Code, HMO Name, HMO Category, Service Rendered, Service ID, Service Category, Location/Department, 10% Co-Payment, Value of Transaction, Covered by Cap, and Not Covered by Cap.

2. **Dimension Tables:** Three dimension tables were created, including Health Maintenance Organization Details (HMO Code, HMO Name, HMO Category), Healthcare Services Details (Service ID, Service Name, Service Category, Sales Price), and HMO Category Details (Serial Number, HMO Category).

3. **Power Query and Power Pivot:** Power Query was used to perform the Extract, Transform, Load (ETL) processes on the data. The data was then connected to Power Pivot for further analysis.

4. **Date Table:** A date table was created to facilitate time-based analysis.

5. **Data Relationships:** One-to-many relationships were established between the dimension tables using their corresponding IDs.

## Measures Categorized:

1. **Cost Evaluation:**
   - Total NHIS Services 2019:=CALCULATE([Total Cost of Serv.],DATEADD(DCalendar[Date],-1,YEAR))
   - Total NHIS Services 2020:=CALCULATE([Total Cost of Serv.],DATEADD(DCalendar[Date],1,YEAR))
   - Percentage Change:=DIVIDE([Total NHIS Services 2020],[Total NHIS Services 2019])
   - Cummulative Yearly Total:=TOTALYTD([Total Cost of Serv.],DCalendar[Date])
   - Total Cost of Serv.:=[Total FFS]+[Total CAP]
   - Total CAP:=sum([Covered by Cap])
   - Total FFS:=Sum([Not Covered By Cap])
   - Total 10% Co-Payment:=SUM([10% Co-payement])
   - % of Total Cost:=Divide([Total Cost of Serv.],(CALCULATE([Total Cost of Serv.],ALL(FTransactions))))

2. **Service Efficiency:**
   - Total NHIS Visit:=COUNT([Value of Transaction])
   - Avr. NHIS visit:=AVERAGEX(DCalendar,[Total NHIS Visit])
   - Total NHIS FFS:=Count([Not Covered By Cap])
   - Total NHIS CAP:=Count([Covered by Cap])
   - Avr.Monthly NHIS visit:=AVERAGEX(ALL(DCalendar[Month]),[Total NHIS Visit])
   - Avr. Cost of Serv.:=AVERAGEX(DCalendar,[Total Cost of Serv.])
   - Avr.Cost CAP:=AVERAGE([Covered by Cap])
   - Avr.Cost FFS:=ROUND(AVERAGE([Not Covered By Cap]),2)

## Findings and Recommendations

1. **Cost Evaluation:**
   - The analysis reveals that 63% of the total cost of services between 2019 and 2020 are consumed by public enrollees, while private enrollees account for 37%. This finding suggests that cost mitigation strategies should be tailored differently for public and private HMOs.
   - The top 3 most active HMOs (Princeton, Songhai, and WiseHealth) have accounted for a significant portion of the total cost (33%) and may require targeted cost optimization efforts.
   - The Pharmacy department has a major role in the cost structure, with 50% of the total cost attributed to it. Optimizing cost in this department could lead to substantial savings for Almadina Clinic.

2. **Service Efficiency:**
   - The average monthly number of NHIS visits provides insights into the demand for healthcare services, helping allocate resources effectively across departments and time periods.

## Conclusions on Cost Mitigation

Based on the analysis, Almadina Clinic can focus on implementing the following cost mitigation strategies:

1. **Optimize Pharmacy Operations:** Given the Pharmacy department's significant contribution to the total cost, it is crucial to closely monitor and streamline its operations. This includes efficient drug inventory management, cost-effective procurement practices, and close collaboration with the Clinic to reduce credit issuance for drugs.

2. **Targeted Cost Reduction for Active HMOs:** The top 3 most active HMOs demand a considerable share of healthcare services. Identifying the specific cost drivers for each HMO and negotiating better terms can help optimize cost without compromising service quality.

3. **Efficient Resource Allocation:** Understanding the monthly variation in NHIS visits enables Almadina Clinic to allocate resources more efficiently. By aligning staff schedules and service offerings with peak demand periods, the clinic can optimize capacity utilization and minimize costs.

4. **Continuous Monitoring and Analysis:** Regularly monitoring cost trends and conducting periodic analysis will enable Almadina Clinic to identify emerging cost drivers and take proactive measures to mitigate potential cost implications.

Through the implementation of these strategies, Almadina Clinic can achieve enhanced cost efficiency, maintain service quality, and ultimately provide more affordable and accessible healthcare services to HMO enrollees.

## Visualizations and Charts

### Total Cost of Services: ₦401,194,041
### Total Fee for Service: ₦180,998,509
### Total Capitation: ₦220,195,532

#### Column Chart: Battery Gauge (% of Total Cost)

#### Doughnut Chart: Segmented HMO Category based on Average Cost of Services

#### Bar Chart: Top 3 Most Active HMOs

## Slicers

- Filter by Year: 2019, 2020
- Filter by HMO Category: Private, Public
- Filter by HMO Name: Health Maintenance Organization
- Filter by Month: Jan, Feb, March, etc.

## Project Deliverables

1. Cost Efficiency Report: A comprehensive report detailing the findings of the cost evaluation and estimation analysis, along with actionable recommendations.
2. Visualizations: Informative visualizations and charts representing the cost data to facilitate easy comprehension of the findings.
3. Cost Estimation Model: A regression model or any other relevant approach used for cost estimation, including documentation on its accuracy and limitations.
4. Cost Mitigation Recommendations: Detailed recommendations for mitigating or reducing cost implications while ensuring the quality and effectiveness of healthcare services.

## Glossary Terms

**HMO:** Health Maintenance Organizations A private or public incorporated company registered by the NHIS solely to manage the provision of health care services through Health Care Providers accredited by the Scheme.

**HMO Category:** These can be categorized under the formal or informal sector (public or private). Public includes governmental institutions that make available health insurance services to their staff, while private includes businesses or corporations that establish a health care scheme for their staff and employees to access care from a health provider.

**NHIS:** The National Health Insurance Scheme, A body corporate established under Act 35 of 1999, to regulate and provide health insurance in Nigeria where health care services are paid for from the common pool of funds contributed by the participants of the Scheme.

**Enrollee or Beneficiary:** A person who has enrolled (or has been enrolled) with NHIS and who, by being up to date with payment of premium (or having been paid for), is entitled to cover by NHIS.

**Cap (Capitation):** This is payment to a primary healthcare provider by the HMOs on behalf of a contributor for services to be rendered by the healthcare provider. This payment is made regularly and in advance, irrespective of whether the enrollee utilizes the service or not.

**FFS (Fee For Service):** This is payment made by HMO(s) to secondary/tertiary healthcare providers that render services on referrals from other accredited healthcare providers. Primary healthcare providers can also be paid on a fee-for-service basis for emergency cases.

**Co-Payment:** This is payment made by the enrollee to the accredited pharmacy provider at the point of service. It is 10% of the total cost of drugs dispensed per prescription in accordance with the NHIS Drug Price List (not applicable to vulnerable groups and tertiary institutions' programs).


## Conclusion

The Cost Efficiency Analysis project conducted on Almadina Clinic's healthcare services has provided valuable insights into cost structures, cost drivers, and opportunities for cost mitigation. By implementing the recommended strategies and closely monitoring cost trends, Almadina Clinic can enhance financial efficiency, deliver high-quality healthcare services, and continue its commitment to providing accessible and affordable healthcare to HMO enrollees.
