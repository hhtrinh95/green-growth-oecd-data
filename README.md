# green-growth-oecd
The replication codes for my article published in Applied Economics 
"Do green growth and technological innovation matter to infrastructure investments in the era of climate change? Global evidence"

************************************************************************************************************************************************************
************************************************************************************************************************************************************
Owner: Hai Hong Trinh (Massey University, New Zealand)
Emails: h.h.trinh@massey.ac.nz; hai.hong.trinh.econfin@gmail.com
************************************************************************************************************************************************************
************************************************************************************************************************************************************

Do green growth and technological innovation matter to
infrastructure investments in the era of climate change?
Global evidence
Hai Hong Trinh, Michael McCord, Daniel Lo & Graham Squires
To cite this article: Hai Hong Trinh, Michael McCord, Daniel Lo & Graham Squires (2023)
Do green growth and technological innovation matter to infrastructure investments in
the era of climate change? Global evidence, Applied Economics, 55:35, 4108-4129, DOI:
10.1080/00036846.2022.2125493
To link to this article: https://doi.org/10.1080/00036846.2022.2125493

************************************************************************************************************************************************************
************************************************************************************************************************************************************
-> Intial processing steps
************************************************************************************************************************************************************
************************************************************************************************************************************************************
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\Merged_All.dta"
clear
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\Gihub USD & %GDP.dta", replace
clear
drop seriesname seriescode countrycode time
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\World Bank.dta", replace
clear
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\OECD stats.dta", replace
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\World Bank.dta"
gsort country year
tabulate country
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\World Bank.dta", replace
clear
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\OECD stats.dta"
gsort country year
tabulate country
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\OECD stats.dta", replace
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\Gihub USD & %GDP.dta"
gsort country year
tabulate country
clear
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\World Bank.dta"
gsort country year
tabulate country
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\World Bank.dta", replace
clear
************************************************************************************************************************************************************
************************************************************************************************************************************************************
-> Merge all datasets together
-> generate id for each country
************************************************************************************************************************************************************
************************************************************************************************************************************************************
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\Merged_All.dta"
generate 	id 	=	.						
replace 	id 	=	1	if 	country 	==	"Angola"
replace 	id 	=	2	if 	country 	==	"Argentina"
replace 	id 	=	3	if 	country 	==	"Australia"
replace 	id 	=	4	if 	country 	==	"Azerbaijan"
replace 	id 	=	5	if 	country 	==	"Bangladesh"
replace 	id 	=	6	if 	country 	==	"Benin"
replace 	id 	=	7	if 	country 	==	"Brazil"
replace 	id 	=	8	if 	country 	==	"Cambodia"
replace 	id 	=	9	if 	country 	==	"Canada"
replace 	id 	=	10	if 	country 	==	"Chile"
replace 	id 	=	11	if 	country 	==	"China"
replace 	id 	=	12	if 	country 	==	"Colombia"
replace 	id 	=	13	if 	country 	==	"Croatia"
replace 	id 	=	14	if 	country 	==	"Côte d'Ivoire"
replace 	id 	=	15	if 	country 	==	"Ecuador"
replace 	id 	=	16	if 	country 	==	"Egypt"
replace 	id 	=	17	if 	country 	==	"Ethiopia"
replace 	id 	=	18	if 	country 	==	"France"
replace 	id 	=	19	if 	country 	==	"Germany"
replace 	id 	=	20	if 	country 	==	"Ghana"
replace 	id 	=	21	if 	country 	==	"Guinea"
replace 	id 	=	22	if 	country 	==	"India"
replace 	id 	=	23	if 	country 	==	"Indonesia"
replace 	id 	=	24	if 	country 	==	"Italy"
replace 	id 	=	25	if 	country 	==	"Japan"
replace 	id 	=	26	if 	country 	==	"Jordan"
replace 	id 	=	27	if 	country 	==	"Kazakhstan"
replace 	id 	=	28	if 	country 	==	"Kenya"
replace 	id 	=	29	if 	country 	==	"Korea"
replace 	id 	=	30	if 	country 	==	"Malaysia"
replace 	id 	=	31	if 	country 	==	"Mexico"
replace 	id 	=	32	if 	country 	==	"Morocco"
replace 	id 	=	33	if 	country 	==	"Myanmar"
replace 	id 	=	34	if 	country 	==	"New Zealand"
replace 	id 	=	35	if 	country 	==	"Nigeria"
replace 	id 	=	36	if 	country 	==	"Pakistan"
replace 	id 	=	37	if 	country 	==	"Paraguay"
replace 	id 	=	38	if 	country 	==	"Peru"
replace 	id 	=	39	if 	country 	==	"Philippines"
replace 	id 	=	40	if 	country 	==	"Poland"
replace 	id 	=	41	if 	country 	==	"Romania"
replace 	id 	=	42	if 	country 	==	"Russia"
replace 	id 	=	43	if 	country 	==	"Rwanda"
replace 	id 	=	44	if 	country 	==	"Saudi Arabia"
replace 	id 	=	45	if 	country 	==	"Senegal"
replace 	id 	=	46	if 	country 	==	"Singapore"
replace 	id 	=	47	if 	country 	==	"South Africa"
replace 	id 	=	48	if 	country 	==	"Spain"
replace 	id 	=	49	if 	country 	==	"Tanzania"
replace 	id 	=	50	if 	country 	==	"Thailand"
replace 	id 	=	51	if 	country 	==	"Tunisia"
replace 	id 	=	52	if 	country 	==	"Turkey"
replace 	id 	=	53	if 	country 	==	"United Kingdom"
replace 	id 	=	54	if 	country 	==	"United States"
replace 	id 	=	55	if 	country 	==	"Uruguay"
replace 	id 	=	56	if 	country 	==	"Viet Nam"
save "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\Merged_All.dta", replace
clear
use "H:\Infrastructure Investment and Green Growth - A cross-country study (Trinh, Squiers, McCord, Javed, Lo) for JPIF\Data\Gihub USD & %GDP.dta"
generate 	id 	=	.						
replace 	id 	=	1	if 	country 	==	"Angola "
replace 	id 	=	2	if 	country 	==	"Argentina "
replace 	id 	=	3	if 	country 	==	"Australia "
replace 	id 	=	4	if 	country 	==	"Azerbaijan"
replace 	id 	=	5	if 	country 	==	"Bangladesh"
replace 	id 	=	6	if 	country 	==	"Benin"
replace 	id 	=	7	if 	country 	==	"Brazil"
replace 	id 	=	8	if 	country 	==	"Cambodia"
replace 	id 	=	9	if 	country 	==	"Canada "
replace 	id 	=	10	if 	country 	==	"Chile"
replace 	id 	=	11	if 	country 	==	"China"
replace 	id 	=	12	if 	country 	==	"Colombia"
replace 	id 	=	13	if 	country 	==	"Croatia"
replace 	id 	=	14	if 	country 	==	"Côte d'Ivoire"
replace 	id 	=	15	if 	country 	==	"Ecuador "
replace 	id 	=	16	if 	country 	==	"Egypt"
replace 	id 	=	17	if 	country 	==	"Ethiopia"
replace 	id 	=	18	if 	country 	==	"France "
replace 	id 	=	19	if 	country 	==	"Germany "
replace 	id 	=	20	if 	country 	==	"Ghana"
replace 	id 	=	21	if 	country 	==	"Guinea"
replace 	id 	=	22	if 	country 	==	"India "
replace 	id 	=	23	if 	country 	==	"Indonesia"
replace 	id 	=	24	if 	country 	==	"Italy"
replace 	id 	=	25	if 	country 	==	"Japan "
replace 	id 	=	26	if 	country 	==	"Jordan"
replace 	id 	=	27	if 	country 	==	"Kazakhstan"
replace 	id 	=	28	if 	country 	==	"Kenya"
replace 	id 	=	29	if 	country 	==	"Korea"
replace 	id 	=	30	if 	country 	==	"Malaysia "
replace 	id 	=	31	if 	country 	==	"Mexico"
replace 	id 	=	32	if 	country 	==	"Morocco"
replace 	id 	=	33	if 	country 	==	"Myanmar"
replace 	id 	=	34	if 	country 	==	"New Zealand"
replace 	id 	=	35	if 	country 	==	"Nigeria"
replace 	id 	=	36	if 	country 	==	"Pakistan "
replace 	id 	=	37	if 	country 	==	"Paraguay"
replace 	id 	=	38	if 	country 	==	"Peru"
replace 	id 	=	39	if 	country 	==	"Philippines"
replace 	id 	=	40	if 	country 	==	"Poland "
replace 	id 	=	41	if 	country 	==	"Romania"
replace 	id 	=	42	if 	country 	==	"Russia"
replace 	id 	=	43	if 	country 	==	"Rwanda"
replace 	id 	=	44	if 	country 	==	"Saudi Arabia"
replace 	id 	=	45	if 	country 	==	"Senegal"
replace 	id 	=	46	if 	country 	==	"Singapore"
replace 	id 	=	47	if 	country 	==	"South Africa"
replace 	id 	=	48	if 	country 	==	"Spain"
replace 	id 	=	49	if 	country 	==	"Tanzania"
replace 	id 	=	50	if 	country 	==	"Thailand "
replace 	id 	=	51	if 	country 	==	"Tunisia"
replace 	id 	=	52	if 	country 	==	"Turkey "
replace 	id 	=	53	if 	country 	==	"United Kingdom "
replace 	id 	=	54	if 	country 	==	"United States "
replace 	id 	=	55	if 	country 	==	"Uruguay"
replace 	id 	=	56	if 	country 	==	"Viet Nam"

save "H:\Do green growth and technological innovation matter to infrastructure investments in the era of climate change - Global evidence.dta"
************************************************************************************************************************************************************
************************************************************************************************************************************************************
use  "H:\Do green growth and technological innovation matter to infrastructure investments in the era of climate change - Global evidence.dta"

**# Declare panel data

. xtset country_n year

Panel variable: country_n (unbalanced)
 Time variable: year, 2000 to 2020
         Delta: 1 year


************************************************************************************************************************************************************
************************************************************************************************************************************************************
**# Table 2. Summary statistics.
************************************************************************************************************************************************************
************************************************************************************************************************************************************
tabstat investmentneedusd investmentneedincsdgsusd investmentneedgdp investmentneedincsdgsgdp currenttrendsusd currenttrendsgdp logIIT CO2 logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA, columns(stats) stats(n mean min p50 max sd)


Variable	N	Mean	Min	p50	Max	SD
						
Investment need $USD	784	36600000000.00	172000000.00	9410000000.00	928000000000.00	103000000000.00
Investment need SDG $USD	784	37400000000.00	172000000.00	9710000000.00	931000000000.00	103000000000.00
Investment need %GDP	784	4.64	0.99	3.82	25.85	3.34
Investment need SDG %GDP	784	5.25	0.99	3.83	41.68	5.05
Current investment trends $USD	1164	36300000000.00	172000000.00	9620000000.00	872000000000.00	104000000000.00
Current investment trends %GDP	784	4.16	0.99	3.55	25.36	2.76
logIIT	1164	22.96	18.97	22.99	27.49	1.60
CO2	1170	475776.60	520.71	98257.27	10300000.00	1295041.00
logCO2	1170	11.38	6.26	11.50	16.15	1.98
PBCO2	1171	6.23	1.20	5.30	21.36	3.38
DBCO2	1145	4.12	1.78	4.03	7.32	1.16
NEMP	1171	1.80	0.25	1.35	7.92	1.47
EAMP	1150	0.77	-6.85	1.09	10.16	1.77
MPEPM25	1171	30.27	5.98	24.81	95.84	18.24
DET	1171	9.36	0.00	8.20	100.00	10.54
RAET	1171	1.02	0.00	0.93	14.06	1.18
DETI	1171	1.48	0.00	0.02	31.97	4.88
DETIPC	1171	4.62	0.00	0.13	76.91	12.01
EGRDB	1150	3.22	0.09	3.52	17.66	2.17
NEEP	812	1.84	1.02	1.89	2.58	0.27
EODA	1129	21.24	0.06	16.00	54.09	14.87
ERT	1150	1.37	-1.53	1.29	4.22	0.90
ERTT	1150	5.82	-12.14	6.05	20.87	4.03
ERTR	1150	55.18	-73.69	60.29	243.74	32.84
RTRTA	1150	40.91	-141.04	35.88	155.82	32.03

************************************************************************************************************************************************************
************************************************************************************************************************************************************
**# Table 6. Regression of infrastructure on climate change and green growth indicators.
************************************************************************************************************************************************************
************************************************************************************************************************************************************
xtreg logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA i.year i.country_n , fe vce(cluster country_n)

xtreg logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA i.year,  pa

xtreg logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA i.year, be

reg logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA i.year i.country_n, robust

xtpcse logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA

xtregar logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA

xtdpdsys logIIT logCO2 PBCO2 DBCO2 NEMP EAMP MPEPM25 DET RAET DETI DETIPC EGRDB NEEP EODA ERT ERTT ERTR RTRTA
