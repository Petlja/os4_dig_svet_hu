Програми са гранањем
====================

Хајде да се вратимо на наш пример паковања ранца. Да ли сваког дана носиш све књиге? А темпере? Од чега то зависи?
Рецимо да ликовно имаш петком. **Ако** је петак - спаковаћеш темпере. Да ли ћеш их носити у школу ако није петак? 
Или, слично - **ако** имаш математику, спаковаћеш две свеске, радне листове, књигу... да ли ти је потребна књига из математике **ако** немаш тај час петком?

Присети се:

.. infonote::

 Када се у програму проверава неки услов и раде различите ствари у зависности од тога да ли је он испуњен или не, говоримо о **гранању**.

Пример 8
---------

Марко је смислио једну игру која ће ти помоћи да поновиш математику. Карел ће да направи корак напред само ако је тачан услов који је постављен.
Замени знакове **=** у програму који је саставио Марко тако да Карел сваки пут направи предвиђени број корака и да стигне до поља (5, 1)

.. blockly-karel:: p542
  :categories: 
  :exportmode:
  
  {
      setup: function() {
           
           var world = new World(5, 2);
           world.setRobotStartAvenue(1);
           world.setRobotStartStreet(1);
           world.setRobotStartDirection("E");
           var robot = new Robot();
		   var domXml = '<xml xmlns="https://developers.google.com/blockly/xml">\n  <block type="controls_if" id="dr|2OCEqioQ0Q/qHg{qQ" x="84" y="75">\n    <value name="IF0">\n      <block type="logic_compare" id="dp=1x)eiJeYtsa4H{1e:">\n        <field name="OP">EQ</field>\n        <value name="A">\n          <block type="math_arithmetic" id="KX-lywbTIEFs0tnz:j@_">\n            <field name="OP">ADD</field>\n            <value name="A">\n              <block type="math_number" id="iLxPi:8}Z5Zk^gcLUxOK">\n                <field name="NUM">125</field>\n              </block>\n            </value>\n            <value name="B">\n              <block type="math_number" id="I(GZ$!X|;aSk.j[nDT((">\n                <field name="NUM">5</field>\n              </block>\n            </value>\n          </block>\n        </value>\n        <value name="B">\n          <block type="math_number" id="|zM6^j-wln$P1+ow@5g!">\n            <field name="NUM">138</field>\n          </block>\n        </value>\n      </block>\n    </value>\n    <statement name="DO0">\n      <block type="move" id="Z]3{9c5.@j7ZqA)}~v:["></block>\n    </statement>\n    <next>\n      <block type="controls_if" id="!b{A_)`)%xqp)gwW]V{{">\n        <value name="IF0">\n          <block type="logic_compare" id="e;8yeGz|MU2;3NTB9p+!">\n            <field name="OP">EQ</field>\n            <value name="A">\n              <block type="math_number" id="DfX1eUAO~V/l*FU(uF6D">\n                <field name="NUM">34</field>\n              </block>\n            </value>\n            <value name="B">\n              <block type="math_arithmetic" id="3XULAGQTsS*=v#Ibt;hN">\n                <field name="OP">MINUS</field>\n                <value name="A">\n                  <block type="math_number" id="#^SeY](kczJ,x2KQZB_R">\n                    <field name="NUM">67</field>\n                  </block>\n                </value>\n                <value name="B">\n                  <block type="math_number" id="FBwc`?PYOB!1RH`(k)uo">\n                    <field name="NUM">12</field>\n                  </block>\n                </value>\n              </block>\n            </value>\n          </block>\n        </value>\n        <statement name="DO0">\n          <block type="move" id="iR?yvuOon(}id_THS.k?">\n            <next>\n              <block type="move" id="2Q?u:ornbN?-W~($yJ*a"></block>\n            </next>\n          </block>\n        </statement>\n        <next>\n          <block type="controls_if" id="3b`(BxZ6cmcc{-|H{G,V">\n            <value name="IF0">\n              <block type="logic_compare" id="yx?r-QG~_8I8x/jt)`_x">\n                <field name="OP">EQ</field>\n                <value name="A">\n                  <block type="math_arithmetic" id="tMLG~wk03Z1Fj]0v0Cm=">\n                    <field name="OP">ADD</field>\n                    <value name="A">\n                      <block type="math_number" id="3RY(lU9,nKKR,!sC)ePk">\n                        <field name="NUM">214</field>\n                      </block>\n                    </value>\n                    <value name="B">\n                      <block type="math_number" id="gB)mb9w}=3SdjI?+ou,|">\n                        <field name="NUM">354</field>\n                      </block>\n                    </value>\n                  </block>\n                </value>\n                <value name="B">\n                  <block type="math_number" id="1z=M1Io|r-9:l{OEes6+">\n                    <field name="NUM">567</field>\n                  </block>\n                </value>\n              </block>\n            </value>\n            <statement name="DO0">\n              <block type="move" id="TH;C{g#Qk3|*8lnL{!qR"></block>\n            </statement>\n          </block>\n        </next>\n      </block>\n    </next>\n  </block>\n</xml>';
		   return {world: world, robot: robot, domXml: domXml};
      },
	  
  isSuccess: function(robot, world) {
        return robot.getAvenue() == 5 && 
		robot.getStreet() == 1 
		}
   }