##### **date \& time :**

**-----------------**

**Now():** it returns current time and date

Ex: select now();



Curdate(): it returns the current date only.

select curdate();



curtime(): it returns the current time only.

select curtime();



year(): it is used to extract the year in a date.

select year(curdate());



Month(): it is used to extract the month in a date.

select month(curdate());



day(): it is used to extract the day in a date.

select day(curdate());



dayName(): it extract the day in a date and return day name.

select dayName(curdate());



daydiff(): it returns different two dates.



date\_add(): it is used to add the days, months or year in a date.

syntax: select date\_add(curdate(), interval value);

select date\_add(curdate(), interval 10 day);



date\_sub(): it is used subtract the days, months or year in a date.

syntax: select date\_sub(curdate(), interval 10 day);



date\_format(): 

select curdate(); // 2026-08-21

select date\_format(curdate(), '%d%m%y');



str\_to\_date: to convert string into a date.

select str\_to\_date('19-0-2026', '%y%m%d');



system():

\------------------------------------------------------------------------------------

version():

\----------

select version();



database():

\----------

select database();



user():

\-------

return the current username and host



current\_user():

\------------------

return current username.



connection\_id():

\----------------

select connection\_id();



last\_insert\_id():

\--------------------

select last\_insert\_id();



























































































































































































