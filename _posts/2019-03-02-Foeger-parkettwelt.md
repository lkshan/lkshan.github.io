---
layout: post
title:  "Föeger parkettwelt"
subtitle: "Implementácia eshopu na platforme Magento 2"
date:   2017-06-30
background: '/img/posts/foeger.png'
specification: job
active: 1
---

Föeger Parkettwelt je rakúsky predajca luxusných bytových doplnkov a podláh. Na [stránke](https://boden.foeger.at/parkett) pána FöegeraFöeger si môžete kúpiť parkety z ebenového dreva aj za viac ako 100€/m<sup>2</sup>. Celý tento eshop je postavený na americkej platforme Magento 2. Jedná sa o najvyspelejší a najkomplexnejší framework na tvorbu eshopov. Z posledných správ bolo možné zachytiť, že v Decembri 2018 [spoločnosť Adobe odkúpila platformu Magento 2](https://techcrunch.com/2018/05/21/adobe-to-acquire-magento-for-1-6-b/) za viac ako 1.68 miliard amerických dolárov. 

<img class="img-fluid" src="{{ page.background | relative_url }}">

Ja som na tomto projekte participoval ako pomocný dizajnér. Šlo vlastne o môj prvý komerčný projekt na ktorom som sa podieľal. Mojou úlohol bola predovšetkým implementácia dizajnu pre detailnu stránku produktu a kategorický prehľad preduktov. Na prvý pohľad sa môže zdať, že ide o úplné triviálnosti ale verte mi, v Magento 2 je všetko *92348x* náročnejšie ako sa v skutočnosti zdá. Detailná stránka pozostávala z rôznych modulov a moduly komunikovali s backendom pomocou rôznych rozhraní. Nebolo jednoduché zabezpečiť konzistentnosť údajov medzi backendom a frontendom. Pochopenie Magenta mi chvíľu zabralo. Predovšetkým preto, že jeho jedno fungovalo na php [frameworku Zend] (https://framework.zend.com/), ktorý bol pre mňa úplne nový. Detailná stránka tiež obsahovala modul prerátavajúci cenu na základe zakúpeného množstva, akutálnej zľavy na produkt, veľkosti balíka v ktorej sa tovar nachádzal a podobných drobných sumičiek. Nižšie môžete vidieť finálny produkt mojej práce.

<img class="img-fluid" src="{{ "/img/posts/foeger_detail.png" | relative_url }}">

## Odmena

Ako som už uviedol v predchádzajúcich postoch, spoločnosť v ktorej pracujem sa vie vhodne odvďačiť za dobre odvedenú prácu. Za tento projekt sme spolu s kolegovcami mali súkromný večierok v jednom bratislavskom podniku [Craft BEER](https://b33r.sk/). Podnik odporúčam iba ak si chcete dať unikátne pivo, pretože ich jedlo za veľa nestálo. Na tom sme sa zhodli 8 ľudia.

<img class="img-fluid" src="{{ "/img/posts/foeger_after.jpg" | relative_url}}">
<span class="caption text-muted">After party na počesť ukončenia projektu Föeger parkettwelt</span>
