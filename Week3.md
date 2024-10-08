# Relational-Databases
# Week 3 Exercise 2
Qn1.
select *from goal;

<img width="816" alt="Screenshot 2024-10-08 at 1 10 15 PM" src="https://github.com/user-attachments/assets/a7d855a3-de66-4cdf-a52a-14ac8c58d780">

Qn2.
select name from airport where iso_country = "FI";
<img width="486" alt="Screenshot 2024-10-08 at 1 13 20 PM" src="https://github.com/user-attachments/assets/258fdeb5-aedc-486d-8e65-f45d2ac09f33">
<img width="383" alt="Screenshot 2024-10-08 at 1 13 46 PM" src="https://github.com/user-attachments/assets/ceef7b93-b946-4060-bf2c-5d376cedfb89">

Qn3.
select name from airport where iso_country = "FI" order by name;
<img width="514" alt="Screenshot 2024-10-08 at 1 16 13 PM" src="https://github.com/user-attachments/assets/b799ee83-ad38-4fbb-887b-9e62796f1449">
<img width="378" alt="Screenshot 2024-10-08 at 1 16 34 PM" src="https://github.com/user-attachments/assets/5695bbb5-ca6a-4748-907e-0a874690dd6a">

Qn4.
select name, type from airport where iso_country = "FI" order by type, name;
<img width="597" alt="Screenshot 2024-10-08 at 1 22 56 PM" src="https://github.com/user-attachments/assets/3189ba88-1498-4da1-b277-dbe936e4ea73">
<img width="508" alt="Screenshot 2024-10-08 at 1 23 13 PM" src="https://github.com/user-attachments/assets/c259cf29-56c1-421a-90d8-3fdf320a73ce">

Qn5.
select name from country where name like "F%";
<img width="409" alt="Screenshot 2024-10-08 at 1 24 12 PM" src="https://github.com/user-attachments/assets/71204ded-27a7-4958-9e9e-2806937b5304">

Qn6.
select name from country where name like "%F%"
<img width="412" alt="Screenshot 2024-10-08 at 1 25 01 PM" src="https://github.com/user-attachments/assets/54ee46a9-0aff-4184-9ae8-03c1d443288a">

Qn7.
select location from game where screen_name = "Vesa";
<img width="442" alt="Screenshot 2024-10-08 at 1 25 55 PM" src="https://github.com/user-attachments/assets/d2efcacf-5b24-4204-a4ee-775322e99f56">

Qn8.
select co2_consumed from game where screen_name = "Ilkka";
<img width="472" alt="Screenshot 2024-10-08 at 1 26 33 PM" src="https://github.com/user-attachments/assets/6baef5f6-d26e-4802-806d-7b8a070cae93">

Qn9.
select distinct co2_budget from game;
<img width="333" alt="Screenshot 2024-10-08 at 1 27 13 PM" src="https://github.com/user-attachments/assets/1ef3f9f0-b43c-4948-9ae1-688e43e6ffc7">

Qn10.
select screen_name, co2_budget, co2_consumed, co2_budget - co2_consumed as co2_left from game where screen_name = "Ilkka";
<img width="930" alt="Screenshot 2024-10-08 at 2 26 58 PM" src="https://github.com/user-attachments/assets/7cbff048-7f07-4615-ac1b-d9fbfc14fafe">

