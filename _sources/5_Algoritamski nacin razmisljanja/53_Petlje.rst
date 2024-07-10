Ismétlődő programok
===================

Nézd meg a következő példát. Magyarázd el Karelnek, hogy mit kell tennie.

3. példa
--------

Öt labda van egy kupacban. Karelnek össze kell gyűjtenie mind az öt labdát majd a (6, 1) mezőre kell lépnie. 
 
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

Csináld meg újra az előző példát, de ezúttal ciklus alkalmazásával. Az utasítások áttekinthetősége érdekében csoportokra osztottuk őket. Kattints a ``Ciklusok`` csoportra.
Húzd az első blokkot a munkaterületre. Próbáld meg magad összeállítani a programot. Ha nem sikerül, nézd meg az általunk javasolt megoldást.

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
	 
	 
Пакујеш ранац за школу... све што треба да ставиш у ранац поређао си на радни сто. И почињеш паковање: свеска, гумица, оловка,
свеска, књига, бојица, речник...

.. questionnote::

 Да ли си уочио неку правилност? Да ли се неки кораци понављају тако да можеш да их ставиш у петљу?
 
Ево и друге ситуације: пакујеш оловку, оловку, оловку. Затим свеску, свеску, свеску, свеску, свеску. Па стављаш књигу, књигу, књигу, књигу.

.. questionnote::

 Да ли си овог пута уочио неку правилност? Које би кораке ставио у петљу и на који начин?

 Да ли је упутство „Стави у ранац три оловке, пет свески, па четири књиге“ разумљивије, сажетије?


Пример 4
--------

Ове лоптице су се баш расуле! Добро размотри које кораке Карел треба да направи и колико пута. Ако уочиш да се неки 
кораци понављају, стави их у петљу! 

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

Пример 5
--------

Да би успешно завршио задатак, Карел треба да сакупи пет лоптица које се налазе на крају овог необичног пута. 
Примени петље у програму и помози му! 
 
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

**Помоћ**: Испиши сваку наредбу коју треба да изврши и уочи које се од њих понављају. Колико пута? 
У овом решењу можеш да употребиш две различите петље – за кретање уз зид и за сакупљање лоптица. 

Присети се да смо причали и о **условним петљама**. Када њих користиш? 

Вратимо се на пример паковања ранца. 

.. questionnote::

 Рецимо да треба да спакујеш „све што је на столу“. Не знаш унапред колико чега има. Како ћеш знати до када то треба да радиш, колико пута? 

Можда да кажемо овако: „Све док на столу има предмета, спакуј их у ранац.“

.. infonote::

 Када није унапред познато колико пута наредба (или група наредби) треба да се понови, у програму се користе **условне петље**.

Пример 6
--------

На гомили се налазe лоптицe које Карел треба да убаци у рупу. Карел овог пута **не зна унапред** колико лоптица треба да сакупи.
Сваки пут кад покренеш програм на гомили ће се појавити другачији број лоптица.

Погледај решење које је смислио Пера. 

.. questionnote::

 Да ли ће овако написан програм моћи да се примени без обзира на број лоптица на гомили?

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
