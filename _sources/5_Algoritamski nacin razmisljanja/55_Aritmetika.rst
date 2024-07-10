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

Јована и Никола сваког дана проверавају колико су направили корака. Јована је направила 5286 корака, а Марко 800 корака 
више од Јоване. Састави израз којим се рачуна колико су корака заједно прешли Јована и Марко.

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
  
Који си резултат ти добио када си рачунао? Да ли се слаже са оним што је израчунао Карел? Ако ниси, још једном провери
да ли си добро поређао блокове!

.. infonote::

 Научио си како се у Ворду копирају слике и делови текста. Покушај и у овом окружењу да користиш пречице на тастатури **Ctrl + C** и **Ctrl + V** када ти је неки блок потребан више пута. 
