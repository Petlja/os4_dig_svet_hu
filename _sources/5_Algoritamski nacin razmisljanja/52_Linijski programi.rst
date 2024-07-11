Lineáris programok
==================

Tavaly különböző **programozási struktúrákról** beszéltünk. Beszéltünk arról, hogy mikor használunk ciklusokat a programban, 
milyen esetben mondjuk egy programról, hogy **elágazik**, és hogy miként lehet elvégezni a matematikai műveleteket.

Emlékezz vissza, hogyan kell összeállítani egy programot Karel környezetében! Kezdjük egy egyszerű példával:


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
 - vedd fel!?

Ha ebben a sorrendben állítottad be a lépéseket, Karel eljut arra a mezőre, ahol a labda van, és felveszi azt. A feladatot sikeresen teljesíti.


.. questionnote::

 Cseréld fel néhány lépés helyét, keverd össze őket! Mi történik? Sikerült Karelnak most is felvenni a labdát?

.. infonote::

 Nem mindegy, milyen sorrendben adod meg a lépéseket. Jusson eszedbe, hogy az **algoritmus** olyan lépések sorozata, amelyeket **pontosan meghatározott sorrendben** kell végrehajtani egy probléma megoldásához.

Mindezt szem előtt tartva oldd meg a következő példafeladatot:

2. példa
--------

Márk segíteni akart Karelnak, ezért áthúzott néhány blokkot a programhoz, de utána edzésre kellett mennie. 
Rendezd sorba az előkészített blokkokat, és ellenőrizd, hogy Karel eljut-e a labdához, és felveszi-e azt! 
Ha szükséges, töröld a felesleges blokkot, vagy adj hozzá egyet, ha hiányzik!

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

 Vannak olyan utasítások vagy utasításcsoportok az előző példákban, amelyek többször is megismétlődnek?
 
 

