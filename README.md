# Fall-2025-Group-3-Project-2

MIST 4610 Dr. Sri Fall 2025 Group 3 Section 2

## Team Name
62775 Group 3

## Team Members
1. Matthew Wise [@mwise12345](https://github.com/mwise12345/Fall-2025-Group-3-Project-2)
2. Ghasan Awad [@awadg420](https://github.com/awadg420/Fall-2025-Group-3-Project-2)
3. Trisha Kattoju [@tkattoju](https://github.com/tkattoju/Fall-2025-Group-3-Project-2)
4. Marissa Le [@MarissaLe](https://github.com/MarissaLe/Fall-2025-Group-3-Project-2)

# Data Description

Our data is the leading cause of deaths that we had obtained from https://catalog.data.gov/dataset/nchs-leading-causes-of-death-united-states. 
The data is based on information from all resident death certificates filed in the 50 states and the District of Columbia utilizing demographic and medical characteristics. The dataset contains 10,868 rows and 6 columns, combining both descriptive and quantitative variables. There are a variety of dimensions and data types that are captured. Beginning with the Year dimension which is a number dataset, switched to a date type in Tableau, this represents the years of recorded deaths and the years of the age-adjusted deaths. The following dimensions are State, Cause Name and 113 Cause Name which are string data types. States inform the analysts of the different states of each recorded death. Cause Name is the simplified version of the cause for each death, such as Heart disease or Kidney disease, while 113 Cause Name gives the full name for each cause along with the ICD-10 codes. Lastly the dataset also contains the Deaths and Age-adjusted Death Rate and these are number data types. Death is depicted in whole number form indicating the total number of deaths that are recorded and Age-adjusted Death Rate reflects the death rate per 100,000 people, adjusted for differences in age distribution across populations. After July 1, 2010 population used to compute death rates are estimated based on the 2010 census.

# Question 1

How do deaths and age-adjusted death rates vary across U.S. states, and which states show the highest and lowest rate? For the states with the highest and lowest age-adjusted death rates, what were the leading causes of death in 1999, 2005, 2011, and 2017?

This is an important question because it digs deeper into the public health inequality and risk factors across the U.S and it also narrows down the states with the highest and lowest age-adjusted deaths. By comparing the death rates of the highest and lowest over time we can see how the states are either improving or worsening. Comparing data for 1999, 2005, 2011, and 2017 enables us to see long-term progress or decline. This question also goes into the economical impact that might be required after analyzing this data. We visualized this in Tableau with a map to see the highest and lowest rates that could assist policymakers decide cost-effective interventions and effective health policies. 

<img width="2442" height="1360" alt="image" src="https://github.com/user-attachments/assets/0a299cdc-20e1-4987-bbee-767545e23c8a" />

<img width="2442" height="1360" alt="image" src="https://github.com/user-attachments/assets/da3e0af3-f487-4e19-b347-b91b3716477e" />

## Data Manipulation

There was no data manipulation necessary for this question. The question used the minimal and standard data preparation steps that are given to us by Tableau. The data is filtered to only use the specific years 1999, 2005, 2011, and 2017 as well as filtering Hawaii and Mississippi as the lowest and highest age-adjusted death rates states. The data was also aggregated using the SUM functions in order to compare overall death counts and age-adjusted rates across the states.

## Analysis

We mapped out the total death amount as well as the age-adjusted death rates by state from 1999 to 2017 and compared the two maps. For the non-adjusted death count, California had the highest total with 8,169,513 deaths. On the other hand, Alaska had the lowest total of 117,890 deaths. This seems to make sense because California is known to have a significantly larger population than other states and the latter is true for states like Alaska that are less populated. To overcome this measured deception, there is an age-adjusted death rate in the dataset that takes the total number of deaths and divides it per 100,000 people based on the population’s ages. This gives us new data to work with as Mississippi now shows the highest rate (33,327 deaths) and Hawaii shows the lowest rate (20,723). The leading causes for both rates were shown to be heart disease and cancer. The main takeaway from this analysis is that standardization is important in accurately showing impressions on health outcomes across America. To conclude, age-adjusted rates standardize for population age structure, making comparisons fair across states with different demographics.

# Question 2

Have any causes of death had an increase in rates over the past decade, what are those rates, and what are they projected to increase over the next 8 years?

This question is important because it exposes on a national level what causes of death are still most prevalent and worsening. If you look at an aggregate death rate analysis, it seems that the rates have decreased over time, but we wanted to take a closer look to see where the problem still lies. The question provides information on what underlying issues in society might still be posing issues, and what macro factor will be impacted most. For example, with suicide, do we need more investment in therapy and personal care resources? With Alzheimer's, will we need to prepare for more memory care facility capacity? It provides information on where further investments need to be made to prepare, and what areas need to be focused on in reducing the rates for the future. 

<img width="2446" height="1362" alt="image" src="https://github.com/user-attachments/assets/31e9f3a3-73e6-4270-b181-94e790fd6438" />

<img width="2442" height="1360" alt="image" src="https://github.com/user-attachments/assets/024981a2-1974-4633-a815-5a6a6eb02640" />

## Data Manipulation

We Performed an 8 year forecast to see the projected numbres at the current rate of increase. We also had to change the age-adjusted death rate from sum to average to make sure the rate was accurate. This value was already a rate of increase, so having sum was incorrect. We then filtered down the data heavily to ensure a forecast could be completed. Initially, a forecast wasn't possible due to the amount of data. We created a slope value to determine which rate of increase was most valid.

WINDOW_CORR(
    INDEX(),
    SUM([Age-adjusted Death Rate])
)

## Analysis

When looking at the full forecast chart, unintentional injuries have risen from 38.24 to 52.27 deaths per 100,000, with a forecasted increase to 56.63 at an annual growth rate of 2.04%. This trend may be driven by factors such as distracted driving, increased falls among the elderly, and rising overdose incidents, suggesting a need for stronger prevention efforts. Alzheimer’s disease shows an even sharper increase, climbing from 17.48 to 30.91 and projected to reach 36.34, growing at 4.27% per year. As people live longer and research continues to improve, communities will need to expand memory-care capacity and support systems. Suicide rates have also grown—from 11.74 to 15.54 with a forecast of 18.27—reflecting a 1.8% annual increase and highlighting the need for expanded mental-health resources, therapists, and community supports. A key limitation of this analysis is that the dataset does not provide the underlying causes driving these trends, which restricts deeper interpretation
