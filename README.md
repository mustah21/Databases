#    Week 3 exercise 2---Single table queries

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



