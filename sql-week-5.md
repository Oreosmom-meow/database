#Week 5 Exercises 6: Aggregate Queries\
#Q1
select max(elevation_ft) as "max(elevation_ft)" from airport;
![screenshot](Screenshot_week5_e6_q1.png)

#Q2
select continent, count(*) from airport group by continent;
![screenshot](Screenshot_week5_e6_q2.png)

#Q3
select g.screen_name, count(*) from game as g join goal_reached as gr on g.id = gr.game_id group by g.screen_name;
![screenshot](Screenshot_week5_e6_q3.png)

#Q4
select screen_name from game where co2_consumed in (select min(co2_consumed) from game);
![screenshot](Screenshot_week5_e6_q4.png)

#Q5
``select ct.name, count(*) from country as ct left join airport as ap on ct.iso_country = ap.iso_country group by ct.name order by count(*) DESC limit 50;``
![screenshot](Screenshot_week5_e6_q5.png)

#Q6
select screen_name from game where co2_consumed in (select min(co2_consumed) from game);
![screenshot](Screenshot_week5_e6_q6.png)

#Q7
 select name from airport where elevation_ft in (select max(elevation_ft) from airport);
![screenshot](Screenshot_week5_e6_q7.png)

#Q8
select ct.name from country as ct join airport on ct.iso_country = airport.iso_country where airport.elevation_ft in (select max(airport.elevation_ft) from airport);
![screenshot](Screenshot_week5_e6_q8.png)

#Q9
``select count(*) from goal_reached as gr join game as g on g.id = gr.game_id where g.screen_name ='Vesa';``
![screenshot](Screenshot_week5_e6_q9.png)

#Q10
select name from airport order by (0 - ABS(latitude_deg)) ASC limit 1;
![screenshot](Screenshot_week5_e6_q10.png)

#Exercises 7: Update Queries\
#Q1
```
update game
set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
where screen_name = "Vesa";

select * from game;
```
![screenshot](Screenshot_week5_e7_q1.png)

#Q3
```
delete from goal_reached;
select * from goal_reached;
```

#Q4
```
delete from game;
select * from game;
```


