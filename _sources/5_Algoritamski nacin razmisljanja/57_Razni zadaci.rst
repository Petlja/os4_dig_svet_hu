Feladatok
=========

Most már elegendő tapasztalattal rendelkezel az önálló feladatok megoldásához. Lehetőség szerint többféleképpen oldj meg egy-egy feladatot!

Annak érdekében, hogy egy kicsit megkönnyítsük a munkád, két új blokkcsoportot adtunk az eszköztárhoz: ``Karel elágazás`` és ``Karel ciklus`` néven.
Az ezekben a csoportokban található blokkok a ``Ciklusok``, az ``Elágazások`` és a ``Kérdezd a robotot`` csoport blokkjainak kombinációját képviselik.
Nyugodtan fedezd fel és használd azokat a blokkokat, amelyek neked a legjobban megfelelnek!

.. suggestionnote::

 **Ha lehetséges és van értelme, akkor mindenképp használd a megfelelő ciklusokat a megoldásban!** 

|

1. feladat
----------

**Karel egy szűk járatban találta magát. Segíts neki megszerezni mindkét labdát!**

.. blockly-karel:: p561
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
		   world.addNSWall(2, 1, 5)
		   world.addNSWall(3, 1, 5)
           world.setRobotStartAvenue(3);
           world.setRobotStartStreet(2);
           world.setRobotStartDirection("W");
           world.putBall(3, 5);
		   world.putBall(3, 1);
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
          for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }


2. feladat
----------

**Karelnek be kell dobnia a labdát a lyukba!**

.. blockly-karel:: p562
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBall(4, 3);
		   world.putHole(5, 5);
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
        for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }

3. feladat
----------
  
**Karelnek két labdát kell gyűjtenie. Jó felé fordult? Válassz rövidebb utat!**

.. blockly-karel:: p563
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
		   world.addEWWall(2, 1, 3)
		   world.addNSWall(4, 2, 3)
		   world.addEWWall(2, 4, 3)
		   world.addNSWall(1, 2, 3)
           world.setRobotStartAvenue(3);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("W");
           world.putBall(5, 1);
		   world.putBall(5, 5);
           var robot = new Robot();
           
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
           return robot.getBalls() == 2;
      }
   }
      

4. feladat
----------

**Segíts Karelnek összeszedni az összes labdát a kupacból, majd visszatérni az (1, 1) mezőre!**

|
   
.. blockly-karel:: p564
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBalls(3, 1, 6);
		   world.addEWWall(1, 1, 5)
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
        return robot.getAvenue() == 1 && 
		robot.getStreet() == 1 &&
        robot.getBalls() == 6;
		}
   }
   

5. feladat
----------
  
**Segíts Karelnek összeszedni az összes labdát, majd visszatérni az (1, 1) mezőre!**

|
   
.. blockly-karel:: p565
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("N");
           world.putBalls(2, 1, 3);
		   world.putBalls(1, 2, 3);
		   world.putBalls(2, 2, 3);
           var robot = new Robot();
		   
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
	   return robot.getAvenue() == 1 && 
		robot.getStreet() == 1 &&
        robot.getBalls() == 9;
		}
           
   }
   
**Segítség**: Keresd meg a program ismétlődő részeit!

6. feladat
----------
  
**A feladat hasonló az előzőhöz. Karelnek össze kell szednie a labdákat, és be kell dobnia az (1, 1) mezőn található lyukba **.
Ha a programban ismétlődő részekkel találkozol, használj ciklust!**

|
   
.. blockly-karel:: p566
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("N");
           world.putBall(2, 2);
		   world.putBall(2, 1);
		   world.putBall(1, 2);
		   world.putHoles(1, 1, 3);
           var robot = new Robot();

           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
          for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }

7. feladat
----------
 
**Karelnek össze kell gyűjtenie mind a 12 labdát.**

|

.. blockly-karel:: p567
  :categories: KarelCommands, Loops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("N");
		   world.putBalls(2, 2, 3);
		   world.putBalls(3, 2, 4);
		   world.putBalls(4, 2, 2);
		   world.putBalls(5, 2, 3);
           var robot = new Robot();
 
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
          for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }

**Segítség**: Rövidítsd le a programot azzal, hogy ciklust használsz.
A kupacokban különböző számú labda található. Melyik a jobb megoldás, a számláló vagy a feltételes ciklus használata?

Karel először lépjen előre, majd forduljon jobbra. A következő lépéseket többször meg kell ismételni: amíg vannak labdák a mezőn, vegye fel őket, majd lépjen előre a következő mezőre. Majd ismét… amíg vannak labdák a mezőn, vegye fel őket, majd lépjen a következő mezőre… majd ismét… meddig, hányszor? Ismerd fel, hely mely műveletek csoportja ismétlődik meg többször is. Ha felismered, melyek ezek, tedd őket a megfelelő ciklusba.

|

8. feladat
---------- 
 
**Karel egy cikcakkos falba ütközött. Minden sarokban van egy labda. Segíts neki összeszedni őket!**

| 

.. blockly-karel:: p568
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(6, 6);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
		   for (var i = 1; i <= world.getAvenues()-1; i++)
		       world.addEWWall(i+1, i, 1)
		   for (var i = 1; i <= world.getAvenues()-1; i++){
		       world.addNSWall(i, i, 1)
		       world.putBall(i+1, i+1)
		  }
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
          for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }

**Segítség**: Az előző példákhoz hasonlóan, keresd meg, hogy mely utasítások ismétlődnek, és helyezd őket egy ciklusba.

|

9. feladat
---------

**Karel jelenleg a lyuknál van, ahova három labdát kell bedobnia. Segíts neki ezt megcsinálni!**
 
Azért, hogy gyakorold a számláló ciklusok, a feltételes ciklusok és az elágazások alkalmazását a programban, 
próbáld meg ezt a feladatot több különböző módon megoldani!

|

.. blockly-karel:: p569
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(5, 5);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBall(5, 1);
		   world.putBall(5, 5);
		   world.putBall(1, 5);
		   world.putHoles(1, 1, 3);
           var robot = new Robot();
           
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
          for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }

|

10. feladat
-----------

**Ez a labda jól elbújt! Segíts Karelnek megkeresni és elhozni!**
 
.. blockly-karel:: p5610
  :categories: KarelCommands, Loops, KarelLoops, Branching
  
  {
      setup: function() {
           var world = new World(6, 6);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBall(1, 2);
		   world.addEWWall(1, 1, 5)
		   world.addEWWall(2, 5, 4)
		   world.addNSWall(1, 2, 4)
		   world.addNSWall(5, 2, 4)
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
	      for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }           
   }
   
**Segítség**: Karelnek addig kell haladnia előre, amíg falnak nem ütközik (amíg előre tud haladni). 
Amikor eléri a falat, balra kell fordulnia. Hányszor kell megismételnie ezt a folyamatot? 
Amikor eléri az utolsó mezőt, fel kell vennie a labdát, és ezzel a feladat megoldódott!


