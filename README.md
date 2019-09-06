# BBC-Microbit-Project

### Program Source Reference URL
For our project, we combined three existing pieces of code from [this](https://microbit-micropython.readthedocs.io/en/latest/tutorials/introduction.html) website. The three pieces of code we used from this website included code to make our microbit [play music](https://microbit-micropython.readthedocs.io/en/latest/tutorials/music.html#wolfgang-amadeus-microbit), [detect gestures](https://microbit-micropython.readthedocs.io/en/latest/tutorials/gestures.html#magic-8) and [speak](https://microbit-micropython.readthedocs.io/en/latest/tutorials/speech.html).

### Program Description
Our final program is a game. The microbit starts off by displaying a question mark. When the microbit is shaken, it randomly selects one of four characters from the classic video game *Super Mario Bros*. The character's name scrolls across the screen, then the microbit intoduces itself as the character (speaking in a modified voice to suit the character). After this, the microbit plays the chorus of the video game's theme song. The process is now completed, meaning that the microbit will display the question mark once more, ready for the next round of the game. 

### Python Code Listing
This is our code:
```
from microbit import *
import music
import speech
import random
answers=["Mario","Luigi","Peach","Bowser"]
theme_song = ["E3:1","E3:1","R:1","E3:1","R:1","C3:1","E:2","G4:2","R:2","G3:1"]
while True:
    display.show("?")
    if accelerometer.was_gesture("shake"):
      display.clear()
      sleep(1000)
      choice=random.choice(answers)
      if choice=="Mario":
         display.scroll("Mario")
         speech.say("It's-a-me Mario", pitch=30,speed=90)
      if choice=="Luigi":
         display.scroll("Luigi")
         speech.say("LOOIYJIY time!",pitch=30,speed=90)
      if choice=="Peach":
         display.scroll("Peach")
         speech.say("Everything's Peachy!",pitch=25,speed=90)
      if choice=="Bowser":
         display.scroll("Bowser")
         speech.say("Mwah ha ha ha",pitch=120,speed=255)
      sleep (1000)
      music.play(theme_song)
```

### BBC Microbit Sensors or Characteristics Used / Showcased
The microbit characteristcs that we used were speech, gestures and music. We used the built-in accelerometer in the microbit so that when the microbit is shaken, the movement is detected and the microbit chooses from one of the four game characters options.

### Testing Information
We tested our project by first making sure that all three aspects of the code were working correctly separately. For example, we tested that our figured-out theme song was working properly. For this, we found the pitch key to be wrong and altered it accordingly. Then, we realised that the random generator that selected a character would always give the first character in the list after testing it a couple of times - we found that commas between the items in the list of characters were missing. Once we had fixed this, the program was able to output all the different characters. The microbit was also unable to correctly pronounce the name “Luigi” and we fixed this issue by spelling his name phonetically. The hardest problem we faced was modifying the voice settings to make each character sound like their counterpart in the original video game. We did this by researching how to modify the voice and then, by trial and error, adjusting the pitch and speed of each character’s voice until it sounded right.
We followed the process of using the code from our sources and adjusting it to suit our desired outcome. We tested the program and identified problems. Next, we went back to fixing the issue and tried again until the code worked the way we wanted it to. If the code seemed to be working perfectly, we would test it three more times to triple-check. When the speech, randomisation and theme song elements were working correctly in multiple tests, we amalgamated the codes and tested the final project. After this, we fixed a few more issues and tested it multiple times again to ensure it was working correctly. 

### Ideas to Extend the Project
Our extension ideas are as follows: 
-We could add more characters from the *Super Mario Bros* videogame- such as Yoshi the Dinosaur. In this case, the LED display would show "Yoshi" and the micro bit would say "Yoshi!" in a voice setting similar to that of Yoshi's in the game itself.
-After Peach (the princess whom Mario has to rescue in order to win the game) has said her catchphrase of "Everything's Peachy!" and the theme song has played, the LED display on the micro bit would show "You Win!" as a reference to the original game.
-Bowser is the villian of *Super Mario Bros* and if he defeats Mario at the end of the game, the screen would display "Game Over." As a reference to this idea, after the Bowser on the micro bit has said his catchphrase of "Mwah ha ha" and the micro bit has played the theme song, the LED display could show "Game Over" and the micro bit would shut down, indicating the player has "lost" the game.
-If we were to not use the Bowser extension idea above, we could use this idea instead. If the player were to get Bowser three times in a row, then the LED display would show a "fireball" (referencing Bowers' ability to create fireballs) and the micro bit would play a "whooshing" sound to accompany the fireball.
-If the player were to get Mario (the hero of the game) three times in a row, the micro bit would play the "1UP" sound and show a mushroom on the LED display. This references a mushroom in the game that gives Mario an extra life- a 1UP mushroom.
-Finally, if the player has played the game 5 times (gotten 5 characters), the micro bit LED display would show a star, and the "Super Star" music would play. After this, the display would show "Thank You For Playing!". The star references the Super Star in *Super Mario Bros* that makes Mario invincible for a short time. The appreciation message references how if a player completed *Super Mario Bros* to 100%, the developers included a hidden secret and thank you message in the game.
