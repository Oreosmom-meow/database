#Week 4 Assignment
#Q1
 select country.name as "country name", airport.name as "airport name" from country join airport on country.iso_country = airport.iso_country where country.name = 'Finland';
![screenshot](Screenshot_week4_q1.png)

#Q2
 select game.screen_name, airport.name from airport join game on game.location = airport.ident;
![screenshot](Screenshot_week4_q2.png)

#Q3
select game.screen_name, country.name from airport join game on game.location = airport.ident join country on country.iso_country = airport.iso_country;
![screenshot](Screenshot_week4_q3.png)

#Q4
select airport.name, game.screen_name from airport left join game on airport.ident = game.location where airport.name like "%Hels%";
![screenshot](Screenshot_week4_q4.png)

#Q5
select goal.name, game.screen_name from goal left join goal_reached on goal_reached.goal_id = goal.id left join game on goal_reached.game_id = game.id;
![screenshot](Screenshot_week4_q5.png)
