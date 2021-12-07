##virtual-assistant-service

Change database configuration in application.properties

#### Get TOPICS

http://localhost:8080/modeln/topics/

`["Job","Users"]`

http://localhost:8080/modeln/topics/Job

`["History"]`


####Get Questions


http://localhost:8080/modeln/questions/Job

`[{"Q1":{"id":1,"displayName":"Get status of a Job","userInputText":"Enter job Name","sqlQuery":"select STATUS as Response from TECMF_SCHEDULER_STATUS where jobname=? order by jobstatusid desc OFFSET  1 ROWS FETCH NEXT 1 ROWS ONLY"}},{"Q2":{"id":2,"displayName":"Get Last Run time of a Job","userInputText":"Enter job Name","sqlQuery":"select status from job_table where job_id=?"}},{"Q3":{"id":3,"displayName":"Get scheduled Time","userInputText":"Enter job Name","sqlQuery":"select time from job_table where job_id=?"}},{"Q4":{"id":4,"displayName":"is LICENSE Active","userInputText":"Enter LICENSE ID","sqlQuery":"select IsActive as Response from TECMF_LICENSE where licenseid=?"}}]`


http://localhost:8080/modeln/questions/Job/History

`[{"Q1":{"id":1,"displayName":"Get Job data archieved time","userInputText":"Enter job Name","sqlQuery":"select date from job_table_hist where job_id=?"}},{"Q2":{"id":2,"displayName":"Number of time a job ran today","userInputText":"Enter job Name","sqlQuery":"select count(*) from job_table where job_id=? and date=curr_date()"}}]`

#### Response
##### Get License Status

http://localhost:8080/modeln/response/Job/4?inputText=1073743104

`1`

#####Get Jobs Status

http://localhost:8080/modeln/response/Job/1?inputText=RoNotificationDispatcher

`Error`