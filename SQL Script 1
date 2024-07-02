--management wants to see all the users that did not login in the past 5 months


--5 months back the date would be 2024-02-02 10:36:55
--so we need to find the users who logged in before this date time 
---first we will get the max and latest login date time for each user and compare that with above date 

select user_id, max(login_timestamp)--dateadd(month,-5,getdate()) 
from logins
group by user_id
having max(login_timestamp) < dateadd(month,-5,getdate())

select * from logins
---2nd approach 

select distinct user_id from logins where user_id not in (
  select user_id from logins where login_timestamp > dateadd(month,-5,getdate())
)
