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

We need to identify students who possess skills in both Python and SQL. Students with three skills should not be considered in this context.

My own solution:

with myfun as(select *,
case when skill="python" then 1
when skill="sql" then 2
else 3
end as ans
from stu)
select student_id from myfun group by student_id having count(student_id)>1 and sum(ans)=3;



