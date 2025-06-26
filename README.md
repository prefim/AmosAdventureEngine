# AmosAdventureEngine
Text adventure engine created in Amospro.

Hey there!

Thanks for checking this very early alpha out of my Amos Adventure Engine. This is a small test adventure created with it to check things work as expected, that I've not missed anything too obvious and so on. Its set in a world of castles, knights and villagers with a sprinkling of fairytales in there too. As each location supports an image, I've added one for each in the demo. these are just placeholder images. Please don't read too much into the quality!

I'd love to hear your thoughts, bugs you found, possible improvements so please drop me an email to:- mat@preferredimage.co.uk


HOW TO PLAY THE DEMO
So here is a basic run down of what you can do. I'm sure you've all played a text adventure over the years.

MOVEMENT
Exploring the world is kind of the point. The engine supports 8 compass directions as well as up and down. You can use shorthand as well as full words so 'NORTHEAST' and 'NE' both work for example.

TAKING THINGS
Being able to take things you find can be useful elsewhere in the world. So you can 'GET' or 'TAKE' a thing. Most objects in the world will be single words like EGG or BALL. Some may be two words like WOODEN BOWL or METAL SWORD so you'd use 'GET WOODEN BOWL' or 'TAKE METAL SWORD' etc. Some objects aren't allowed to be picked up. Maybe there's a lever on a wall or a statue in a room that's just not going with you. Characters are currently treated as objects you can't take if they are a state change required (like alive to dead).

DROPPING THINGS
Just as important to gathering up everything in the game is putting stuff down again. 'DROP' will let you place that thing, in that room.

INVENTORY
Knowing what you are carrying on you can help decide how to proceed. So 'INVENTORY' or 'INV' will list what its got in its pocketses.

LOOK
Getting a refresher on the location you are in will clear the text panel and redescribe where you are as well as list any objects that are present. 'LOOK', 'DESCRIBE' or 'WHERE AM I' are the commands to use for that.

EXAMINE
Often, more detail means more knowledge. So 'EXAMINE' a thing to learn more. This might be an object you are carrying, and object in the location or a detail of the location itself. EXAMINE RIVER might tell you if its cold and wet for example.

USING THINGS (WITH OTHER THINGS)
The bulk of any adventure is doing stuff. To that end, the engine supports actions. these are usually specific actions for specific objects, sometimes requiring to be in a specific room. 'DRINK WATER' might be a glass of water you have picked up to refresh you or it could be a well. 'TALK TO WIZARD' would strike up a chat with a nearby professional magician and hopefully get you information, objects or whatever. Actions lead to consequences however. 'ATTACK KNIGHT' might not get you a win. 'USE WITH' is also something you can do here. 'USE STRING WITH GUITAR' could make a broken guitar playable again. Action words will take some thinking about. this is kind of the meat and potatoes of adventuring.

QUITTING
You can quit out the game by typing 'QUIT', you'll need to confirm you've had enough but this will bail right back to workbench / CLI.

HOW THE ENGINE FUNCTIONS
The engine supports a 32 colour IFF image per room to help flesh out the text description. In the ROOMS folder its ROOMX.iff
The text is stored in a ROOMX.DSC file in the same folder. one file for each room. Also in that file is short words and long descriptions of location based things with more info. 
In the ROOMS folder there is also a START and BLANK set of room files. START is for the opening page when the game runs. BLANK is used as a catch all in case an image or text file is missing for that room number.

In the ENGINE folder are several functional files to make the game work within the engine. ADVENTURE.MAP is an array file which lists all the room numbers and their movement links to other rooms. There's a RESPONSES.TXT file which lists response lines for the engine to use like 'You can't go that way' or 'That's not going to happen' etc. The OBJECTS.TXT file contains a list of objects in the game, the structure and layout is quite particular in here. ACTIONS.TXT is the master list of specific game commands (aside from the ones mentioned above which are hardcoded into the engine). Again, structure is key here, an additional line break etc. could mess up the reading of the file. 

WHAT CAN THE ENGINE DO IN GAME?
The engine runs what I've called an action script. When you request an action to be performed, lets say 'ATTACK WIZARD', there are various things the engine can do as part of the script linked to that action. Firstly the engine checks if object or location requirements are met, then the script is run through. This can include killing the player, removing or adding an object from your inventory, changing an objects state, placing an object in the location, adding or removing a direction to a location (not just the one you are in), swapping one location with another (not just the one you might be in) and moving you instantly to another location. from these simple commands, I've found I've been able to do most things but I'm sure I could add to this script list.


WHAT WOULD I LIKE FROM YOU
I'm already thinking of things I could add to this (health, inventory weight limits, characters that move around the map with you etc.). But it would be great to hear from you if you think I've missed anything obvious, if something doesn't work the way you thought it might or just what your thought in general. I started this project because as a kid, I've written the odd adventure where you hardcode it into basic, but never an engine that reads the files in meaning its the same executable just working with different data so gave it a go as a challenge to myself. 
