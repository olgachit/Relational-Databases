# Exercise 6
qn1.
select max(elevation_ft)
from airport;
<img width="231" alt="Screenshot 2024-10-08 at 3 11 52 PM" src="https://github.com/user-attachments/assets/d628332e-c02e-4674-8374-36367a124434">

qn2.
select continent, count(*)
from country
group by continent;
<img width="258" alt="Screenshot 2024-10-08 at 3 12 43 PM" src="https://github.com/user-attachments/assets/2be774d0-8952-485c-843f-7bf5daa99999">

qn3.
select screen_name, count(*)
from game, goal_reached
where id = game_id
group by screen_name;
<img width="254" alt="Screenshot 2024-10-08 at 3 13 23 PM" src="https://github.com/user-attachments/assets/bd8b692f-004d-4770-845a-c6bf81d35f38">

qn4.
select screen_name
from game
where co2_consumed in(
select min(co2_consumed)
from game);
<img width="230" alt="Screenshot 2024-10-08 at 3 13 50 PM" src="https://github.com/user-attachments/assets/d78e9bc6-05e8-4ae9-818c-e0a2714eca53">

qn5.
select country.name, count(*)
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
order by count(*) desc
limit 50;
<img width="400" alt="Screenshot 2024-10-08 at 3 10 23 PM" src="https://github.com/user-attachments/assets/0b2ffce7-5b2f-4191-8118-8f7be2b862a4">

qn6.
select country.name
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
having count(*) > 1000;
<img width="390" alt="Screenshot 2024-10-08 at 3 14 36 PM" src="https://github.com/user-attachments/assets/50143615-7455-406f-87f4-97314e41f148">

qn7.
select airport.name
from airport
where elevation_ft in(
select max(elevation_ft)
from airport);
<img width="235" alt="Screenshot 2024-10-08 at 3 15 20 PM" src="https://github.com/user-attachments/assets/87b4c41a-7c89-423f-8039-f63e36452edb">

qn8.
select name
from country
where iso_country in(
select iso_country
from airport
where elevation_ft in(
select max(elevation_ft)
from airport));
<img width="229" alt="Screenshot 2024-10-08 at 3 15 57 PM" src="https://github.com/user-attachments/assets/008a7d54-062b-4c0a-806c-277996597e9f">

qn9.
select count(*)
from goal_reached, game
where id = game_id and screen_name = "Vesa"
group by screen_name;
<img width="365" alt="Screenshot 2024-10-08 at 3 16 53 PM" src="https://github.com/user-attachments/assets/df9cc96b-d7a7-44db-afcd-8f5e756e1135">

qn10.
select name
from airport
where latitude_deg in(
select min(latitude_deg)
from airport
);
<img width="244" alt="Screenshot 2024-10-08 at 3 17 29 PM" src="https://github.com/user-attachments/assets/ba135d0a-e2fd-4f62-a277-ac2b89d15dc5">

# Exercise 7
qn1.
update game
set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
where screen_name = "Vesa";
select * from game;
<img width="440" alt="Screenshot 2024-10-08 at 3 28 07 PM" src="https://github.com/user-attachments/assets/f87f3481-49be-4cdf-8111-1311a1f8ae78">
