# green-growth-oecd
The replication codes for my article published in Applied Economics 
"Do green growth and technological innovation matter to infrastructure investments in the era of climate change? Global evidence"
************************************************************************************************************************************************************
Major data sources can be publically accessed below
1. The OECD Green Growth database https://data-explorer.oecd.org/vis?lc=en&df[ds]=dsDisseminateFinalDMZ&df[id]=DSD_GG%40DF_GREEN_GROWTH&df[ag]=OECD.ENV.EPI&dq=AUS....&pd=2017%2C&to[TIME_PERIOD]=false
2. Global infrastructure investments https://outlook.gihub.org/
3. CO2 emissions are from https://databank.worldbank.org/source/world-development-indicators/preview/on 
   
Please find Table 1. Variables, codes, and definitions.
Variable	Label	Source
Infrastructure investment trend ($USD) – IIT	Infrastructure Investment Trend - IIT	https://outlook.gihub.org/
CO2 emissions (kt) – CO2	Climate Change - CC	WDIs-WB
Production-based CO2 productivity, GDP per unit of energy-related CO2 emission – PBCO2	Green growth – GG1	OECD statistics
Demand-based CO2 productivity, GDP per unit of energy-related CO2 emissions – DBCO2	Green growth – GG2	OECD statistics
Non-energy material productivity, GDP per unit of DMC – NEMP	Green growth – GG3	OECD statistics
Environmental-adjusted multifactor productivity growth – EAMFP	Green growth – GG4	OECD statistics
Mean population exposure to PM2.5 – MPEPM2.5	Green growth – GG5	OECD statistics
Development of environment-related technologies, % all technologies – DET	Technological innovation – TI1	OECD statistics
Relative advantage in environment-related technology – RAET	Technological innovation – TI2	OECD statistics
Development of environment-related technologies, % inventions worldwide – DETI	Technological innovation – TI3	OECD statistics
Development of environment-related technologies, inventions per capita – DETIPC	Technological innovation - – TI4	OECD statistics
Environmentally related government R&D budget, % total government R&D – EGRDB	Environment-related expenditure – ERE1	OECD statistics
National expenditure on environmental protection, % GDP – NEEP	Environment-related expenditure – ERE2	OECD statistics
Environmentally related Official Development Assistance - ODA, % total ODA – EODA	Environment-related expenditure – ERE3	OECD statistics
Environmentally related taxes, % GDP – ERT	Environmental-related taxes – ERT1	OECD statistics
Environmentally related taxes, % total tax revenue – ERTT	Environmental-related taxes – ERT2	OECD statistics
Energy-related tax revenue, % total environmental tax revenue – ERTR	Environmental-related taxes – ERT3	OECD statistics
Road transport-related tax revenue, % total environmental tax revenue – RTRTA	Environmental-related taxes – ERT4	OECD statistics

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
