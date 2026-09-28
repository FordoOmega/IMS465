# IMS465

NOTICE: Some folders left out from original project due to sizing issues, hoping Unity regens them automatically with the source files.

Recap: Week 1 I highlighted the coin allocation system from Kingdom Two Crowns, the core mechanic/system that fueled the kingdom building aspect of the game. Essentially, a player stands on a building project (like a dirt mound), and then when standing over it, ghostly coins appear to notify the player of the cost. Then, by pressing and holding the interaction key, the player drops coins into the project and fills the outlines to completion if able.

Architecture: The interface defines several methods, which is then implemented by the Mound script. The player calls upon methods from the interface when raycasting for an interactable object. Update and SetTarget in Player also call upon the interface's methods. Delta time is used both in the timer passing of the coins, and the movement. A coin fills the slot every secondPerCoin seconds of real time, and the speed of the player is consistent across all frame rates.

For the sake of simplicity, and because I don't have the proper skills, I had to cut down on a lot. For example, there is no player purse to check whether or not you have money, it just fills up one way or another. Our slots are also simply determined by how many I hook up to the mound. Our coin simply toggles a different sprite display with no animation, sound, flash, etc. Our downward raycast is different from the proximity cast Kingdom uses, making our version more rigid. There is more, but essentially this prototype captures the core loop, the baseline of what the mechanic is without all the smoothing out and the flashy effects.
