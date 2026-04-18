<!-- In Chapter  13 and 14, refactoring was done for better organization.  If you were redesigning this project again, explain which modules and classes you would create to better organize the game than what we have currently done in class.  You do not need to go into full detail just explain how the project would be organized and why it would be better than what you currently have. -->

# For this prompt I chose question 2

## Child parent relationship

If I were to redesign this project I would change all the classes to have a parent and child relationship that is similar to a hierarchy. I have noticed that a reference to the main game instance is passed to most classes and I believe that is is unnecessary.

## Alien Modifications

I believe that the alien class should not know about the settings, boundaries, or screen. To get around this I would add attributes to the alien class for speed, width, and instead of the 'check_edges' method I would have the AlienFleet check the position of the alien. Instead of having the alien render itself to the screen directly, I would have it return an image to the main game loop that is then rendered to the screen. The AlienFleet would have to gather all the images from the aliens, then return them to the game loop as an array. This would definitely have to be an interface as each class within the game would be required to have a method that returns a final rendered image representing the state of the sprite (it already does with the draw method but renders to screen directly)

## HUD Modifications

I would implement this same kind of behavior for the HUD because I believe that the HUD should not be concerned with anything that goes on within the game, it should only display what it is being told to display.

## ShipArsenal Modifications

I would also modify the ShipArsenal class to allow you to fire any kind of bullet instead of just the Bullet class. This would require implementing an interface for the base Bullet class and the child classes then you would pass the Bullet in as an argument to the 'ShipArsenal.create_bullet' method.

## Conclusion

These modifications may be over the top, but I would definitely implement them if I were to add more features within the game.