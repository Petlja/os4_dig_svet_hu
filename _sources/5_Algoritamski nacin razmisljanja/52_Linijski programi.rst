Lineáris programok
==================

Tavaly különböző **programozási struktúrákról** beszéltünk. Beszéltünk arról, hogy mikor használunk ciklusokat a programban, 
milyen esetben mondjuk egy programról, hogy **elágazik**, és hogy miként lehet elvégezni a matematikai műveleteket.

Emlékezz vissza, hogy hogyan kell összeállítani egy programot a Karel környezetben! Kezdjük egy egyszerű példával:


1. példa
--------

Segíts Karelnek megszerezni a labdát!

.. blockly-karel:: p521 
  :flyouttoolbox:
  :categories: BeginnerKarelCommands

   {
        setup:function() {
            var world = new World(5,5);
            world.setRobotStartAvenue(2);
            world.setRobotStartStreet(1);
            world.setRobotStartDirection("E");
            world.putBall(4, 2);
            world.addEWWall(1, 1, 2);
            world.addEWWall(2, 3, 3);
            world.addNSWall(3, 1, 1);
            world.addNSWall(3, 4, 1);
            world.addNSWall(1, 5, 1);
            var robot = new Robot();
			
			return {robot:robot, world:world};
        },

        isSuccess: function(robot, world) {
           return robot.getAvenue() == 4 &&
		   robot.getStreet() == 2 &&
           robot.getBalls() == 1;
        }
   }
   
Tartalmazza-e a megoldásod a következő lépéseket:
 - lépés előre,
 - fordulj balra,
 - lépés előre,
 - fordulj jobbra,
 - lépés előre,
 - vedd fel?

Ha ebben a sorrendben állítottad be a lépéseket, Karel eljut arra a mezőre, ahol a labda van, és felveszi azt. A feladatot sikeresen teljesíti!


.. questionnote::

 Замени место неким корацима, „измешај их“! Шта се десило? Да ли је Карел и овог пута успешно узео лоптицу?

.. infonote::

 Није свеједно којим редом наводиш кораке. Присети се да је **алгоритам** низ корака које је потребно направити **тачно одређеним редоследом** како би се решио неки проблем.

Имајући ово у виду, уради следећи пример:

Пример 2
--------

Марко је хтео да помогне Карелу, превукао је неколико блокова, али је морао да крене на тренинг! 
Сложи припремљене блокове и провери да ли ће Карел успети да дође до лопте и узме је. 
Ако је потребно, избриши блок који је вишак или додај неки ако недостаје!

.. blockly-karel:: p522
  :flyouttoolbox:
  :categories: BeginnerKarelCommands

   {
        setup:function() {
            var world = new World(5,5);
            world.setRobotStartAvenue(1);
            world.setRobotStartStreet(1);
            world.setRobotStartDirection("E");
            world.putBall(1, 3);
            world.addEWWall(1, 1, 2);
            world.addEWWall(2, 3, 3);
            world.addNSWall(3, 1, 2);
            world.addNSWall(3, 4, 1);
            world.addNSWall(1, 5, 1);
            var robot = new Robot();
            var domXml = '<xml xmlns="https://developers.google.com/blockly/xml">\n  <block type="move" id="v((;N^?~/DPk?PtcD!rH" x="49" y="70"></block>\n  <block type="move" id="^c,s6?}@%hfN~%l{L^4]" x="288" y="62"></block>\n  <block type="turn_left" id="8ot[uBd,stAEC4|/E7}o" x="188" y="147"></block>\n  <block type="pick_up" id="u;=%D4uiqat3FDWes#=P" x="42" y="189"></block>\n  <block type="turn_right" id="3QvO+QuL$beiAIhQN/Qg" x="322" y="228"></block>\n  <block type="move" id="8jzM+{4K7b6%3,D_tpyl" x="147" y="240"></block>\n  <block type="turn_left" id="s3fOMprumtO,.x/?fyNO" x="34" y="311"></block>\n  <block type="move" id="[;1x]bR043wC(UJQ:[$6" x="321" y="313"></block>\n  <block type="move" id=":.jI_,|BH6syiWlrrUNe" x="162" y="367"></block>\n  <block type="move" id="=fvSp9pM2-te1KdOu3Rd" x="102" y="442"></block>\n</xml>';
            return {robot:robot, world:world, domXml:domXml};
        },

        isSuccess: function(robot, world) {
           return robot.getAvenue() == 1 &&
		   robot.getStreet() == 3 &&
           robot.getBalls() == 1;
        }
   }

.. questionnote::

 Да ли у претходним примерима постоје неке наредбе или групе наредби које се понављају више пута?
 
 

