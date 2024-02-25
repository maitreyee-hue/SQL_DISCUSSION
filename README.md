# SQL_DISCUSSION
I am posting here sql questions and answers of my own solution which are very important and specially I liked it while solving. 


Question no 1:
Table :
create table students  (
student_id int,
skill varchar(20)
);

insert into students values
(1,'sql'),(1,'python'),(1,'tableau'),(2,'sql'),(3,'sql'),(3,'python'),(4,'tableau'),(5,'python'),(5,'tableau')

this is table given for students with their subject and values. We have to find only those students who have skills of python and sql only. If any student has 3 skills that also should not taken into consideration

My own solution:

with myfun as(select *,
case when skill="python" then 1
when skill="sql" then 2
else 3
end as ans
from stu)
select student_id from myfun group by student_id having count(student_id)>1 and sum(ans)=3;



