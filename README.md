# Game
Public repository coming Soon™

# Sitekick Remastered

[![Discord](https://img.shields.io/discord/603580736250970144.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.gg/eKR2FKP)

Welcome to the repository for [Sitekick Remastered](https://sitekickremastered.com/)! 

# Setting up your Local Environment

## Software Needed
1. [Unity Hub](https://unity3d.com/get-unity/download)
1. [Unity 2021.3.8f1](https://unity3d.com/get-unity/download/archive)
1. [MySQL](https://dev.mysql.com/downloads/) (I recommend downloading the MySQL Installer and installing the items through there)
1. [Visual Studio](https://visualstudio.microsoft.com/vs/community/) or [VSCode](https://code.visualstudio.com/) (VS Code will require some more setup to utilize the C# Server Solution)

## Creating your Local Database
1. Go through the MySQL Server setup and create a local mySQL database on port 3306. 
1. Once you have that created, run the [schema](https://github.com/coolpick/sidekick/blob/master/Server/Database/schema.sql) and [data](https://github.com/coolpick/sidekick/blob/master/Server/Database/data.sql) files to get the database filled with the correct tables and data.
1. You'll need to manually add your account to the `accounts` table. One of the current developers should be able to get your the values you need for your `password` and `password_salt`. Make sure you have `Verified = 1`
1. Once you have that and your database is running we can move on to setting up the Server

## Running the Local Server
1. The Server solution is located in [`/Server/Project/SitekickServer.sln`](https://github.com/coolpick/sidekick/tree/master/Server/Project).
1. You will need to update your `Server.config` file to match your local database created in the last step. The file is located at [/Server/Project/SitekickServer/Server.config](https://github.com/coolpick/sidekick/blob/master/Server/Project/SitekickServer/Server.config)
1. Once you have the updated `Server.config` you should be able to run the Server either via your IDE or by the executable itself (created after you build it for the first time). Once it's running it should look like this ![Webserver Running](https://i.imgur.com/MfpPB4n.png)
### NOTE: Building the Server Solution after changes
If you make any changes to the `SharedServices` project you'll need to build the solution in `Release` configuration so it copys the `.dll` file to the correct area for Unity.

## Setting up the Local Environment in Unity
1. To open the project in Unity you'll need to select the `Sidekick`. 
1. Once you have it open you'll need to update a few variables before you run it for the first time.
1. Go to `File > Build Settings` and it should be set to `Windows, Mac, Linux`. Check off the `Development Build` box. It should look like this ![Build Settings](https://i.imgur.com/DV48aCP.png)
1. Go to `Player Settings` at the bottom of the window above. Make sure the `Version` is set to the most current version. ![Version](https://i.imgur.com/fg761vX.png)
1. Close out of these settings and navigate to `Assests/Data/GameConstants.asset` or search for it via the Search bar. 
1. Set your Target Server to `Local` ![Local](https://i.imgur.com/oEfw7a5.png)

## Running in Unity
1. You do not need to build in Unity. You can utilize the Play functionality at the top of the screen. 
1. To do this, navigate to `Assets/Scenes` and choose the `Login` scene.
1. Click on the Play button and it should start running in the `Game` display in Unity. 
1. Login with your credentials that you manually input into the `accounts` table when setting up your database. It will cache your credentials as well.
![Running](https://i.imgur.com/DMuBu5v.gif)
