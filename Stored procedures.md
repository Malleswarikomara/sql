Stored procedures:

\------------------

Procedures is a group of sql statement. it is used to store the group of sql statement inside the datebase.

The main purpose of stored procedure is used to code reusability.



Procedure syntax:

\----------------

delimiter //

create procedure procedure\_name()

begin 

&#x20;

write sql statements



end //

delimiter;





How to call the procedure:

\--------------------------

call procedure\_name();



procedure status:

\----------------

show procedure status where db ='databasename';





Example:

delimiter //

create procedure empDetails()

begin

select \* from employee;

end //

delimiter;







with parameter stored procedure:

\-------------------------------

in : the procedure take the input.

out : return the output

inout : take and return output.





delimiter //

create procedure empIDDetails(in empId int)

begin 

select \* from employee where emp\_id= empId;

end //

delimiter ;









Out: the procedure return a value.



delimiter //

create procedure empCount(out cemp int)

begin

select count(\*) into cemp from employee;

end //

delimiter ;



call empCount(@cemp);

select @cemp;





inout:

\------

The procedure take input and return output.



delimiter //

create procedure salaryUpdate(in Eid int, inout

&#x20;esal decimal(10,2))

begin

update employee set salary = salary+5000 where emp\_id =Eid;

select salary into esal from employee where emp\_id =Eid;

end //

delimiter ;



































