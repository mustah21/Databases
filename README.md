#exercise 2 Single table queries

Q1. select * from goal;
![Screenshot 2024-09-15 152346](https://github.com/user-attachments/assets/9350845d-b54a-4e3a-b77b-da8c05120693)

Q2. select name, type from airport where iso_country = "FI";
![Screenshot 2024-09-15 152400](https://github.com/user-attachments/assets/9c5e3ec1-506d-44e7-bfe1-8654dac82946)

Q3. select name from airport where iso_country = "FI" order by name;
![Screenshot 2024-09-15 152442](https://github.com/user-attachments/assets/f5f707df-9a75-40a6-aaa9-af5863378b60)

Q4. select name, type from airport where iso_country = "FI" order by type, name;
![Screenshot 2024-09-15 152510](https://github.com/user-attachments/assets/64d2d290-04d9-46aa-a0ed-39a2e836765f)

Q5. select name from country where name like "F%"
![Screenshot 2024-09-15 152547](https://github.com/user-attachments/assets/5626d160-71b5-44fe-8fa0-3674188ac11f)

Q6. select name from country where name like "%F%";
![Screenshot 2024-09-15 152828](https://github.com/user-attachments/assets/230c4957-58fe-4858-8bb3-5ce98dc597a0)

Q7. select location from game where name = "Vesa";
![Screenshot 2024-09-15 152902](https://github.com/user-attachments/assets/0539bc20-3529-419d-bf77-c2e71440e3cf)

Q8. select co2_consumed from game where screen_name = "Ilkka";
![Screenshot 2024-09-15 153047](https://github.com/user-attachments/assets/9856f0ec-bc51-4667-a63e-f9d74eaf9aad)

Q9. select distinct co2_budget from game;
![Screenshot 2024-09-15 153108](https://github.com/user-attachments/assets/4e8d3088-fb6d-4f9e-96db-f5c74ba61e86)

Q10. select screen_name, co2_budget, co2_consumed, (co2_budget - co2_consumed) As co2_difference from game where screen_name = "Ilkka";
![Screenshot 2024-09-15 153146](https://github.com/user-attachments/assets/02d0117f-9346-4a3b-8896-25da78a5f121)

