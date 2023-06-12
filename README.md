# InteractiveFictionGamingSystem
  I want to build an interactive novel game system.   To put it simply, the story starts with one beginning, and there will be plot branches in the middle, instead of the original single line, and the end of the story may be multiple.  Based on players typing instructions on the keyboard in the game -- Digital Interactive Novel Game Management System
  
  [Please add entities (namely users (namely players) and administrators (namely people 
who manipulate and manage clients)) into the following expository if you wanna know the whole sturcture the system is.]
  
  I want to build an interactive novel game system. Interactive novel, in simple terms, is that 
the story begins with one, and there will be story branches in the middle, which is no longer the 
original single line, and the end of the story may be multiple. The basic game rules (not all) of the 
interactive novel game in this system are based on the player typing instructions on the keyboard 
in the game. After the system recognizes the instructions, the corresponding information is fed 
back and output to the client. This system is to create a digital interactive novel game 
management system.

  The detailed functional requirements include:

  1. The main system interface:
  There are background (is a piece of wallpaper, the content is dark gold, and always moves 
in the opposite direction of the player's mouse movement direction), level thumbnail button 
(click (that is, mouse click, subsequent click synonymous) to enter each game subsystem), save 
button (click to enter the save interface) system Settings button (click to enter the Settings 
interface), About and help button (click to enter the user's operation guide interface), exit button 
(click will pop up a prompt window, declare "whether to exit the system", and there are "yes" and 
"no" two buttons, click "yes" button, you can launch the system; Click the "no" button, you can 
directly close the prompt window).

  2. Game Subsystem:
  Click different thumbnails on the main page of the system to enter, at this time, the page 
is similar to the interface of the command prompt, and the function is similar to the command 
prompt -- the player also inputs the instructions through the keyboard, and the system identifies 
and outputs the corresponding one or different results according to the player's instructions. Just 
enter the system will automatically output a text (with a text to clarify the details of the game 
background or tips), the player's general input format is: English words and phrases, numbers 
these three formats.
  The plot text of the subsystem includes: a piece of text (referred to as background) that 
has just entered the automatic output of the subsystem, and the subsequent plot (the 
subsequent plot is processed in sections, and the attributes include: plot id, plot content (string 
class)).
   Each subsystem has two different sets, namely, the verb set and the noun set
   The noun set includes all nouns in the subsystem text, which are generally divided into 
entity class and object class. The entity class contains all person names in the subsystem text 
(person name attributes include: entity id (primary key int type), person name (string type), and 
person existence state (int type), and the state includes: 1, 2, 3 (meaning alive, dead, not in the 
scene in turn)), and the entity class contains all nouns in the subsystem text other than the name 
(noun attributes include: real object id (main key int type), noun name (string type), and real 
object existence state (int type), and the state includes: 1, 2, 3 (meaning in turn intact, damaged, 
not in the scene)).
  The verb set is the base verb instruction, including: "Open", "close", "difference", "pick 
up", "look at", a "push" and "pull", "talk to", "use", "go to", "to", "with" using these verbs, You 
are not allowed to capitalize anything but the first letter of the word, otherwise the screen will 
print "How old are you, this *" (the asterisk refers to the name of the instruction), and the player 
can re-enter it later. The instruction format is usually "basic verb instruction" (those verbs) or 
"basic verb instruction" + "noun" (i.e., phrase). If the instruction (English verb + noun), in the 
instruction entered by the player, the English verb is not in the basic instruction, the interface will 
output "I don't understand what you are saying", and the player can re-type after that; If the 
noun doesn't exist in the current plot, the interface will print "You did something meaningless", 
and the player can re-type it; When the noun in the phrase is not part of the episode (i.e., the 
character name has a task presence state of 3; Or a value of 3 for the noun's physical presence), 
the interface outputs "none" or "not here," depending on the type of noun. When the user 
enters the English verb + noun correctly, the system will output the corresponding subsequent 
text plot. In addition, the basic verb instruction "to" is generally combined with "give" in the 
format of "give" + noun 1 + "to" + noun 2 ". Here, for example, noun 1 and noun 2 only restrict 
the entity class in the noun set (the instruction rules follow the rules described just after the
general format); The basic verb instruction "with" will generally be combined with "use", the 
format is "use" + noun 1 + "with" + noun 2 ", the example of noun 1 and noun 2 here only restrict 
the entity class in the noun set (the instruction rule follows the rules described after the general 
format just described).
  In some plot segments output by the interface, they have a time limit. In other words, 
when the output of the plot segment is delayed by one second after the interface, the timer is 
triggered, that is, the interface starts to output the 11 integer numbers in reverse order from 10 
to 0 every two seconds. Input the relevant instructions before the output of 0, and the interface 
will output the corresponding plot segment. If the syntax error follows the syntax execution rules 
after the general instruction format; If the player does not act, the interface will output the 
corresponding plot segment that does not enter the instruction.
  When the player hits the "esc" key on the keyboard in the game subsy stem interface, a 
black semi-transparent interface with the same size as the current interface will pop up to cover 
the current interface, and the game subsystem interface data can no longer be directly 
manipulated. We call this interface pause. The center of the interface is on the right side to 
output the text in the user guide interface, and the center is on the left side. There are two 
buttons up and down in a column, which are the archive and exit subsystems. At this time, if you 
hit the esc button in the keyboard, the interface will be closed, and the game subsystem can 
continue to operate; If you click the save button, the game subsystem related data will be stored 
in a storage block of the save interface; A prompt box that lasts two seconds will pop up on the 
interface, and the box will show that the storage is successful; If you click the button to launch 
the subsystem, a prompt window will pop up on the interface, declaring "whether to quit the 
game", and there are two buttons of "yes" and "No". Click the "Yes" button to launch the game 
subsystem and return to the main interface of the system; Click the "No" button to directly close 
the prompt window.

  3. Player operation guide interface:
  Click on the About and Help buttons in the main system interface to access this interface. 
The interface has a black background, and is center-aligned to output all verbs in the action set in 
the content description of the game subsystem, each verb is separated by a distance of four bytes, 
each four verbs as a line, and the basic verb instruction usage specification of another line. The 
player will return to the main interface of the system after hitting the "esc" key on the keyboard.

  4. Save screen
  Click the save button in the main interface of the system to jump to the archive page. The 
archive interface is a black background wallpaper. There are three lines in the interface, two lines 
in total, and six white boxes, which are visualized game storage blocks. The box of the storage 
block will display the saving time (year, month, day), the name of the game subsystem and the id 
of the game subsystem (the three are the attributes of the storage block set, in which the saving 
time is date type, the name of the game subsystem is string type, and the game subsystem id is 
int type). If the storage block is clicked, all kinds of data stored in the game subsystem will be 
read. The system will jump to the game subsystem where the data state is stored. And click the 
"esc" key in the keyboard, the save interface is closed, and the system jumps to the main system 
interface.

  5. Setup interface
  Click the system Settings button in the main system interface to jump to the setting 
interface, the setting interface is a black background wallpaper, there is a click interactive text 
"clear the archive record", click will delete all the stored time point data, only this function, there 
is no other function. And click the "esc" key in the keyboard, set the interface to close, and the 
system jumps to the main system interface.

  6. Login interface: 
  Before entering the main system, you will enter the login interface with 
a white background and a light yellow pop-up window in the middle, which contains the user 
name, password, and the input box of the user name and password (the format of the user name 
input box is text type, the format of the password input box is password type), and the login and 
registration buttons. At the same time, check whether the player's system is connected to the 
network, if not, then pop up a white translucent interface covering the entire login interface, the 
small pop-up window shows "no network connection", the player can hit the "esc" key in the 
keyboard, at this time, the system will judge the player's system network connection state again, 
until the network connection is normal and no more poop pops up. After the player correctly 
input the user name and password will close the login interface, jump to the system main 
interface, which keeps the appearance of the last time the player used the system and the final 
modification of all the player's archive data; Click the registration button, leave the pop-up 
window to call a new pop-up window, which contains the user name Settings, please enter the 
password, please confirm the password of the three texts and the corresponding input box of the 
three texts, plus the registration button. When a new player sets a username and password, the 
username format is limited to numbers and upper - and lowercase letters, and the number of 
digits is between 1 and 12; The password format is limited to digits and uppercase letters, and 
the digits are between 8-15. At the same time, judge whether the content of the new player's 
password is consistent with that of the new player's password. If it is inconsistent, a small 
window will pop up for 1 second to display "password inconsistent"; If the user name is 
consistent with the user name of the player in the cloud database, a small window for 1 second 
will pop up to display "repeat user name". If all the conditions are met, click the registration 
button, and the new player information data (username and password as well as the default data 
storage of the system (referring to all the original records of the system plus the first login time of 
the new user)) will be uploaded to the cloud database. At the same time, close the interface and 
jump to the initial default system main interface.

  7. Cloud player database: 
  The platform stores the user name and password of all 
registered users and all game data of corresponding players in the cloud, which will be called 
every time the player uses the login interface; At the same time, the user name and password as 
well as the system default data will be stored in the database (Mysql linked list structure) after 
the new player registers the account.
 
  Specialized Functional requirements definition and description of functional requirements are as follows:

  1. System main interface:
 - Background version: with the content of the gradient dark gold wallpaper, with the player's 
mouse movement direction in the opposite direction of movement.
 - Level thumbnail button: Click the button to access each game subsystem.
 -Save button: Click the button to access the save screen.
 -System Settings button: Click the button to enter the Settings interface.
 -About and Help buttons: Click on the button to enter the player operation guide interface.
 - Exit button: Click the button to pop up a prompt window asking whether to exit the system, 
click yes to exit the system, click otherwise to close the prompt window.

  2. Game subsystem:
 - Click on the level thumbnail to enter the game subsystem, which is displayed in a command 
prompt like interface.
 - The player enters instructions through the keyboard, and recognizes and outputs the 
corresponding results according to the instructions.
 -The initial entry subsystem will automatically output a text containing details or hints about 
the game's background.
 -Player input formats include English words, phrases, and numbers.
 -The plot text of the subsystem is divided into background and subsequent plots, and each 
plot has a corresponding plot id and plot content.
 -The subsystem contains the verb set and the noun set, and the noun set includes the entity 
class and the object class.
 -The verb set includes the base verb instructions, which the player enters through the 
keyboard to operate.
 -The interface outputs and processes the instructions based on their format and content, and 
outputs the corresponding subsequent text plot.
 - The plot segment has a time limit, and the player enters the relevant instructions before the 
countdown ends to trigger the corresponding plot segment.

  3. User guide interface:
 - Click the About and Help buttons in the main system interface to enter the user's operation 
guide interface.
 -The interface is presented with a black background, and the action set and basic verb 
instruction usage specifications in the game subsystem are output in the middle center.
 - The player can return to the main system screen by pressing the "esc" key on the keyboard.

  4. Save screen:
 - Click the archive button in the main system interface to enter the archive interface.
 - The interface is presented on a black background and contains visualized game storage 
blocks, each of which displays the time of saving, game subsystem name, and id.
 - Click on the storage block to read the corresponding game subsystem data and jump to that 
game subsystem.
 - Click the "esc" key on the keyboard to close the archive screen and return to the main 
system screen.

  5. Set the functional requirements of the interface:
 - Users click the system Settings button in the main system interface to jump to the Settings 
interface.
 - The Settings screen presents a black background wallpaper containing a clickable text label 
"Clear archive records".
 - When the user clicks on the "Clear Archive Record" text label, the system will delete all 
stored data for the archived time point.
 -There are no other functions in the Settings interface.
 - The user can close the Settings screen by pressing the "esc" key in the keyboard.
 - After closing the Settings screen, the system will return to the main system screen.

  6. Functional requirements of login interface:
 - The user will enter the login screen before entering the main system.
 - The login screen has a white background and a light yellow popup.
 - The login screen contains the username, password and the corresponding input field (the 
username input field is text type, the password input field is password type).
 - The login screen also contains login and Register buttons.
 - Before entering the login screen, the system checks if the player's system is connected to 
the network. If not, a white translucent screen will be displayed that covers the entire login 
screen, and a small pop-up window will be displayed saying "No network connection".
 - The user can press the "esc" key on the keyboard, at which time the system will check the 
network connection status of the player's system again until the network connection is normal.
 - After the user enters the username and password correctly, the login screen will close and 
jump to the main system screen.
 - In the main system interface, keep the data state of the last logged-in player and the latest 
modified data of all saved data.
 -Users can click the registration button, and a new window will pop up, which contains the 
three texts of user name setting, please enter password, please confirm password, and the 
corresponding input box, as well as the registration button.
 - When a new player sets a username and password, the format of the username is limited to 
numbers and upper - and lowercase letters, and the number of bits is between 1-12.
 - The password format is limited to numbers and upper - and lowercase letters with between 
8-15 digits.
 - The system verifies that what the new player entered in "Please enter password" and 
"Please Confirm Password" is the same. If they don't, a small window that lasts 1 second will pop 
up saying "Password Inconsistent."
 - The system verifies that the new player's username is a duplicate of the player's username 
in the cloud database. If it does, a small window that lasts 1 second will pop up showing 
"Duplicate username".
 - When all the conditions are met, after the user clicks the register button, the new player's 
information data (username and password) and the system's default data storage will be 
uploaded to the cloud player database.
 - After successful registration, the interface will close and jump to the initial default system 
main interface.

  7. Cloud Player Database:
- The system needs to provide a cloud player database to store the username, password of all 
registered users and all game data of the corresponding player.
- The database should adopt Mysql's linked list structure to organize the data.
- In the login interface, the system needs to call the cloud player database to verify the 
correctness of the user name and password entered by the player.
- After a new player registers an account, the system should upload the user name, password and 
the system default data storage to the cloud player database.
- Cloud player database functions include storing and retrieving player data so that when a player 
logs in, they can restore the state of their last use of the system and all archived final modified
data.
