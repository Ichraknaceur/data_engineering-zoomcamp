# Week 1 Homework 
In this homework we will install the dependencies  and practice what we learned  with terraform and SQL
## Question 1
- Install google cloud sdk and get the version using 

       gcloud --version
 - Result :
      369.0.0
 ## Question 2 
 - copy the entire output - from the moment you typed terraform init to the very end.
 ## Question 3 
 - Query :

       SELECT COUNT (tpep_pickup_datetime)
       FROM yellow_taxi_trips
       WHERE date(tpep_pickup_datetime) = CAST ('2021-01-15') AS DATE );
       
  - Result : 2021-01-20
 ## Question 4 
 - Query :

       SELECT tip_amount , tpep_pickup_datetime
       FROM yellow_taxi_trips
       WHERE tip_amount = SELECT MAX (tip_amount ) FROM  yellow_taxi_trips);
       
  - Result : 53024
 ## Question 5 
 - Query :

       SELECT "DOLocatioID" , count( "DOLocatioID") AS value_occurence
       FROM (SELECT * FROM yelow_taxi_trips WHERE DATE(tpep_pickup_datetime)=CAST('2021-01-14' AS DATE) AND
       GROUP BY "DOLocatioID"
       ORDER BY value_occurence DESC
       LIMIT 1 ;
       
  - Result : Upper East Side South
 ## Question 6 
 - Query :

       SELECT index,"PULocationID", "DOLocatioID" ,total_amount
       FROM yellow_taxi_trips
       WHERE total_amount=(SELECT MAX(totalamount) FROM yellow_taxi_trips);
       
  - Result : central park/ Upper East Side North
