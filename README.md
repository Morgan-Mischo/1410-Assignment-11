# 1410-Assignment-11
Asteroids
The main method is in the Asteroids class.  Run the game, such as it is.  This is what you should see:

It begins with a splash screen with one asteroid floating around.

When you click the "Start Game" button, the game starts.  A ship appears in the center of the screen.  You can rotate the ship by using the right arrow button, but that's the only way you have to control the ship.  

After about two seconds, the ship will start accelerating.  You will be able to (sort of) control its direction by turning right.

Eventually, the asteroid and the ship will collide.  Both will disappear and the game will end.
 

Now run AsteroidsDemo.jar, which should be in your project.  You will see that the full game is quite a bit different.  Most of the differences will be quite obvious, but I'll point some out here:

The splash screen and the initial screen have four asteroids.

There is a on-screen display showing lives remaining, level, and score.  The ship gets three lives initially.

The ship does not move autonomously.  Instead, you can accelerate it in the direction it is pointing with the up-arrow or W key.  There is a maximum speed to which a ship can accelerate.

You can turn left with either the left-arrow or A key.  You can turn right with either the right-arrow or D key.

When you accelerate the ship, a small flame is animated.

You can fire bullets by pressing the down-arrow, S, or space key.  There can be at most eight bullets flying around at any given time.  A bullet disappears when it hits something or when it has reached its maximum range.

When a large asteroid collides with a bullet or a ship, the asteroid splits into two medium asteroids.  When a medium asteroid collides, it splits into two small asteroids.  When a small asteroid collides, it disappears.

Transient "dust" appears briefly when an asteroid splits or disappears.

Transient "debris" appears briefly when the ship is hit.

The game score goes up by 20 points when a large asteroid splits, by 50 points when a medium asteroid splits, and by 100 points when a small asteroid disappears.

At the beginning of the game, four large asteroids are placed in the vicinity of the four corners of the screen.  The exact position is randomly chosen, as is the rotation and direction of the asteroid.  There are three speed limits for asteroids: slow, medium, and fast.  A large-sized asteroid always has the slow speed.  A medium-sized asteroid has a randomly chosen speed that lies between slow and medium.  A small-size asteroid has a randomly chosen speed that lies between slow and fast.

Each time a new level is reached (i.e., each time all the asteroids on the screen are destroyed), new large asteroids appear.  The number of these large asteroids increases by one from the previous level.  At the beginning of the game, there are four large asteroids; at level 2, there are five; at level 3, there are six; and so on.

Ship rotation and thruster firing work smoothly in the complete game.  The control in the stripped-down game are very awkward by comparison.

At level 2, a medium size alien ship appears 5-10 seconds after the level begins.  It follows a zig-zag path, periodically firing bullets in random directions.  It starts off screen and goes in a direction either left-to-right or right-to-left across the screen.  It randomly zig-zags in three directions: either perfectly horizontal, or at a slight angle one radian upward or downward from horizontal.  When it is destroyed, you earn 200 points.  About 5-10 seconds later, it appears again.

At level 3 and above, the medium alien ship stops appearing and the small alien ship appears instead.  The small alien ship zig-zags the same as the medium alien ship, but moves faster and fires bullets toward the ship.  (Specifically, it fires in a randomly chosen direction that is within five degrees of the direction of the center of the ship.)  Its destruction earns you 1000 points.

There are sound effects. 

Implementation
Once you understand how the full game differs from the partial implementation, your job is to complete the partial implementation.  Here's how to get started:

Generate the documentation.  Select the project.  In the Project menu at the top of Eclipse, choose Generate Javadoc.  In the dialog that appears, make sure that your project is selected.  For the "Javadoc command" enter the full path of the javadoc executable that is in the bin folder of your Java installation.  (For me, on Windows, that path is C:\Program Files\Java\jdk10.0.2\bin\javadoc.exe.)  Specify that documentation for private members should be created and that the documentation should be placed in a "doc" folder in the project folder.  Generate the documentation, open the new doc folder, and double click on index.html.  You'll see the Javadoc for the project organized for you.

Study the documentation and the implementation and get a feel for how the classes and interfaces fit together.  We will discuss the implementation in the labs and in lecture.  Some classes you will not need to modify; other classes will require extensive modification.  It is important to understand how the implementation is designed so that you will have a good feel for where to make different kinds of changes.  

Get the ship motion working smoothly.  The Controller class contains the code that interacts with the keyboard, so you'll need to make changes there.  The key is to make tiny adjustments to the ship's direction and acceleration once per frame, instead of once per key press event.
 
Create classes that represent bullets and debris.  Look at the  Ship and Asteroid classes for inspiration.  Notice that both of those classes extend Participant.  Your Bullet and Debris classes should extend Participant as well.

Change the Controller and Ship classes so that ships can fire bullets.  Change the Asteroid and Ship classes so that Debris appears when asteroids and ships are destroyed.

Work on sound.  The "sounds" package contains the nine .wav files that you'll  need, along with a class SoundDemo that shows how to create and play sound clips.

Proceed with the rest of the modifications.
You will notice that there are lots of comments in my partial implementation.  I expect you to document your work in the same fashion.
