# Exercise 4
qn1.
select country.name as "country name", airport.name as "airport name"
from country inner join airport on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled_service = "yes";
<img width="596" alt="Screenshot 2024-10-08 at 2 51 13 PM" src="https://github.com/user-attachments/assets/63cb1d4d-f9c5-45c0-8fdd-dadbc85accd6">

qn2.
SELECT screen_name, airport.name
FROM game inner join airport on location=ident;
<img width="390" alt="Screenshot 2024-10-08 at 2 52 01 PM" src="https://github.com/user-attachments/assets/09bf7b9a-f6a9-4e4d-bfaf-76645c55b306">

qn3.
select screen_name, country.name
from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;
<img width="851" alt="Screenshot 2024-10-08 at 2 52 51 PM" src="https://github.com/user-attachments/assets/c4822971-2ac9-4d04-9463-3e7b3ce95642">

qn4.
select airport.name, screen_name
from airport left join game on ident = location where name like "%Hels%";
<img width="565" alt="Screenshot 2024-10-08 at 2 53 53 PM" src="https://github.com/user-attachments/assets/84ff8303-5918-43e0-a2b7-6b5133def6dc">

qn5.
select name, screen_name
from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;
<img width="709" alt="Screenshot 2024-10-08 at 2 54 33 PM" src="https://github.com/user-attachments/assets/a844c7c8-ac79-4b66-9bc3-a0e6bcf888f3">

# Exercise 5
qn1.
select name 
from country
where iso_country in(
select iso_country
from airport 
where name like "%Satsuma%");
<img width="263" alt="Screenshot 2024-10-08 at 3 02 00 PM" src="https://github.com/user-attachments/assets/76ba82fd-51f1-4647-bc07-9dd6f3f4dd64">

qn2.
select name
from airport
where iso_country in(
select iso_country
from country
where name = "Monaco");
<img width="267" alt="Screenshot 2024-10-08 at 3 02 38 PM" src="https://github.com/user-attachments/assets/906f7587-6827-4a78-8c74-ec47827a2c62">

qn3.
select screen_name
from game
where id in(
select goal_id
from goal_reached
where goal_id in(
select id
from goal
where name = "CLOUDS"));
<img width="214" alt="Screenshot 2024-10-08 at 3 03 52 PM" src="https://github.com/user-attachments/assets/1e596c72-38a4-4f2c-9cd0-3205d8c88d12">

qn4.
select country.name
from country
where iso_country not in(
select airport.iso_country
from airport
);
<img width="248" alt="Screenshot 2024-10-08 at 3 04 33 PM" src="https://github.com/user-attachments/assets/812689b3-ff01-4389-987d-81349e732834">

qn5.
select name
from goal
where id not in(
select goal_id
from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = "Heini"
);
<img width="551" alt="Screenshot 2024-10-08 at 3 05 19 PM" src="https://github.com/user-attachments/assets/66a119c1-79a0-4e01-9d99-a13521d3c379">
