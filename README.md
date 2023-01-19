# *Uber-case-study*

![image](https://user-images.githubusercontent.com/90236224/211821944-fbd53227-3813-4fcc-91a6-c91f875f6fc4.png)


Uber Technologies, Inc. provides services like peer-to-peer ridesharing, hailing an Uber ride with your phone, renting bikes & cars, and ordering food for delivery. It’s based on the On-demand app development model.
Uber is best known for its ridesharing service and has changed the way people use transportation in general. Before Uber, it used to be difficult for people to find a cab when they needed it; however, now they can order one with a click.

Here we have a Uber dataset. Before jumping into the analysis let us find the out the basic overview of the data. We are doing this analysis in Excel. 

## *Overview *
1. The data has 6746 rows and 6 columns. 
2. Request_id: The request id is generated when a user request for cab booking. 
3. Pickup point: From where the use has to be picked up. In this case only two pickup locations, Airport and City, are considered.
4. Status: Trips has completed, cancelled or there was no availability of car.
5. Request_timestamp: When the cab booking is initiated.
6. Drop_timestamp: When the rides was over.

## *Exploratory Data Analysis* 
We will try to find answer to some of the questions;
1. Number of completed rides from pickup point.
2. Number of rides per day.
3. Finding the highest cancellation rate.
4. Finding the highest trip completion rate. 
5. Average ride duration of top 10 drivers. 

For finding the answer to our first question we need to make an additional column 'Flag_for_completion'. 1 for 'trip completed' and 0 for 'cancelled' and 'no car available'.

### 1. Number of completed rides from pickup points. 
Pivot table is best for this purpose. 

![image](https://user-images.githubusercontent.com/90236224/211825312-27eabffe-4b9b-49a7-92f3-8cf5284db1cb.png)

![image](https://user-images.githubusercontent.com/90236224/211825476-5b1595b3-66de-47b2-a468-6483d6c250ef.png)
1. 3238 requests made from Airport out of which about 41% trips were completed. 
2. 3507 requests made from City out of which about 43% trips were completed. 
Rides from City have highest completion rate.  

2. Number of rides per day. 
We have request_timestamp and drop_timestamp. We shall choose Request_timestamp for this purpose because total no of rides here is total request we got. 
We shall make an additional columns for date using date() and make a pivot table. 

![image](https://user-images.githubusercontent.com/90236224/211827513-3355a629-3222-450a-9952-ad1f91cc6ed9.png)

![image](https://user-images.githubusercontent.com/90236224/211827648-6b2548e1-361c-4af5-b82c-90e908d70f33.png)
We have trips data from 11 July to 15 July. 
1. Highest trips completed on 13 July and lowest on 14 July. 
2. Number of not availability of cars is significant, which needs to looked into. 
3. Cancellation rate is highest on 13 July, despite having highest trips completed. 

3. Finding the highest trip completion rate. 
Ride completion rate = no of rides completed/total no of rides. 
We need to make a seperate table for this purpose with columns driver_id, total_rides, completed_rides and ride_completion_rate. 

Row Labels	Sum of Ride_completion_rate

![image](https://user-images.githubusercontent.com/90236224/211829951-489550eb-4ac7-4022-869e-a08fdd11951c.png)

![image](https://user-images.githubusercontent.com/90236224/211830020-a106412c-c259-4d00-9420-38d141bb6e8a.png)
We have taken top 10 drivers on the basis of completion rate. 
1. Drivers with 42, 75, 11, 12 and 55 have 100% completion rate. Which quite commendable. 

4. Finding the highest cancellation rate. 
Cancellation rate = total rides cancelled/total number of rides. 
We need to make a seperate table for this purpose also with columns driver_id, total_rides, completed_rides and cancellation_rate. 

![image](https://user-images.githubusercontent.com/90236224/211831423-f7bc053d-9214-4fba-9404-d741728a1ffc.png)

![image](https://user-images.githubusercontent.com/90236224/211831487-e164ec19-f85e-4355-af3c-41302e0124c2.png)
We have taken top 10 drivers on the basis of cancellation rate. 
1. Drivers with Id 45 and 138 have 100% cancellation rate. This is worrysome. Action should be taken to understand the reason. 

5. Average ride duration.
Using Pivot table we have built a table with Driver_id, sum_duration, Total_no_of_trips. For finding avg duration the data is copied and pasted. 

![image](https://user-images.githubusercontent.com/90236224/212477253-fade2838-85c2-46a6-bbd9-d2e650f5a8cf.png)

![image](https://user-images.githubusercontent.com/90236224/212477270-187c3b90-d981-4f3c-a0d6-5bc729c3cb62.png)
Driver_id 84, 56 and 117 have avg_ride_duration of 1.1 hour which quite good. 

So this is our final dashboard with slicers. 

![uber dashboard image](https://user-images.githubusercontent.com/90236224/212477520-614340a2-6377-4191-97fc-5c83128684a8.jpg)

# *Recommendations*
### 1. Ride cancellation is 18.74% of total request which is significant. It not only affects user experience but also levy additional charges, paid by users or drivers. Proper analysis should be done, why are cancellations increasing, on the user end as well as driver's end. 

### 2. The no car availability is almost 40% of total request which again shift user to other cab providing companies. More number of cars should be employed after with area specific demands. It will help to increase and maitain the user rentention rate. 

### 3. Rides booked from City has 30.40% cancellation rate which is not good and rides booked from Airport has 52.90% no car availability issue with highest on 14 and 15 July. Request from Airport is 2 times the availability of cars. Number of cars should be increased. 

### 4. In the conclusion Uber is the company who revolutionized the cab booking industry with its easy to use platform and on site drop & picking. These are some insight which should be looked into. Less cancellation rate, more availability of car and high trip completion rate will help user retention, better user experience, more frequent ride booking and overall revenue generation for the company.   

<div class="badge-base LI-profile-badge" data-locale="en_US" data-size="medium" data-theme="light" data-type="VERTICAL" data-vanity="akshay9605" data-version="v1"><a class="badge-base__link LI-simple-link" href="https://in.linkedin.com/in/akshay9605?trk=profile-badge">Akshay Kumar</a></div>
              











  

