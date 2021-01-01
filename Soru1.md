#Soru1

```SQL
Select name, car.id as car_id,car.model as car_model, manufacture.year as manufacture_year, 
  array(Select as struct id, (TIMESTAMP_ADD(p.date, INTERVAL 3 hour)) as date  from unnest(purchase) as p) as purchase
From asiyenur_yilmaz.semi_structured_hw
Cross Join Unnest(car) car
Cross Join Unnest(manufacture) manufacture on car.id = manufacture.id
Order By name ASC, car.id DESC

```
