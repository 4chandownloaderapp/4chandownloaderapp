I'm currently working on making this app easier to use, there will be new commits in near future. More info soon.

4chandownloaderapp is app that allows to download all new data posted on chosen 4chan boards and store it in Microsoft SQL Server Database. The application consists of three components:
1. Microsoft SQL Server Database (4ch_Database repository) - Database for storing 4chan data (posts, threads, files).
2. Visual Studio SSIS project (4ch_Downloader repository) - This project contains logic for downloading data from 4chan saving it in database.
3. Visual Studio Windows Forms C# Project (4chanviewer repository) - Application for viewing data stored in the database.

How does it work?
4chandownloaderapp downloads periodically first page of chosen board and saves new content(new posts, threads, files) in the database. This solution is not perfect because if there is a lot of traffic on the board, it can miss some posts but usually it's good enough to save most content posted on boards to database.

How to start your own  4chandownloaderapp?
1. Install Microsoft SQL Server.
App needs database to store all the data. If you already have SQL Server Installed that can store your data, you can skip this step. Dwonload and install Microsoft SQL Server:
https://www.microsoft.com/en-us/sql-server/sql-server-downloads
If you use this app only for testing you can choose free developer edition with full functionalities. Otherwise you can choose free express edition(this edition has limitation regarding sizes of databases)
2. ....instructions in progress.....
