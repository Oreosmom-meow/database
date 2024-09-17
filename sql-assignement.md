#Week 3 Excercise 3: Multiple Table Queries
#Q1
select country.name as "country name", airport.name as "airport name" from country inner join airport on country.iso_country = airport.iso_country where airport.iso_country = 'IS';

