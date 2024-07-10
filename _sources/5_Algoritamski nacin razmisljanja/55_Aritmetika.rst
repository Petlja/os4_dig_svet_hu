Aritmetikai műveletek
=====================

A programokban az elágazás feltételei gyakorta valamilyen matematikai kifejezések. Emlékezz vissza, hogy miként lehet matematikai kifejezéseket létrehozni Karel világában. Ezúttal egy kicsit bonyolultabb példák várnak rád. Alaposan gondold át, hogy milyen sorrendben kell végrehajtani a műveleteket. Próbáld logikusan elhelyezni a megfelelő blokkokat...

9. példa
--------

Megfelelő módon állítsd össze az utasítás blokkokat a következő feladat megoldásához: a 138 és a 23 különbségéből vond ki a 6 és a 4 szorzatát.

.. blockly-karel:: p551  
  :categories: KarelSays, Arithmetic, Logic

  {
            setup:function() {
                var world = new World(3,3);
                world.setRobotStartAvenue(2);
                world.setRobotStartStreet(2);
                world.setRobotStartDirection("S");;
                var robot = new Robot();
                return {robot:robot, world:world};
            },
			
            isSuccess: function(robot, world) {
              return robot.getLastMessage() == 91
            },
  }
  
**Sgítség**:

E feladat a matematikai kifejezése a következő:

(138 - 23) - (6 * 4)

Milyen sorrendben helyezed el a blokkokat? Hány blokkra van szükséged az aritmetikai műveletekhez?

Szükséged lesz egy blokkra a 138 és a 23 különbségéhez. Egy másik blokkra, hogy megszorozd a 6-ot és a 4-et. A harmadik blokkra pedig, hogy kivond egymásból ezt a két eredményt.


10. példa
---------

Juli és Márk minden nap ellenőrzik, hogy hány lépést tettek meg. Juli 5286 lépést tett meg, míg Márk 800 lépéssel többet tett meg, mint Juli. 
A blokkok segítégével állítsd össze azt a kifejezést, amely kiszámítja, hogy hány lépést tett meg Juli és Márk összesen.

.. blockly-karel:: p552  
  :categories: KarelSays, Arithmetic, Logic

  {
            setup:function() {
                var world = new World(3,3);
                world.setRobotStartAvenue(2);
                world.setRobotStartStreet(2);
                world.setRobotStartDirection("S");;
                var robot = new Robot();
                return {robot:robot, world:world};
            },
			
            isSuccess: function(robot, world) {
              return robot.getLastMessage() == 11372
            },
  }
  
Milyen eredményt kaptál, amikor te számoltál? Egyezik azzal, amit Karel számolt ki? 
Ha nem, ellenőrizd még egyszer, hogy helyesen rendezted-e el a blokkokat!

.. infonote::

 Megtanultad, hogyan lehet a Wordben képeket és szövegrészleteket másolni. Próbáld meg ebben a környezetben is használni a **Ctrl + C** és a **Ctrl + V** a billentyűparancsokat, amikor egy blokkra többször is szükséged van. 

