# MIST4610-Group-Project-1

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

