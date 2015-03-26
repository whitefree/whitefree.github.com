#Salesforce如何将搜索结果写入csv文件并发邮件
***
##Search by SOQL
	AggregateResult[] duplicateInfo = [select pse__Resource__c, 
						  pse__End_Date__c, 										      
						  SUM(pse__Total_Hours__c), 
						  MIN(pse__Project__c)
					   from pse__Timecard_Header__c
					   group by pse__Resource__c, pse__End_Date__c
					   HAVING  COUNT(Id) > 1];
##soql is very similar with 
***
