# boitapotard-midi
![Teensy LC](https://www.pjrc.com/store/teensylc.html) + 8 potards rotatifs linéaires 10kΩ + librairie [MIDIController](https://github.com/joshnishikawa/MIDIcontroller)

Utilise intensément la formidable librairie de Josh Nishikawa [MIDIController](https://github.com/joshnishikawa/MIDIcontroller) qui permet de gérer boutons, potards, encodeurs, pour créer des contrôleurs midi.   
Josh (qu'il en soit remercié) a mis à jour la lib. en version 2.5.3 pour "forcer" la lecture des contrôleurs une première fois.  
Dans le sketch Processing, au setup, une première lecture des potards permet de remplir la table de vérité (un array) avec les données réelles (positions initiales des potentiomètres)).

```
 teensy LC | --- | Control num
------------------------------------
     14/A0 | --- | 51  
     15/A1 | --- | 52
     16/A2 | --- | 53
     17/A3 | --- | 54
     18/A4 | --- | 55
     19/A5 | --- | 56
     20/A6 | --- | 57
     21/A7 | --- | 58
     
```
**Teensy LC :** 
- reconnu comme un périphérique MIDI (cf. `name.c` pour le nom du device)
- gestion midiUSB
- pas très cher (<20€)
- 13 entrées analogiques (ADC jusqu'à 12 bits, 10 bits par défaut)
- de la RAM
- une led intégrée sur la PIN 13
- un port microUSB (pour l'alim et la communication)

Dans Processing, j'utilise cette autre formidable bibliothèque [theMidiBus](https://github.com/sparks/themidibus) de Severin Smith, pour intercepter les messages midi et remplir un Array __Pots[]__

![boitapotard_int](https://user-images.githubusercontent.com/1716290/165055529-7a3cbd8e-8464-4f92-a8b9-d2e43c4be280.jpg)

![boitapotard_ext](https://user-images.githubusercontent.com/1716290/165055586-23fc91f3-c62f-4772-aa2d-b08b1714a504.jpg)
