# BBC-Microbit-Project

### Program source reference URL
For our project, we combined three existing pieces of code from [this](https://microbit-micropython.readthedocs.io/en/latest/tutorials/introduction.html) website. The three pieces of code we used from this website included code to make our microbit [play music](https://microbit-micropython.readthedocs.io/en/latest/tutorials/music.html#wolfgang-amadeus-microbit), [detect gestures](https://microbit-micropython.readthedocs.io/en/latest/tutorials/gestures.html#magic-8) and [speak](https://microbit-micropython.readthedocs.io/en/latest/tutorials/speech.html).

### Program description
Our final program is a sort of game. The microbit starts off by displaying a question mark. When the microbit is shaken, it randomly selects one of four characters from the classic video game *Super Mario Bros*. The character's name scrolls across the screen, then the microbit intoduces itself as the character (speaking in a modified voice to suit the character). After this, the microbit plays the chorus of the video game's theme song. The process is now completed, meaning that the microbit will display the question mark once more, ready for the next round of the game. 

### Python Code listing
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

### BBC Microbit sensors or characteristics used / showcased
The microbit characteristcs that we used were speech, gestures and music. We used the built-in accelerometer in the microbit so that when the microbit is shaken, the movement is detected and the microbit chooses from one of the four game characters options.

### Testing information
We tested our project by first making sure that all three aspects of the code were working correctly separately. For example, we tested that the theme song that we figured out was working properly. In that case, we found the key to be wrong and altered it accordingly. Another time we realised that the random generator that selected a character would always give the first character in the list after testing a couple of times - we found that commas between the items in the list of characters were missing. Once we had fixed this, the program was able to output all the different characters. The microbit was also unable to correctly pronounce the name “Luigi” and we fixed this issue by spelling his name phonetically. The hardest problem we faced was modifying the voice settings to make each character sound like their counterpart in the original video game. We did this by researching how to modify the voice and then, by trial and error, adjusting the pitch and speed of each character’s voice until it sounded right.
We followed the process of using the code from our sources and adjusted it to suit our desired outcome. We tested the program and identify problems. Next we would go back to fixing the issue and try again until the code worked the way we wanted it to. If the code seemed to be working perfectly, we would test it three more times to triple-check. When the speech, randomisation and theme song elements were working correctly in multiple tests, we amalgamated the codes and tested the final project. After this, we fixed a few issues and tested it multiple times again to ensure it was working correctly. 

