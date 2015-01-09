Callblaster
===========
Callblaster is an application written in PHP for Asterisk to send voice broadcasts. It can generate multiple simultaneous calls to a list of numbers and play a custom audio message. Callblaster can receive DTMF input options and connect to any predefined destinations.
We can find different occasions where Callblaster can solve problems with minimum effort like event management, customer relations, staff management and where ever people like to hear from you.
Call blaster is simple in design and user interface so that anyone can install and start call blasting  within few minutes. Following paragraphs will make you an expert in call blasting.

Key Features
------------
-Supports multiple simultaneous calls to a list of numbers.  
-Separate audio messages for each number.  
-Receives DTMF inputs  
-Dialing Screen displays call status and DTMF response  
-Detailed log for each calls
-Easy to use Management Panel

..............................................
Prerequisite
------------
Asterisk server  
-With trunk and outbound route for making outgoing calls  
FreePbx -optional  
MySql database  
Webserver  
...............................................



Installation
------------
1-Copy all files and directories to a directory  in your web-server where asterisk is installed.

2- Open config.php in a text editor and change database configurations and base path to the installed directory.

Provide your MySql host,database name, database user and database password. Give all privileges on the database to the user.



//Database configuration   
//...........................................  
$db_host="localhost";     
$db_name="callblaster";   
$db_user="root";          
$db_pass="passw0rd";     
//..........................................



Provide path to your directory and Asterisk agi path.
You can change welcome sound file path here.


Provide path to your directory and Asterisk agi path.
You can change welcome sound file path here.

//paths    
//...........................................

$basepath="/var/www/html/callblastergpl/";

$agipath="/var/lib/asterisk/agi-bin/";

$welcomeSound = $basepath."audio/welcome";
//sound file without extension


//...........................................


3- Make sure directories  audio ,files , logs and tmp are writable. (
change file permission to 777)

4- Give write permissions to directory  /var/spool/asterisk.

5- Create a dial plan context for callblaster.
 
If FreePbx is installed in your server , you can create callblaster context in  file extensions_custom.conf .
Open extensions_custom.conf located in /etc/asterisk in a text editor and add following lines at the end of file.


;callblaster context

[callblaster]
exten => 333,1,AGI(/var/www/.....path to..../callblaster.php)

change path to callblaster.php script which is in your base directory of callblaster installation.
Please don't forget to reload asterisk, run core reload in asterisk console.

6- Callblaster needs to run php functions  shell_exec or exec , please ensure your installation is able to run these functions.

Now your Callblaster is ready to use, please go through following line to know how to make your first call blasting.


How to use
----------
Open you browser and point to your callblaster location, you will be directed to Call Blaster Management Panel.

Call Blaster Management Panel has four sections such as Config, Upload and make Calls,Call Logs and Audio Files.

Config section:

This section helps you to set call interval and two destination extensions and related context.
During callblasting your listener will be prompted to choose 1 or 2 and connected to chosen destination. Here you are setting these two destinations.

Upload and make Calls:

This section allow you to upload .csv file contained numbers and preferred audio file names and initiate calls.
Please check sample file numbers-sample.csv and keep the file format for your uploads.


Call Logs:

From this section you can see what happened with your call blasting and what your listeners chosen.

Audio Files:

Here you can upload your custom audio files and make test calls to ensure everything working good.
You can add custom files in any way by putting files in asterisk supported format in audio directory.



Who we are:
-----------
Callblaster is developed at Nethram.Nethram is a Silicon Valley based telecommunications and cloud innovator. Our mission is to provide the cloud telephony solutions that the big boys use at an affordable price by listening to your needs and providing you with what you actually want.

Thank you for using Callblaster, please don't hesitate to write to us at
support@nethram.com. Find more about us at our website www.nethram.com



