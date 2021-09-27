# azure-autoshutdown
Improved version of azure scheduling runbook by automys (https://github.com/automys/Azure-Automation-Scheduled-VM-Shutdown).

New Feature.
1. ability to specify a date to end the schedule. After the specific date the instances will no longer start.To activate the feature an additional tag is endDate has to be added to the Resource Group or the instance
 
To schedule instances using this runbook Tag the instance/Resource group with following tags
1. AutoShutdownSchedule
    This is the main tag of the runbook. The format of the tag is as follows.
    
   1. to keep the instance shutdown between 08.00 PM and 02.00 AM  the tag value should be 20:00 -> 02:00
   2. to keep the instance shutdown on specific days ( ex- weekends ) tag should be saturday,sunday, etc
   3. to keep the instance down specific time period plus specific days ( example - out of hours in weekdays and weekends ) 18:00 -> 09:00, saturday, sunday

2. endDate
   This tag will determine the last date the environment will be turned on based on the previous tag. If you need your instance up until the 02nd October 2021 you should add an endDate tag with the value "October 02 2021" along side the AutoShutdownSchedule tag
