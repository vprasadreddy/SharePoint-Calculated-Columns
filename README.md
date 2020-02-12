# SharePoint-Calculated-Columns
## Calculated Formula For Fiscal Year Quarter
### SubmittedDate is SharePoint column name
=IF(ISBLANK([SubmittedDate]), "N/A", 
IF(AND(YEAR([SubmittedDate])<=2019, MONTH([SubmittedDate])<4),CONCATENATE("Q1",YEAR([SubmittedDate])),
IF(AND(YEAR([SubmittedDate])<=2019, MONTH([SubmittedDate])<7),CONCATENATE("Q2",YEAR([SubmittedDate])),
IF(AND(YEAR([SubmittedDate])<=2019, MONTH([SubmittedDate])<10),CONCATENATE("Q3",YEAR([SubmittedDate])),
IF(AND(YEAR([SubmittedDate])<=2019, MONTH([SubmittedDate])<=12),CONCATENATE("Q4",YEAR([SubmittedDate])),
IF(MONTH([SubmittedDate])<5,CONCATENATE("T1",YEAR([SubmittedDate])),
IF(MONTH([SubmittedDate])<9,CONCATENATE("T2",YEAR([SubmittedDate])),
IF(MONTH([SubmittedDate])<=12,CONCATENATE("T3",YEAR([SubmittedDate])),
""))))))))
