I'm currently working on making this app easier to use, there will be new commits in near future. More info soon.

Contact: 4chan_downloader_app(at)superbox.pl

4chandownloaderapp is app that allows to download all new data posted on chosen 4chan boards and store it in Microsoft SQL Server Database. The application consists of three components:
1. Microsoft SQL Server Database (4ch_Database repository) - Database for storing 4chan data (posts, threads, files).
2. Visual Studio SSIS project (4ch_Downloader repository) - This project contains logic for downloading data from 4chan and saving it in database.
3. Visual Studio Windows Forms C# Project (4chanviewer repository) - Application for viewing data stored in the database.

How does it work?
4chandownloaderapp downloads periodically first page of chosen board and saves new content(new posts, threads, files) in the database. This solution is not perfect because if there is a lot of traffic on the board, it can miss some posts but usually it's good enough to save most content posted on boards to database.

How to start your own  4chandownloaderapp?
1. Install Microsoft SQL Server.
App needs database to store all the data. If you already have SQL Server Installed that can store your data, you can skip this step. Dwonload and install Microsoft SQL Server:
https://www.microsoft.com/en-us/sql-server/sql-server-downloads
If you use this app only for testing you can choose free developer edition with full functionalities. Otherwise you can choose free express edition(this edition has limitation regarding sizes of databases)
2. Download and install SQL Server Management Studio - free program for managing SQL Server and sending executing queries on your SQL Server Database - you might need it for quering data you downloaded to your database.
https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15
3. Download and install Visual Studio. I used Visual Studio 2019 Enterprise. No idea if it will work on any other versions of Visual Studio.
https://visualstudio.microsoft.com/pl/downloads/
4. Download FFmpeg - it's needed for creating thumbnails from webms
https://www.gyan.dev/ffmpeg/builds/
ffmpeg-git-full.7z
5. Create database on your SQL Server and name it 4ch
6. Create all needed objects on your database(tables and procedures included in 4ch_Database repository)
7. Run query "insert data to board last update.sql" included in "4ch_Database" repository - this query contain boards from which we want to download and store data in database. You can change the query to include different boards.
8. Application will need location to store temporary data. Create folder where you want to store your temporary data.
9. Create folder in your folder for temporary data and name it ffmpeg 
10. Copy bin folder from ffmpeg-git-full.7z you downloaded to ffmpeg folder
11. To start downloading data to your database, open Visual Studio and open project included in 4ch_Downloader repository.
12. Change Project.params in the project:
DatabaseServerName - Server name where you will store your 4chan data
WorkspacePath - Path to folder you created for storing temporary data
13. You can start downloading data - click on Start. If you don't want to deal with PS windows poping up, you can use option "Debug->Start Without Debugging" - single command prompt windows will open after starting.
14. You can check your downloaded data using SQL Server Management Studio or search Interface included in "4chanviewer" repository
