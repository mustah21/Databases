# Week 3 exercise 2---Single table queries

Q1. select * from goal;
![Screenshot 2024-09-15 152400](https://github.com/user-attachments/assets/9c5e3ec1-506d-44e7-bfe1-8654dac82946)

Q2. select name, type from airport where iso_country = "FI";
![Screenshot 2024-09-15 152442](https://github.com/user-attachments/assets/f5f707df-9a75-40a6-aaa9-af5863378b60)

Q3. select name from airport where iso_country = "FI" order by name;
![Screenshot 2024-09-15 152510](https://github.com/user-attachments/assets/64d2d290-04d9-46aa-a0ed-39a2e836765f)

Q4. select name, type from airport where iso_country = "FI" order by type, name;
![Screenshot 2024-09-15 152547](https://github.com/user-attachments/assets/5626d160-71b5-44fe-8fa0-3674188ac11f)

Q5. select name from country where name like "F%"
![Screenshot 2024-09-15 152828](https://github.com/user-attachments/assets/230c4957-58fe-4858-8bb3-5ce98dc597a0)

Q6. select name from country where name like "%F%";
![Screenshot 2024-09-15 152902](https://github.com/user-attachments/assets/0539bc20-3529-419d-bf77-c2e71440e3cf)

Q7. select location from game where name = "Vesa";
![Screenshot 2024-09-15 152946](https://github.com/user-attachments/assets/3a5103f9-8261-4894-bfe4-6cf2eec49a0e)

Q8. select co2_consumed from game where screen_name = "Ilkka";
![Screenshot 2024-09-15 153047](https://github.com/user-attachments/assets/9856f0ec-bc51-4667-a63e-f9d74eaf9aad)

Q9. select distinct co2_budget from game;
![Screenshot 2024-09-15 153108](https://github.com/user-attachments/assets/4e8d3088-fb6d-4f9e-96db-f5c74ba61e86)

Q10. select screen_name, co2_budget, co2_consumed, (co2_budget - co2_consumed) As co2_difference from game where screen_name = "Ilkka";
![Screenshot 2024-09-15 153146](https://github.com/user-attachments/assets/02d0117f-9346-4a3b-8896-25da78a5f121)


#  Week 3 exercise 3---Multiple data queries 


Q1.  select country.name as "Country name", airport.name as "Aiport name" from airport, country where country.iso_country = airport.iso_country and country.name = "iceland";
![Screenshot 2024-09-15 163929](https://github.com/user-attachments/assets/ce0b1c05-382e-4f53-9447-5d44f49b12be)

Q2. select airport.name as "Airport name" from airport, country where airport.iso_country = country.iso_country and country.name = "France" and airport.type = "large_airport";
![Screenshot 2024-09-15 165243](https://github.com/user-attachments/assets/d173272d-acfe-4c4d-b8b6-616e14870a4a)

Q3. select country.name as "Country name", airport.name as Airport name" from airport, country where country.iso_country = airport.iso_country and country.continent = "AN";
![Screenshot 2024-09-15 170627](https://github.com/user-attachments/assets/3367d61a-c22a-413f-99fc-b7c13fbf9a6a)

Q4.  select elevation_ft from airport, game where ident = location and screen_name = "Heini";
![Screenshot 2024-09-15 172551](https://github.com/user-attachments/assets/10a4f95c-2ddb-4674-88da-a53e762d3ca7)

Q5.  select elevation_ft * 0.3048 as "elevation_m" from airport, game where ident = location and screen_name = "Heini";
![Screenshot 2024-09-15 173709](https://github.com/user-attachments/assets/b7b6fa46-cdc9-4461-8fdf-c9cc3ad0caee)

Q6.  select name from airport, game where location = ident and screen_name = "Ilkka";
![Screenshot 2024-09-15 174026](https://github.com/user-attachments/assets/ddf96636-6cc4-4787-ba58-61dac7a7442f)

Q7.  select country.name from country, game, airport where location = ident and airport.iso_country = country.iso_country and screen_name = "Ilkka";
![Screenshot 2024-09-15 174813](https://github.com/user-attachments/assets/ffb92dd0-d3dc-4815-bff1-07b35de6635d)

Q8.  select name from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
![Screenshot 2024-09-15 180558](https://github.com/user-attachments/assets/3911f574-c8ee-47bb-ba8d-2e08386ff4fd)

Q9.  select airport.name from airport, goal_reached, goal, game where ident = location and game.id = game_id and goal.id = goal_id and screen_name = "ILKKA" and goal.name = "clouds";
![Screenshot 2024-09-15 181417](https://github.com/user-attachments/assets/f171249d-73f2-475b-a147-36b8828ac298)

Q10.  select country.name from airport, goal_reached, goal, game, country where ident = location and game.id = game_id and goal.id = goal_id and airport.iso_country = country.iso_country and screen_name = "ILKKA" and goal.name = "clouds";
![Screenshot 2024-09-15 182228](https://github.com/user-attachments/assets/632f8842-979f-436b-82a3-1beae81983c6)


# Week 4 exercise 4

Q1. select country.name as "country name", airport.name as "airport name" from country inner join airport on country.iso_country = airport.iso_country where country.name = "Finland" and scheduled_service = "yes";
![Screenshot 2024-09-23 174517](https://github.com/user-attachments/assets/bff6530f-d606-41c7-9c2b-e25cb8121395)

Q2. select screen_name, airport.name from game inner join airport on location =ident;
![Screenshot 2024-09-23 180418](https://github.com/user-attachments/assets/497f228b-084a-42e0-953c-767b7f8f8f2a)

Q3.select screen_name, country.name from game inner join airport on location = ident inner join country on country.iso_country = airport.iso_country;
![Screenshot 2024-09-23 180522](https://github.com/user-attachments/assets/4df704c5-f80b-4821-acb5-588d7fc7d99b)

Q4. select airport.name, screen_name from airport left join game on ident = location where name like %Hels%;
![Screenshot 2024-09-23 181143](https://github.com/user-attachments/assets/1bc15eb2-1687-4748-b4fb-4775eea6e269)

Q5.select name, screen_name from goal left join goal_reached on goal.id = goal_id left join game on game.id = game_id;
![Screenshot 2024-09-23 181522](https://github.com/user-attachments/assets/e256eaaf-43ba-4d95-a03d-154da7556587)

# Week 4 exercise 5

Q1. select name from country where iso_country in ( select iso_country from airport where name like "Satsuma%");
![Screenshot 2024-09-25 222302](https://github.com/user-attachments/assets/d31ecc84-ea98-4581-a073-849f5989ab0e)


Q2. select name from airport where iso_country in (select iso_country from country where name like "Monaco");
![Screenshot 2024-09-25 222502](https://github.com/user-attachments/assets/fa834249-3959-45d0-b304-2fdb1eb418ac)


Q3. select screen_name from game where id in (select game_id from goal_reached where goal_id in ( select id from goal where name = "Clouds"));
![Screenshot 2024-09-25 223042](https://github.com/user-attachments/assets/206b25d0-e1c3-4445-abce-98690628d2d3)

Q4.  select country.name from country where iso_country not in(select airport.iso_country from airport);
![Screenshot 2024-09-25 223420](https://github.com/user-attachments/assets/aefa197f-c233-4443-833f-a848d04d9e8d)


Q5. select name from goal where id not in(select goal.id from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini" );
![Screenshot 2024-09-25 223617](https://github.com/user-attachments/assets/ef00fd25-bf41-4be4-b4d0-1282fe6ce3ba)

# Week 5 exercise 6

Q1. select max(elevation_ft) from airport;
![Screenshot 2024-09-25 230633](https://github.com/user-attachments/assets/87d378e3-3183-4555-b348-de09e9b059c9)

Q2. ![image](https://github.com/user-attachments/assets/e124f28a-ba31-4ad9-8128-f45de5174d64)
![Screenshot 2024-09-25 231251](https://github.com/user-attachments/assets/9ce87aaf-3bb6-4547-b0ce-108febe47979)


Q3. select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;
![Screenshot 2024-09-25 231532](https://github.com/user-attachments/assets/859a9923-8ead-4463-97ac-01b50643b9b2)

Q4. select screen_name from game where co2_consumed in (select min(co2_consumed)from game);
![Screenshot 2024-09-25 233339](https://github.com/user-attachments/assets/dab543ef-67e8-4ee2-b3de-4b53d157d11e)

Q5. select country.name, count(*) from country, airport
where airport.iso_country = country.iso_country
group by country.iso_country
order by count(*) desc
limit 50;
![Screenshot 2024-09-25 234200](https://github.com/user-attachments/assets/4f95b739-c6c4-4cd2-bc52-d3a63251e97d)

Q6. select country.name from country, airport where airport.iso_country = country.iso_country
group by country.iso_country having count(*) > 1000;
![Screenshot 2024-09-25 234822](https://github.com/user-attachments/assets/f8510cb7-0a1e-42fa-9fd4-f52bcb8d6d84)

Q7. select name from airport where elevation_ft in (select max(elevation_ft) from airport);
![Screenshot 2024-09-25 235128](https://github.com/user-attachments/assets/3a1aae89-79d2-410a-82e6-661f43ac9051)

Q8. select name from country where iso_country in (select iso_country from airport where elevation_ft in (select max (elevation_ft) from airport));
![Screenshot 2024-09-26 000043](https://github.com/user-attachments/assets/44bf8bd5-a1c6-47dc-887f-d6af1ae2e30f)

Q9. select count(*) from game where screen_name = "Vesa";
![Screenshot 2024-09-26 000552](https://github.com/user-attachments/assets/85f17fb7-03e1-4faa-8740-85716426a101)

Q10. select name from airport where latitude_deg in(select min(latitude_deg) from airport);
![Screenshot 2024-09-26 000806](https://github.com/user-attachments/assets/cbb989b9-a6c4-4305-bccb-3e9847fa86b9)

# Week 5 exercise 5

Q1. update game
set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
where screen_name = "Vesa";
![Screenshot 2024-09-26 002936](https://github.com/user-attachments/assets/42e390c2-daf1-40c0-89f8-8d6d5ff6cb04)

Q2. 

Q3. delete from goal_reached;
![Screenshot 2024-09-26 003407](https://github.com/user-attachments/assets/fb08cb60-3cc8-4afa-99dd-9680bc279c22)

Q4. delete from game;
![Screenshot 2024-09-26 003514](https://github.com/user-attachments/assets/731b4f20-ed22-428b-8d65-76495e531654)








