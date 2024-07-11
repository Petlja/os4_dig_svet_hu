Változó értékek
===============

Az előző példában a microbit különböző parancsokat hajtott végre egy matematikai kifejezés alapján, amely mindig ugyanazt adja eredményül. 
Ebben az esetben a program minden egyes futtatásakor a microbit a „Helytelen“ szót fogja kiírni.

Azonban legtöbb esetben a programban feltételként szereplő kifejezések változó értékekűek lehetnek. 
Egy egyszerű példa: a felhasználó beír egy számot, és ha az osztható kettővel, a program a „Páros“ szót írja ki, ellenkező esetben „Páratlan“ szót.

**A felhasználó által beírt értékek változók, ezért a microbit által kiírt értékek is ennek megfelelően változnak.**

.. questionnote::

 Említettük, hogy a microbit képes megmérni a hőmérsékletet. Vajon a hőmérséklet mindig ugyanaz, vagy változik?
 
Ebben a programozói környezetben a Bemenet csoportban egy „hőmérséklet (°C)“ blokk is található, amelyet felhasználhatsz a programodban is egy konkrét szám helyett. 
Ebben a blokkban a pillanatnyi hőmérséklet tárolódik, ami a program futása során különböző értékeket vehet fel.

Nézzük meg, hogyan használhatod ezt a blokkot...


8. példa
~~~~~~~~

Készíts egy programot, amely a microbit környezetének hőmérsékletétől függően a képernyőn „meleg” vagy „hideg” szót jelenít meg.

Rendezd el a blokkokat az alábbi képen látható módon:

.. image:: ../../_images/mb18.png
	:width: 800
	:align: center
	
A microbit csak egyszer mérte meg a hőmérsékletet, és kiírta, hogy „meleg” (a szimulátoron a hőmérőt 36 fokra állítottuk).
És ennyi... De mi van, ha időközben megváltozik a hőmérséklet? Hol hibáztunk?

Logikus, hogy a microbitnek folyamatosan kellene, hogy mérje a hőmérsékletet és ellenőrizze, hogy meleg vagy hideg van-e.

Milyen blokkot kellene alkalmaznunk a ``indításkor`` blokk helyett?

Nézd meg, hogyan néz ki az a program, amely megoldja ezt a problémát:

.. image:: ../../_images/mb19.png
	:width: 800
	:align: center

.. questionnote::

 Nyisd meg a *Bemenet* csoportot, és nézd meg, milyen egyéb blokkok vannak, amelyek változó értékkel rendelkeznek.
 Hogyan használnád ezeket valamelyik programodban? 

A meglévő blokkokon kívül, amelyek változó értékeket használnak (hőmérséklet, fényerősség stb.), saját blokkokat is készíthetsz. 
Kitalálhatsz egy nevet a változó értékhez, és használhatod ezt a blokkot a programodban.


9. példa
~~~~~~~~

Пред тобом је мало другачији задатак од досадашњих. На екрану треба да буде приказан број. Сваки пут када притиснеш 
тастер **А** број треба да се увећа за 2. Када се покрене програм, број треба да буде нула.

Прочитај још једном задатак. Шта, у ствари, треба да урадиш? **Број** треба да буде приказан када се притисне тастер. 
Да ли је број увек исти? Није. **Број** се сваки пут мења, променљив је.

Хајде да онда направимо променљиву Број и да сваки пут када се притисне тастер променимо њену вредност и прикажемо је.

.. questionnote::

 По тексту задатка, колика треба да буде почетна вредност променљиве **Број**? За колико треба сваки пут да је променимо?

Како правиш блок за променљиву вредност?

Кликни на групу Променљиве (1), а затим на Направи променљиву (2). Упиши име променљиве у прозору који се појави. 
Нека се зове **Број**.

.. image:: ../../_images/mb20.png
	:width: 800
	:align: center	
	
Погледај слику испод. Међу променљивама се појавила и твоја. Сада можеш у њу да смешташ различите вредности – 
да јој додајеш бројеве, множиш је неким бројем, поредиш… користиш је као блок са било којим другим бројем.

.. image:: ../../_images/mb21.png
	:width: 800
	:align: center	

.. questionnote::

 Из математике сте радили задатке са променљивим вредностима. Којим словима их обично обележавате?
 На које све начине можемо да поредимо променљиве? 

Вратимо се на наш програм. Постави блокове као на слици испод:

.. image:: ../../_images/mb22.png
	:width: 800
	:align: center	
	
Дакле, на почетку извршавања програма број је постављен на нулу. Сваки пут кад се притисне тастер А Број се увећа 
за два и прикаже.

Измени или допуни програм тако да буде приказана и нула на почетку!

Пример 10
~~~~~~~~~

У претходном примеру приметио си и један нови блок из групе Улаз. Он омогућава да се неке наредбе изврше када се 
притисне тастер **А**. На исти начин можеш да програмираш шта треба да се деси када неко притисне тастер **Б** или оба 
тастера истовремено **(А + Б)**.

Микробит може да реагује и на још неке догађаје – када се протресе, када се закрене на неку страну, када удари о 
нешто и слично. Погледај који све блокови постоје у групи Улаз. За овај интересантан пример користићемо блок ``када се протресе``.

.. image:: ../../_images/mb23.png
	:width: 800
	:align: center	

Један од блокова који такође може да има променљиву вредност (``одабери случајну вредност од _ до``) налази се у групи Математика. 
Употребили смо га на следећи начин:

.. image:: ../../_images/mb24.png
	:width: 800
	:align: center

.. questionnote::

 Шта ради овај програм? За шта би могао да употребиш микробит у који је учитан овај програм?
