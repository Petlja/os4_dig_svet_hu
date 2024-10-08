Ismétlődő programok
===================

Nézd meg a következő példát! Magyarázd el Karelnek, hogy mit kell tennie!

3. példa
--------

Öt labda van egy kupacban. Karelnek össze kell gyűjtenie mind az öt labdát, majd a (6, 1) mezőre kell lépnie. 
 
.. blockly-karel:: p532a
  :categories: KarelCommands
  :flyouttoolbox:
  
  {
      setup: function() {
           var world = new World(6, 2);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBalls(5, 1, 5);
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
  isSuccess: function(robot, world) {
        return robot.getAvenue() == 6 && 
		robot.getStreet() == 1 &&
        robot.getBalls() == 5;
		}
   }

**Segítség**: Karelnek négy lépést kell tennie, majd ötször fel kell vennie egy-egy labdát, és végül még egy lépést kell tennie, hogy elérje a megadott mezőt.

.. questionnote::

 Képzeld el, hogy 1000 labda van egy kupacban! Hány blokkra és mennyi időre lenne szükséged, hogy összeállítsd a programot?
 
Ebben az esetben sokkal célszerűbb **ciklust** alkalmazni a programban.

.. infonote::

 Ha egy utasítást (vagy utasítások csoportját) többször kell végrehajtani egy adott programban, akkor ehhez **ciklust** használunk.

Csináld meg újra az előző példát, de ezúttal ciklus alkalmazásával! Az utasítások áttekinthetősége érdekében csoportokra osztottuk őket. Kattints a ``Ciklusok`` csoportra!
Húzd az első blokkot a munkaterületre! Próbáld meg magad összeállítani a programot! Ha nem sikerül, nézd meg az általunk javasolt megoldást!

.. blockly-karel:: p532b
  :categories: KarelCommands, Loops
  
  {
      setup: function() {
           var world = new World(6, 2);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBalls(5, 1, 5);
           var robot = new Robot();
           return {world: world, robot: robot};
      },
	  
  isSuccess: function(robot, world) {
        return robot.getAvenue() == 6 && 
		robot.getStreet() == 1 &&
        robot.getBalls() == 5;
		}
   }
   
.. reveal::  3. példa
   :showtitle: Javasolt megoldás   
   :hidetitle: Bezár
	
   Javasolt megoldás
 
   .. image:: ../../_images/karel_p3.png
     :width: 780
     :align: center
	 
	 
Pakolsz be az iskolatáskádba... Mindent, amit be kell tenni a táskába, kiraksz az íróasztalra. Majd hozzáfogsz a pakoláshoz: füzet, radír, ceruza, füzet, könyv, színes ceruza, szótár...

.. questionnote::

 Észrevettél-e valami szabályszerűséget a fenti tevékenységekben? Ismétlődnek bizonyos lépések úgy, hogy akár ciklusba is lehetne őket helyezni?
 
Itt van egy másik helyzet: bepakolsz egy ceruzát, egy ceruzát, egy ceruzát. Aztán egy füzetet, egy füzetet, egy füzetet, egy füzetet, egy füzetet. Majd egy könyvet, egy könyvet, egy könyvet, egy könyvet.

.. questionnote::

 Észrevettél most valami szabályszerű ismétlődést? Mely lépéseket tennéd ciklusba, és hogyan?

 Érthetőbb és tömörebb lenne az az utasítás, hogy „Tégy a hátizsákba három ceruzát, öt füzetet, majd négy könyvet!”? 

4. példa
--------

Ezek a labdák szétszóródtak. Jól gondold át, milyen lépéseket kell Karelnek megtennie, és hányszor! Ha észreveszed, 
hogy bizonyos lépések ismétlődnek, tedd őket ciklusba!

.. blockly-karel:: p534
  :categories: KarelCommands, Loops
  
  {
      setup: function() {
           var world = new World(5, 2);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           world.putBalls(2, 1, 1);
		   world.putBalls(3, 1, 1);
           world.putBalls(4, 1, 1);
           world.putBalls(5, 1, 1);
           var robot = new Robot();
		  
		  return {world: world, robot: robot};
      },
	  
      isSuccess: function(robot, world) {
           return robot.getBalls()==4
      }
   }

5. példa
--------

Ahhoz, hogy sikeresen befejezze a feladatot, Karelnek össze kell gyűjtenie öt labdát, amelyek ezen a szokatlan úton találhatók. 
Használj ciklusokat a programban, és segíts neki!
 
.. blockly-karel:: p535
  :categories: KarelCommands, Loops
  
  {
      setup: function() {
           var world = new World(6, 6);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
		   world.putBalls(6, 6, 5)
		   for (var i = 1; i <= world.getAvenues()-1; i++)
		       world.addEWWall(i+1, i, 1)
		   for (var i = 1; i <= world.getAvenues()-1; i++)
		       world.addNSWall(i, i, 1)
		   for (var i = 1; i <= world.getAvenues()-1; i++)
		       world.addEWWall(i, i+1, 1)
		   for (var i = 1; i <= world.getAvenues()-2; i++)
		       world.addNSWall(i, i+2, 1)
 
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

**Segítség**: Írd le az összes utasítást, amit Karelnek kell végrehajtania, és figyeld meg, hogy melyek ismétlődnek! Hányszor ismétlődnek?

Ebben a megoldásban két különböző ciklust használhatsz - egyet a fal melletti mozgáshoz és egyet a labdák összegyűjtéséhez.

Emlékezz vissza arra is, hogy már említettük a **feltételes ciklusokat**! Mikor használod ezeket?

Térjünk vissza az iskolatáska bepakolásának példájára.

.. questionnote::

 Tegyük fel, hogy mindent be kell pakolnod, ami az asztalon van. Nem tudod előre, hogy pontosan hány dolog vár bepakolásra. Honnan fogod tudni, hogy meddig kell ezt csinálnod, hány alkalommal kell megismételned?

A választ talán megfogalmazhatjuk így is: „Amíg az asztalon vannak dolgok, addig folytasd a táskába való bepakolást!“ 

.. infonote::

 Amikor nem tudható előre, hány alkalommal kell megismételni egy utasítást (vagy utasításcsoportot), akkor a programban **feltételes ciklust** használunk.


6. példa
--------

A labdák egy kupacban vannak, amelyeket majd Karelnek a lyukba kell helyeznie. Karel ezúttal nem tudja előre, hány labdát kell összegyűjtenie.
Ugyanis minden egyes alkalommal, amikor elindítod a programot, más-más számú labda van egy kupacban.

Nézd meg Peti megoldását!  

.. questionnote::

 Alkalmazható-e az így megírt program a kupacban lévő golyók számától függetlenül?

.. blockly-karel:: p536
  :categories: KarelCommands, Loops, KarelBrain

  {
      setup: function() {
           function random(n) {
              return Math.floor(n * Math.random());
           }
           var world = new World(5, 2);
           world.setRobotStartAvenue(5);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("W");
		   var N = 1 + random(7);
           world.putBalls(3, 1, N);
		   world.putHoles(1, 1, N);
           var robot = new Robot();
		   var domXml = '<xml xmlns="https://developers.google.com/blockly/xml">\n  <block type="move" id="@9wN=9YZ]s=i|lCq7V3L" x="104" y="84">\n    <next>\n      <block type="move" id="wS!q2t:%e^7xoo)MM/0S">\n        <next>\n          <block type="controls_whileUntil" id="E`*mAAJ;e`]DxNfoj]Pt">\n            <value name="BOOL">\n              <block type="balls_present" id="wn];hrakB1k]KT#Rs9$_"></block>\n            </value>\n            <statement name="DO">\n              <block type="pick_up" id="h^Fxa]:$1FN`|M;?5FU,"></block>\n            </statement>\n            <next>\n              <block type="move" id=",.GsPM`ueNwG~wH+5ciU">\n                <next>\n                  <block type="move" id="v(6j`Qr{z!V(bNiWs8Yo">\n                    <next>\n                      <block type="controls_whileUntil" id="wVVW}b=aFWg!wv~7K*Vo">\n                        <value name="BOOL">\n                          <block type="has_balls" id="sf+VO=p6XSRn+8::?%lF"></block>\n                        </value>\n                        <statement name="DO">\n                          <block type="drop_off" id="oQ05`ukX}]DMUIy0oEdc"></block>\n                        </statement>\n                      </block>\n                    </next>\n                  </block>\n                </next>\n              </block>\n            </next>\n          </block>\n        </next>\n      </block>\n    </next>\n  </block>\n</xml>';
		   return {world: world, robot: robot, domXml: domXml};
      },
	  
      isSuccess: function(robot, world) {
           for (var i = 1; i <= world.getAvenues(); i++)
              for (var j = 1; j <= world.getStreets(); j++)
                 if (world.getBalls(i, j) != 0)
                    return false;
          return true;
      }
   }
