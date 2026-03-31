<img width="609" height="833" alt="image" src="https://github.com/user-attachments/assets/0dc38733-6b74-4929-9a21-654233b9a4b1" /># MIST4610-Group-Project-1

## Team Name:
21482 Group 6

## Team Members:
1. Andrew Mckenna [@andrew-mckenna] (https://github.com/andrew-mckenna)
2. Benjamin Perez-Acosta [@bp59023] (https://github.com/bp59023)
3. Mason Herndon [@Mason-port] (https://github.com/Mason-port) 
4. Maria Jacob [@mej65217] (https://github.com/mej65217)
5. Parker Gallagher [@Parker1094] (https://github.com/Parker1094)

## Problem Scenario:
The scenario for this project is to build a relational database for the use of an Intramural Basketball League. The central entity in the model is BLANK, this entity shows the BLANK. The basketball league operates by hosting multiple seasons, with multiple games in each season, two different teams per game, multiple venues where the games can be played, multiple players per team, and multiple staffers that worked the games. We aim to accurately model these relationships, create sample data, and populate each entity and its attributes accordingly. Additionally, we want to run functional queries on this data to generate meaningful business insights about the resort and its operations.

## Data Model: 
<img width="1728" height="1157" alt="Data Model" src="https://github.com/user-attachments/assets/765e2820-cba3-4574-97e1-f02055b489c0" />

Explanation of Data Model:

This database is designed to manage a basketball league by organizing information about players, teams, games, staff, and league structure. The goal is to track how players participate in leagues, how teams are formed, and how games are scheduled and managed.

The League table represents different basketball leagues, and each league is tied to a specific Season, which stores when the league begins and ends. This allows the system to separate leagues by time periods and keep data organized across multiple seasons.

Each league contains multiple Teams, and every team belongs to only one league. Teams are identified by their name and linked back to their league through a foreign key.

Players are stored in the Player table, which includes basic information like name and email. Since players can join leagues, the Registration table connects players to leagues. This allows a player to register for multiple leagues and keeps track of when their participation starts and ends.

Players are assigned to teams using the TeamRoster table. This table connects players and teams and also stores details like jersey numbers. This setup allows each team to have many players while keeping the roster flexible.

Games are handled in the Game table, which includes the date of the game and links to both the league and the Venue where the game takes place. The Venue table stores details about locations, such as the venue name and court.

To record game outcomes, the model includes a many-to-many recursive relationship relating games to itself by their relation to competition. A given game has a home and away team with the shared attribute of game ID.

The Staff table stores information about staff members, such as referees or organizers. Staff can be assigned to games through the GameStaff table, which allows multiple staff members to work the same game. The Staff table also includes a supervisorID to represent reporting relationships within staff.

The PlayerGameStats table is used to record statistics derived from games, such as field goals, three-point shots, rebounds, etc. Each player's game statistic is linked to a specific game and player, allowing for performance analysis at an individual level.

Overall, this database supports managing league participation, team organization, game scheduling, staff assignments, and statistical tracking. It is mainly focused on the structure and operations of the league alongside player-level analytics.

## Data Dictionary
<img width="1517" height="352" alt="image" src="https://github.com/user-attachments/assets/49881290-0344-4f44-bd17-1bb279be8da0" />

<img width="1520" height="346" alt="image" src="https://github.com/user-attachments/assets/bff6150b-b3e6-4379-a17d-9dbc3121bf42" />

<img width="1522" height="346" alt="image" src="https://github.com/user-attachments/assets/64e23771-24cd-4947-94ce-d1b9e735b0b7" />

<img width="1518" height="356" alt="image" src="https://github.com/user-attachments/assets/f02dadec-95ed-410e-8146-88e83466bd42" />

<img width="1527" height="347" alt="image" src="https://github.com/user-attachments/assets/62915604-7d84-4fa6-bfe3-8628fc67816a" />

<img width="1521" height="380" alt="image" src="https://github.com/user-attachments/assets/d6ecac23-3b9a-4c74-aead-a0b760dbd5ef" />

<img width="1516" height="385" alt="image" src="https://github.com/user-attachments/assets/013d320e-a2c7-45c2-b45f-8a1c9f657e60" />

<img width="1503" height="388" alt="image" src="https://github.com/user-attachments/assets/a587414a-14dd-442d-b470-808586e5dea6" />

<img width="1511" height="395" alt="image" src="https://github.com/user-attachments/assets/9fc96e23-39be-484d-a0d8-f341e11f6166" />

<img width="1517" height="383" alt="image" src="https://github.com/user-attachments/assets/51a1a9ab-937c-4ff6-9eaf-abad637dbdfb" />

<img width="1527" height="396" alt="image" src="https://github.com/user-attachments/assets/d76272c0-4a0e-4e72-a281-729d499e6aae" />

<img width="1527" height="468" alt="image" src="https://github.com/user-attachments/assets/a6dee2dc-b5ee-4721-89f5-3d9b5cce2374" />





## Queries:
Query 1 – Top Scoring Players
<img width="627" height="400" alt="Screen Shot 2026-03-31 at 10 40 18 AM" src="https://github.com/user-attachments/assets/5ea7077d-a2ee-455f-a3b2-97daa06d47ca" />

This query lists the total number of points scored by each player across all games. The results are ordered in descending order based on total points. This allows managers to identify the highest-performing players in the league. These players may be key contributors and could be prioritized for recognition, team placement, or future recruitment decisions.

Query 2 – Team Performance
<img width="625" height="404" alt="Screen Shot 2026-03-31 at 10 41 06 AM" src="https://github.com/user-attachments/assets/7b9026b9-2ac8-4811-b0cd-3d876572fa02" />

This query calculates the total number of points scored by each team by combining the performance of all players on that team. The results are ordered in descending order of total team points. This helps managers compare team performance and identify the strongest teams in the league. It also helps in evaluating team balance and competitiveness.

Query 3 – Ineligible Players

<img width="617" height="387" alt="Screen Shot 2026-03-31 at 10 41 28 AM" src="https://github.com/user-attachments/assets/457ceeb0-811d-426d-93b0-7eca93372d64" />

This query lists all players who are not eligible to participate in the league. Managers can use this information to ensure that only eligible players are allowed to play. This helps maintain fairness and compliance with league rules and prevents unauthorized participation.

Query 4 – Average Points Per Player
<img width="624" height="397" alt="Screen Shot 2026-03-31 at 10 41 50 AM" src="https://github.com/user-attachments/assets/88ed6f6a-6cdd-4a52-a8ac-d0c5b25f4c8d" />

This query calculates the average number of points scored per game for each player. The results help managers evaluate player consistency and overall performance. Players with higher averages are more reliable contributors, which can influence coaching decisions and team strategy.

Query 5 – Highest Scoring Games
<img width="625" height="391" alt="Screen Shot 2026-03-31 at 10 42 16 AM" src="https://github.com/user-attachments/assets/492e5714-e7f6-434a-8f81-71cd07c6b72f" />

This query calculates the total score for each game by adding both teams' scores and orders the results from highest to lowest. Managers can use this to identify the most competitive and high-scoring games. These games may indicate strong matchups or areas where defensive performance needs improvement.

Query 6 – Staff Workload

<img width="620" height="393" alt="Screen Shot 2026-03-31 at 10 42 44 AM" src="https://github.com/user-attachments/assets/cfd4d1a3-6063-49c7-b802-ac392a26d391" />

This query counts how many games each staff member has worked and orders the results in descending order. Managers can use this to evaluate staff workload and ensure that responsibilities are distributed evenly. It also helps identify overworked staff members.

Query 7 – Players Per Team

<img width="628" height="392" alt="Screen Shot 2026-03-31 at 10 43 20 AM" src="https://github.com/user-attachments/assets/83ea99d0-b71e-4c40-b319-eed8149258ed" />

This query counts the number of players assigned to each team. Managers can use this information to ensure that teams are balanced and properly staffed. If a team has too many or too few players, adjustments can be made.

Query 8 – High Scoring Performances
<img width="626" height="391" alt="Screen Shot 2026-03-31 at 10 43 50 AM" src="https://github.com/user-attachments/assets/701f104a-a9ca-4c5b-be89-01685e66ef74" />

This query lists players who scored more than 20 points in a single game. Managers can use this to identify standout individual performances. These players may be key contributors and can be highlighted for recognition or strategic planning.

Query 9 – Game Locations

<img width="623" height="396" alt="Screen Shot 2026-03-31 at 10 44 20 AM" src="https://github.com/user-attachments/assets/7ed3def2-757a-4aa4-ae1a-435cd9f7dfee" />

This query shows details about where each game is played, including court name and number. Managers can use this information for scheduling and organizing games efficiently. It ensures that venues are properly utilized.

Query 10 – Inactive Players

<img width="628" height="400" alt="Screen Shot 2026-03-31 at 10 44 44 AM" src="https://github.com/user-attachments/assets/80d1c89a-ab79-408b-87a5-330b73f3fe4d" />

This query identifies players who have not participated in any games. Managers can use this to track inactive players and improve engagement. It helps ensure that all registered players are being utilized effectively.

# Database Information

Name of the database: al_Group_21482_G6

