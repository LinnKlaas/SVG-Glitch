# SVG Glitchen - Linn Klaas
## Dokumentation

Aufgabe: Durch Ausprobieren herausfinden, wie SVGs aufgebaut sind, um dann gezielt glitchen zu können.

Ziel: Icons so zu glitchen, dass sie Ähnlichkeiten von Space Invaders haben.

Icons wurden von folgender Website verwendet: https://ionicons.com

1. Zuerst habe ich mir zwei Icons von der Website gedownloaded und diese in VS Code importiert. Die Katze habe ich so gelassen wie sie war, das zweite Icon (eine Steckdose) habe ich mit der Katze kombiniert und an verschiedenen Stellen Zahlen entfernt, sodass das Endprodukt etwas angeschossen aussieht. Um dies besser darzustellen, habe ich ebenfalls die Farbe zu rot geändert.

2. Da Space Invaders ja pixelig sind, müssen nun auch meine Icons verpixelt werden. Dazu habe ich den Filter auf der Seite https://codesandbox.io/s/static-3yslm angewendet. Zunächst musste ich mir erstmal alles durchlesen, um zu verstehen, was welche Funktion besitzt. Danach habe ich angefangen den Filter umzubauen, um ihn auf meine Icons anzuwenden. Zunächst habe ich die *id* umbenannt, sowie den *path* durch meinen ausgetauscht. Dann muss noch die Bezeichnung bei *href* geändert, und die Zeile *use href="#wifi" fill="rgb(255,0,0)"* gelöscht werden, damit nur das verpixelte Icon angezeigt wird.

3. Jetzt kann man mit den Zeilen im *filter* tag spielen. Ich habe so ziemlich alles ausprobiert und geguckt, was die einzelen Zahlen bewirken. Zum Schluss habe ich mich für viele Quadrate nebeneinander entschieden, da der Effekt der Pixel, meiner Meinung nach, so am stärksten hervortritt. Dazu habe ich 0 bei *feFlood x="0"* für x eingesetzt, sowie bei *feComposite width="20" height="20"* jeweils 20.

4. Nun habe ich beide "Space Invaders" in ein SVG zusammengefügt. Allerdings hatte ich dann das Problem, dass beide übereinander lagen. Das habe ich dann mit der x-Koordinate bei *transform="translate(5, 0)"* gelöst.

5. Um das Ganze mehr wie bei Space Invaders aussehen zu lassen, wollte ich die zwei gepixelten Icons bewegen lassen. Das habe ich hiermit umgesetzt:

   *animateTransform attributeName="transform"  
type="translate"  
from="-520 20"  
to="520 20"  
begin="0s"  
dur="5s"  
repeatCount="indefinite"*

6. Zu guter letzt, um dem Ganzen einen kleinen Feinschliff zu geben, habe ich mir vorgenommen, die Icons zu beschießen. Dafür habe ich drei Striche erstellt und unter dem "bereits angeschossenen", roten Space Invader platziert. Um diese nach oben zu bewegen, habe ich den gleichen animateTransform tag, wie bereits oben, benutzt.