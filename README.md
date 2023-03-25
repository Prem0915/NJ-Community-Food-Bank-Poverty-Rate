# NJ-Community-Food-Bank-Poverty-Rate
Regression analysis to predict poverty rate in a county based on demographics and economic factors of a county

Problem Description
The Community Food Bank of New Jersey is leader in raising awareness of hunger and
poverty in New Jersey. Organization brings all sectors of our society together to provide the
short-term responses and the long-term solutions. Company’s main mission is to alleviate
the direct effects of hunger and poverty in US.
Current project is to predict poverty across the United States at the county-level from other
socioeconomic indicators. The data is compiled from a wide range of sources and made
publicly available by the United States Department of Agriculture Economic Research
Service (USDA ERS).
Target Variable & Context
We're trying to predict the variable poverty_rate, which represents percentage (between 0.0
and 100.0) of a county's population meeting the criteria of poverty:
In the United States, being in poverty is officially defined as having an
income below a federally determined poverty threshold. Poverty thresholds
were developed in the 1960s and are adjusted annually to account for
inflation. They represent the Federal Government’s estimate of the point
below which a family of a given size has cash income insufficient to meet
basic needs. Any family/individual with total income less than an amount
deemed to be sufficient to purchase food, shelter, clothing, and other
essential goods and services is classified as poor. (For details, see "How the
Census Bureau Measures Poverty.")
The amount of income necessary to purchase these basic needs is set by
the Office of Management and Budget (OMB). The 2016 poverty line was
$12,486 for an individual under 65 years of age and $11,511 for those 65
years or older. The poverty line for a three-person family with one child and
two adults was $19,318 in 2016; for a family with two adults and three
children the poverty line was $28,643. For a complete list of poverty lines by
size of family and number of children, see the U.S. Census Bureau's tables
of Poverty Thresholds.)

Features
There are 33 variables in this dataset. Each row in the dataset represents a United States
county, and the dataset we are working with covers two particular years, denoted a,
and b We don't provide a unique identifier for an individual county, just a row_id for each
row.
The variables in the dataset have names that of the form category__variable,
where category is the high level category of the variable (e.g. econ or health). variable is
what the specific column contains.
Categories
A R E A — INFORMATI ON ABOUT THE COUNTY

• area__rucc — Rural-Urban Continuum Codes "form a classification scheme that
distinguishes metropolitan counties by the population size of their metro area, and
nonmetropolitan counties by degree of urbanization and adjacency to a metro area.
The official Office of Management and Budget (OMB) metro and nonmetro categories
have been subdivided into three metro and six nonmetro categories. Each county in
the U.S. is assigned one of the 9 codes." (USDA Economic Research Service,
https://www.ers.usda.gov/data-products/rural-urban-continuum-codes/)
• area__urban_influence — Urban Influence Codes "form a classification scheme that
distinguishes metropolitan counties by population size of their metro area, and
nonmetropolitan counties by size of the largest city or town and proximity to metro
and micropolitan areas." (USDA Economic Research Service,
https://www.ers.usda.gov/data-products/urban-influence-codes/)
E C O N — E CONOMI C INDI CATORS

• econ__economic_typology — County Typology Codes "classify all U.S. counties
according to six mutually exclusive categories of economic dependence and six
overlapping categories of policy-relevant themes. The economic dependence types
include farming, mining, manufacturing, Federal/State government, recreation, and
nonspecialized counties. The policy-relevant types include low education, low
employment, persistent poverty, persistent child poverty, population loss, and
retirement destination." (USDA Economic Research Service,
https://www.ers.usda.gov/data-products/county-typology-codes.aspx)
• econ__pct_civilian_labor — Civilian labor force, annual average, as percent of
population (Bureau of Labor Statistics, http://www.bls.gov/lau/)

• econ__pct_unemployment — Unemployment, annual average, as percent of population
(Bureau of Labor Statistics, http://www.bls.gov/lau/)
• econ__pct_uninsured_adults — Percent of adults without health insurance (Bureau of
Labor Statistics, http://www.bls.gov/lau/)
• econ__pct_uninsured_children — Percent of children without health insurance (Bureau
of Labor Statistics, http://www.bls.gov/lau/)
H E A L T H — HE ALTH INDI CATORS

• health__pct_adult_obesity — Percent of adults who meet clinical definition of obese
(National Center for Chronic Disease Prevention and Health Promotion)
• health__pct_adult_smoking — Percent of adults who smoke (Behavioral Risk Factor
Surveillance System)
• health__pct_diabetes — Percent of population with diabetes (National Center for
Chronic Disease Prevention and Health Promotion, Division of Diabetes Translation)
• health__pct_low_birthweight — Percent of babies born with low birth weight (National
Center for Health Statistics)
• health__pct_excessive_drinking — Percent of adult population that engages in
excessive consumption of alcohol (Behavioral Risk Factor Surveillance System, )
• health__pct_physical_inacticity — Percent of adult population that is physically
inactive (National Center for Chronic Disease Prevention and Health Promotion)
• health__air_pollution_particulate_matter — Fine particulate matter in μg/m3 (CDC
WONDER, https://wonder.cdc.gov/wonder/help/pm.html)
• health__homicides_per_100k — Deaths by homicide per 100,000 population (National
Center for Health Statistics)
• health__motor_vehicle_crash_deaths_per_100k — Deaths by motor vehicle crash per
100,000 population (National Center for Health Statistics)
• health__pop_per_dentist — Population per dentist (HRSA Area Resource File)
• health__pop_per_primary_care_physician — Population per Primary Care Physician
(HRSA Area Resource File)
D E M O — DEMOGRAP HI CS INFORMATION

• demo__pct_female — Percent of population that is female (US Census Population
Estimates)
• demo__pct_below_18_years_of_age — Percent of population that is below 18 years of
age (US Census Population Estimates)
• demo__pct_aged_65_years_and_older — Percent of population that is aged 65 years or
older (US Census Population Estimates)
• demo__pct_hispanic — Percent of population that identifies as Hispanic (US Census
Population Estimates)

• demo__pct_non_hispanic_african_american — Percent of population that identifies as
African American (US Census Population Estimates)
• demo__pct_non_hispanic_white — Percent of population that identifies as Hispanic and
White (US Census Population Estimates)
• demo__pct_american_indian_or_alaskan_native — Percent of population that identifies
as Native American (US Census Population Estimates)
• demo__pct_asian — Percent of population that identifies as Asian (US Census
Population Estimates)
• demo__pct_adults_less_than_a_high_school_diploma — Percent of adult population
that does not have a high school diploma (US Census, American Community Survey)
• demo__pct_adults_with_high_school_diploma — Percent of adult population which has
a high school diploma as highest level of education achieved (US Census, American
Community Survey)
• demo__pct_adults_with_some_college — Percent of adult population which has some
college as highest level of education achieved (US Census, American Community
Survey)
• demo__pct_adults_bachelors_or_higher — Percent of adult population which has a
bachelor's degree or higher as highest level of education achieved (US Census,
American Community Survey)
• demo__birth_rate_per_1k — Births per 1,000 of population (US Census Population
Estimates)
• demo__death_rate_per_1k — Deaths per 1,000 of population (US Census Population
Estimates)
Example Row
Here's an example of one of the rows in the dataset so that you can see the kinds of values
you might expect in the dataset. Some are numeric, some are categorical, and there can be
missing values.
area__rucc

Nonmetro - Completely rural or less than 2,500 urban population,
adjacent to a metro area

area__urban_influence Noncore adjacent to a large metro area
econ__economic_typology Federal/State government-dependent
econ__pct_civilian_labor 0.358
econ__pct_unemployment 0.089
econ__pct_uninsured_adults 0.253
econ__pct_uninsured_children 0.099
demo__pct_female 0.494
demo__pct_below_18_years_of_age 0.2
demo__pct_aged_65_years_and_older 0.195
demo__pct_hispanic 0.044
demo__pct_non_hispanic_african_american 0.517
demo__pct_non_hispanic_white 0.378
demo__pct_american_indian_or_alaskan_native 0.056
demo__pct_asian 0
demo__pct_adults_less_than_a_high_school_diploma0.223896
demo__pct_adults_with_high_school_diploma 0.345382

demo__pct_adults_with_some_college 0.273092
demo__pct_adults_bachelors_or_higher 0.157631
demo__birth_rate_per_1k 10
demo__death_rate_per_1k 11
health__pct_adult_obesity 0.345
health__pct_adult_smoking 0.219
health__pct_diabetes 0.159
health__pct_low_birthweight 0.154
health__pct_excessive_drinking NaN
health__pct_physical_inacticity 0.317
health__air_pollution_particulate_matter 12
health__homicides_per_100k 9.33
health__motor_vehicle_crash_deaths_per_100k 33.75
health__pop_per_dentist 5429
health__pop_per_primary_care_physician 6949
yr b
References
• Economic Research Service (ERS), U.S. Department of Agriculture (USDA). Poverty

Series. https://www.ers.usda.gov/topics/rural-economy-population/rural-poverty-well-
being/poverty-overview.aspx.

• University of Wisconsin Population Health Institute. County Health Rankings &
Roadmaps. www.countyhealthrankings.org.
