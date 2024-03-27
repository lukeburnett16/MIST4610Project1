# **MIST4610 Group 4 Project**

## Team Name:
**61608 Group 4**

## Team Members:
1. Devin Davis [@dvndavis](https://github.com/dvndavis)
2. Hadden Peel [@hmpeel](https://github.com/hmpeel)
3. Kate Macken [@katemacken](https://github.com/katemacken)
4. Keira Cullinan [@keiracullinan](https://github.com/keiracullinan)
5. Lleyton Poole [@lleytonpoole10](https://github.com/lleytonpoole10)
6. Luke Burnett [@lukeburnett16](https://github.com/lukeburnett16)

## Problem Description:
The project at hand is to build and implement a relational database tailored to the operational framework of a national soccer club. At the core of this database lies the Players entity, representing the central hub of our organization. The players are the framework for the organization as they are members of the team and our program revolves around them. The Players entity operates in tandem with associated entities such as Teams, CommunityEngagement, Contracts,and TrainingSessions. These entities collectively delineate the intricate web of relationships and processes within our soccer club, encompassing player training, contract management, match scheduling, financial transactions, and performance tracking. Our primary objective is to meticulously model these relationships, defining the attributes and dependencies of each entity. Once established, the database will be populated with sample data to simulate a real-world scenario. Additionally, we aim to develop robust query functionalities within the database, enabling us to extract valuable insights into the club's operations, performance metrics, and strategic opportunities. Through this comprehensive database solution, we hope to enhance decision-making capabilities, and ultimately elevate the overall experience for our players, coaches, staff, and stakeholders within the soccer community.


## Data Model:
Data Model Explanation: 
Our model is based on the managerial structure of two soccer teams, the U.S. Women's Soccer Team and the U.S. Men’s Soccer Team. The team entity represents all 50 players on the teams, which is represented by the one-to-many relationship we placed between teams and players. 

From the Players table, there is a one-to-many relationship between Players and Training Session. One player can go to many training sessions, and each training session includes data on the session as well as the length. The Training Session connects with the Training Type which includes the location of training and training type. 

There is also a many-to-many relationship between Players and Matches, which created the table Player Stats. Player Stats includes important information such as goals or assists scored. This information helps to connect the players to the matches they have played. Matches include attributes such as the date of the match, opponent, attendance, the revenue generated from the match, and the name of the venue. Teams have a one-to-many relationship with Matches to put the team name with the match and opponent. One team can play many matches against different opponents. 

The Equipment table has a many-to-many relationship with Training Sessions to create Equipment Utilization. Equipment is included in many training sessions, and training sessions use lots of different equipment. The Equipment table includes the name of the equipment, quantity, and condition, such as Good or Used, the date of purchase, and the last maintenance date. 

There are many staff members within each team, so we added a one-to-many relationship between the Teams and Staff tables. Staff members also connect to Training Sessions, as many staff members run the training sessions. 

From the contracts table, there are three relationships stemming from the table: Staff, Sponsors, and Players. Each sponsor has a contract, so we created a one-to-one relationship between those two tables. The sponsor table includes important information such as the name of the sponsor, the amount given, and the industry that the sponsor is in. The contract table includes information such as the start and end date and the total amount of the contract. 

Lastly, there is a community engagement entity that shows the date of community engagement and the type of engagement. Players has a one-to-many relationship with community engagement. 

<img width="1062" alt="dataModel" src="https://github.com/dvndavis/Group4/assets/163315179/12d9d350-a69f-4ef5-9fc6-79ec7d3c10ba">

## Data Dictionary:

<img width="483" alt="Screenshot 2024-03-27 at 11 55 14 AM" src="https://github.com/dvndavis/Group4/assets/163012542/91f859d3-94ff-46a2-aaf3-ff0b9c4d9a8f">
<br>
<img width="483" alt="Screenshot 2024-03-27 at 11 58 07 AM" src="https://github.com/dvndavis/Group4/assets/163012542/4b67971f-c767-4c46-8ffe-e25dd5ff3618">
<br>
<img width="482" alt="Screenshot 2024-03-27 at 12 08 57 PM" src="https://github.com/dvndavis/Group4/assets/163012542/28f9a95d-a679-4162-810d-f6d3a113e267">
<br>
<img width="485" alt="Screenshot 2024-03-27 at 12 11 24 PM" src="https://github.com/dvndavis/Group4/assets/163012542/844f9f8c-f3ec-4066-a104-c13f2dd05b79">
<br>
<img width="483" alt="Screenshot 2024-03-27 at 12 13 38 PM" src="https://github.com/dvndavis/Group4/assets/163012542/10cedca0-542a-409e-9ade-5e0406fd09f1">
<br>
<img width="389" alt="Screenshot 2024-03-27 at 12 47 06 PM" src="https://github.com/dvndavis/Group4/assets/163012542/79674384-8df8-493a-a39e-7c0dcd1265fc">
<br>
<img width="396" alt="Screenshot 2024-03-27 at 12 30 08 PM" src="https://github.com/dvndavis/Group4/assets/163012542/1e0122a1-3c95-49ad-b024-51c32a38f83b">
<br>
<img width="386" alt="Screenshot 2024-03-27 at 12 38 28 PM" src="https://github.com/dvndavis/Group4/assets/163012542/e07f804c-afd3-47af-b6ad-607ed6a1da84">
<br>
<img width="387" alt="Screenshot 2024-03-27 at 12 53 24 PM" src="https://github.com/dvndavis/Group4/assets/163012542/5a1d1c16-dbdf-4791-90ff-a51390214472">
<br>
<img width="404" alt="Screenshot 2024-03-27 at 12 46 11 PM" src="https://github.com/dvndavis/Group4/assets/163012542/fad7b60f-8681-4a80-9e21-3584bea1a43b">
<br>
<img width="389" alt="Screenshot 2024-03-27 at 12 43 04 PM" src="https://github.com/dvndavis/Group4/assets/163012542/8313470c-2d11-4524-ab7e-7fb2dc910140">
<br>
<img width="391" alt="Screenshot 2024-03-27 at 12 50 06 PM" src="https://github.com/dvndavis/Group4/assets/163012542/0fb3cd70-57f2-4495-b31d-25eabe2539ad">




## Queries:

### Query 1:
Query 1 lists the total amount of goals and assists by each player in this calendar year.
<img width="776" alt="Screenshot 2024-03-27 at 2 07 50 PM" src="https://github.com/dvndavis/Group4/assets/163012542/6e198736-e52b-4974-a5c3-31052806dfde">
<br>
Query 1 allows managers and others to fully break down the performance of each of their players. Maybe there is a condition in their contract in which a certain amount of goals/assists in a season gets them a bonus or contract option. Using this information the manager can decide whether he wants to resign a player, and if so this information can help when determining that new players’ salary.

### Query 2:
Query 2 lists player names along with their contract amounts and team name if their contract started after 2019.
<img width="775" alt="Screenshot 2024-03-27 at 2 08 20 PM" src="https://github.com/dvndavis/Group4/assets/163012542/cba4d2b8-a802-4da1-b239-1c6ed7f535cb">
<br>
Query 2 allows the club to look at the amount that they have been paying players in the past 4 years. This is a good metric for clubs as they are able to compare their recent contract amounts for both teams and compare to them to the amounts that other teams are paying their players. This is important, because it would not useful for managers to analyze the contracts of players that they paid in a different player market. 

### Query 3:
Query 3 lists player names along with their contract amounts and their total playing time for the year.
<img width="777" alt="Screenshot 2024-03-27 at 2 08 40 PM" src="https://github.com/dvndavis/Group4/assets/163012542/999899d9-9f8e-47be-add7-73d7bdda923e">
<br>
Query 3 allows the club to fully value a player by comparing the amount of time they play to the amount they pay for them. It will also allow the club to see why someone may be underperforming even though they are very skilled, in which they may not be getting enough playing time. They may also look to see if a player is being played too much, therefore increasing the risk of burning out and injury. This analysis will allow them to build strategies around their players more efficiently.

### Query 4:
Query 4 lists the number of players at each position that are paid more than the average contract of all players.
<img width="776" alt="Screenshot 2024-03-27 at 2 09 19 PM" src="https://github.com/dvndavis/Group4/assets/163012542/bf9bc63e-c11b-42fa-87e1-8558a4ec0864">
<br>
Query 4 allows the club to see which positions they are or are not allocating their money towards or where they should allocate more of their money to. If one position has more contracts above the average than the others then the club may need to reevaluate their spending habits or may need to allocate more of their salary cap to other positions.

### Query 5:
Query 5 lists each sponsor that donates more than the average amount of all sponsors as well as the total amount they donate.
<img width="776" alt="Query5" src="https://github.com/dvndavis/Group4/assets/163315179/f50f92c7-592f-436a-86ed-0538cebbd86c">
<br>
Query 5 allows the club manager to analyze their top-paying sponsors. By doing this the club will be able to determine whether they have been honoring the contract amount with their sponsor faithfully. This will allow the club to strengthen their current business relationships and also allow them to create stronger relationships in the future. 

### Query 6:
Query 6 lists the equipment name, id, condition and quantity for equipment that is in fair or used condition and has a quantity over 15.
<img width="776" alt="Screenshot 2024-03-27 at 2 38 43 PM" src="https://github.com/dvndavis/Group4/assets/163012542/dd45576c-d925-4b2d-9aa6-67c489c25bf7">
<br>
Query 6 helps the organization to know so they can place orders for the pieces of equipment that are not in good condition so that their facilities are in the best shape possible. By having the best pieces of equipment, player workouts are more effective and the players develop better. This also allows the team to recruit better as their facilities will then be in better condition.

### Query 7:
Query 7 lists the position, total goals, and total assists for each of the men's soccer players across all matches as well as the total contract amounts for the players at each position while excluding goalkeepers.
<br>
<img width="776" alt="query7" src="https://github.com/dvndavis/Group4/assets/163315179/73015f93-4f26-445f-bd7b-bdb81d0042e5">
<br>
Query 7 shows the total goals and assists. This information is important for a manager to know for positioning reasons. If the defenders are scoring more than the forwards, then the players who are playing in the defender position may want to try the forward position. It is also important to note the differences in pay between the three groups. A large difference in the contract amounts between the three positions could create tension in the team due to pay differences. 

### Query 8:
Query 8 lists the date of birth of certain players and their names, positions, and previous clubs. 
<br>
<img width="776" alt="query8" src="https://github.com/dvndavis/Group4/assets/163315179/3841546b-016c-4f9e-ae48-25050cbed94b">
<br>
Query 8 would be helpful for a manager to know for recruiting reasons. When managers recruit, they must know the age of the players, as well as their position and previous clubs. With previous clubs, the managers can watch the player's games and know their positions. A manager of a soccer team must know how many players they are recruiting for each position, so this information is crucial. Younger players can be more inexperienced or be a part of a different team (U20 vs U21 for example), and managers must know this to watch their games. 

### Query 9:
Query 9 lists the amount of time staff members train players. 
<img width="776" alt="Query9" src="https://github.com/dvndavis/Group4/assets/163315179/022b05f8-5d53-4c57-845e-51cc23c8b8d8">
<br>
Knowing how long each staff member is involved with training players can be used to help the teams determine what areas of training may need more time, as well as how involved the staff members are with the team. If a staff member is training too little, then their role might need to be changed or they may need to have more players assigned to them, and if a staff member is training dramatically more than another staff member, their responsibilities may need to be re-evaluated. 
### Query 10:
Query 10 lists the players who have not completed their community engagement. 
<br>
<img width="776" alt="query10" src="https://github.com/dvndavis/Group4/assets/163315179/be0806e2-65e0-40b1-b42b-0a2d650fca68">
<br>
Query 10 would be important for a manager to know who has or has not done their community engagement. As a member of the U.S. soccer team, the players should be required to participate in at least one community engagement, and this query will allow a manager to quickly see who has not done it. 

## Database Information
**Database Name:** ns_Sp24_61608_Group4

**Stored Procedures:** Each of the 10 queries are stored with formatting TP_Qx, where x is the query number.




