---
layout: post
title:  "Raiffeisen Centro Bank Austria"
subtitle: "Implementácia rozhrania pre nákup investičných aktív"
date:   2017-11-08
background: '/img/posts/RCB.png'
specification: job
active: 1
---

Môj prvý projekt pri ktorom som sa prvý krát stretol s **Yii 2** a **Typo 3**. Na tomto projekte som začal pracovať hneď keď som dokončil projekt [Föeger parkettwelt]({% post_url 2019-03-02-Foeger-parkettwelt %}). V projekte RCB šlo predovšetkým o vylepšenie a zmodernizovanie starej stránky. Toto zahrňalo upgrade verzie **Typo3** a nový dizajn. Systém zobrazoval živé dáta zo svetových búrz ktoré pôsobili ako prostredník medzi investormi a brokermi (sprostredkovatelia nákupu a predaja investičných aktív). 

<img class="img-fluid" src="{{ page.background | relative_url }}">

Na rozdiel od svojích doterajších úloh s dizajnom som na tomto projekte pracoval ako skutočný programátor. Vytváral som rôzne tabuľkové modulý ktoré obsahovali základné informácie o aktívach, vývoj cien akcií, trend ekonomiky a podobne. Najväčšou výzvou pre mňa bola implementácia tzv. weather máp. Tieto mapy zobrazujú stav ekonomík rôznych štátov podľa aktuálneho trendu (rastúci, stagnujúci, klesajúci). Možno sa to zdá ako triviálnosť ale v komerčnom prostredí tomu tak nie je. Ako prvé je nevyhnutné nájsť existujúcu knižnicu na ktorú sa vzťahujú také licenčné podmienky ktoré sú priaznivé pre obé strany. Inými slovami, takú knižnicu ktorá nie je prehnane predražená a jednoducho implementovateľná. Ja som si vybral knižnicu [Ammaps](https://www.amcharts.com/visited_countries/). Ďalej som už podračoval štandardným spôsobom.

<img class="img-fluid" src="{{ "/img/posts/RCB_after.png" | relative_url }}">

Výsledok projektu bol neopísateľný. Prehľadná stránka, ktorá zachytáva všetky potrebné informácie. Nádherne vizualizované dáta pomocou grafov a máp. Z pohľadu mňa ako programátora som sa toho veľmi veľa naučil. Okrem zlepšených programátorských schopností som konečne pochopil aj tomu, čo tie čísla a skratky v tých tabuľkách znamenajú :D

## Odmena

Po nasadení nového systému na *LIVE* server sme dostali pozvanie od spoločnosti *Raiffeisen Bank* na spoločné posedenie vo Viedni. Toto posedenie bol prejav vďaky za dobre odvedenú prácu. A úprimne si neviem predstaviť lepší prejav vďaky ako večera v centre Viedne, so skvelým jedlom, výborným vínom a nadherným počasím.

<img class="img-fluid" src="{{ "/img/posts/RCB_party1.jpg" | relative_url }}">
<span class="caption text-muted">Cheers!! Don't worry, it's just water.</span>

<img class="img-fluid" src="{{ "/img/posts/RCB_party2.jpg" | relative_url }}">
<span class="caption text-muted">Och a to jedlooooo....</span>