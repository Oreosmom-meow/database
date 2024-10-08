#Wwek 3 Exercise 2: Single Table Queries\
#Q1
select * from goal;
![screenshot](Screenshot_week3_e2_q1.png)

#Q2
select name, type from airport where iso_country = 'FI';
![screenshot](Screenshot_week3_e2_q2.png)
#Q3
select substring(name, 1, 19) as name from airport where iso_country = 'FI' order by name ASC;
![screenshot](Screenshot_week3_e2_q3.png)

#Q4
select name, type from airport where iso_country = 'FI' order by type, name;
![screenshot](Screenshot_week3_e2_q4.png)

#Q5
select name from country where name like 'F%';
![screenshot](Screenshot_week3_e2_q5.png)

#Q6
 select name from country where name like '%F%';
![screenshot](Screenshot_week3_e2_q6.png)

#Q7
select location from game where screen_name = 'Vesa';
![screenshot](Screenshot_week3_e2_q7.png)

#Q8
select co2_consumed from game where screen_name = 'Ilkka';
![screenshot](Screenshot_week3_e2_q8.png)

#Q9
select distinct co2_budget from game;
![screenshot](Screenshot_week3_e2_q9.png)

#Q10
select screen_name, co2_budget, co2_consumed, @co2_left := co2_budget - co2_consumed as co2_left from game where screen_name = 'Ilkka';
![screenshot](Screenshot_week3_e2_q10.png)

#Week 3 Excercise 3: Multiple Table Queries\
#Q1
select country.name as "country name", airport.name as "airport name" from country inner join airport on country.iso_country = airport.iso_country where airport.iso_country = 'IS';
![screenshot](Screenshot_week3_q1.png)

#Q2
select name as "airport name" from airport where iso_country = 'FR' and type like '%large%';
![screenshot](Screenshot_week3_q2.png)

#Q3
 select country.name as "country_name", airport.name as "airport_name" from country inner join airport on country.iso_country = airport.iso_country where country.continent = 'AN';
![screenshot](Screenshot_week3_q3.png)

#Q4
select airport.elevation_ft from airport inner join game on airport.ident = game.location where game.screen_name = 'Heini';
![screenshot](Screenshot_week3_q4.png)

#Q5
select airport.elevation_ft * 0.3048 as elevation_m from airport inner join game on airport.ident = game.location where game.screen_name = 'Heini';

![screenshot](Screenshot_week3_q5.png)

#Q6
select airport.name from airport inner join game on airport.ident = game.location where game.screen_name = 'Ilkka';
![screenshot](Screenshot_week3_q6.png)

#Q7
 select country.name from airport inner join game on airport.ident = game.location inner join country on airport.iso_country = country.iso_country where game.screen_name = 'Ilkka';
![screenshot](Screenshot_week3_q7.png)

#Q8
select goal.name from game join goal_reached on game.id = goal_reached.game_id join goal on goal.id = goal_reached.goal_id where game.screen_name = 'Heini';
![screenshot](Screenshot_week3_q8.png)

#Q9
select airport.name
    from game
    join goal_reached
    on game.id = goal_reached.game_id
    join goal
    on goal.id = goal_reached.goal_id
    join airport
    on game.location = airport.ident
    where game.screen_name = 'Ilkka' and goal.name = 'CLOUDS';
![screenshot](Screenshot_week3_q9.png)

#Q10
select country.name from game join goal_reached on game.id = goal_reached.game_id join goal on goal.id = goal_reached.goal_id join airport on game.location = airport.ident join country on country.iso_country = airport.iso_country where game.screen_name = 'Ilkka' and goal.name = 'CLOUDS';
![screenshot](Screenshot_week3_q10.png)
