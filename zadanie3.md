---
layout: page
title: Zadanie 3
description: Dokumentácia 3. zadania z WPUB
background: '/img/bg-dokumentacia.jpg'
---
## Zadanie 3

Zadanie 3 som vypracovával s použitím technológie `XML`. Štruktúru stromu zaspísaného v jazuku `XML` (viď súbor `prezentacia.xml`) som opísal, resp. obmedzil na vybrané množstvo elementov a ich vnorených potomkov a atribútov pomocou technológie `Relax NG` (viď súbor `prezentacia.rng`). Stromová štruktúra prezentácie začína značkou `<prezentacia>`. Prezentácia môže obsahovať žiaden alebo mnoho slidov (označené značkou `<slide>`). Každý slide prezentácie má atribút `typ` opisujúci typ daného slidu. Deklarované typy slajdu sú:

- `uvodny` - úvodný slide obsahujúci len nadpis a podnadpis (úvod do prezentácie)
	- text zarovnaný na stred
- `obrazok-vpravo` - slide tohoto typu zobrazuje definovaný obrázok na 40% šírky, na pravej strane
	- zvyšný text je zarovnaný na ľavú stranu
	- slide obsahuje tiež atribút `zdroj`, ktorý definuje cestu k obrázku ktorý bude zobrazený v danom slide
- `obrazok-vlavo` - slide tohoto typu zobrazuje definovaný obrázok na 40% šírky, na ľave strane
	- zvyšný text je zarovnaný na ľavú stranu
	- aby obrázok neprekrýval text, tak je použitý element typu `stlpec`, ktorému je nastavená šírka tak, aby odsadila text v danom slide
	- slide obsahuje tiež atribút `zdroj`, ktorý definuje cestu k obrázku ktorý bude zobrazený v danom slide
- `koncovy` - dedí všetky vlastnosti od uvodneho slidu s výnimkou zobrazenia podnadpisu, ktorý ma extrémne veľký font
- `obycajny` - regulérny slide

Každý slide obsahuje elementy `<nadpis>`, reprezentujúci názov slidu (ktorý sa tiež zobrazuje v názve karty prehliadača pri zobrazení) a `<obsah>`, obsahujúci hlavný obsah daného slidu. Hlavný obsah slidu pozostáva z už spomínaných stĺpcov `<stlpec>`. Každý stĺpec má definovanú šírku v atribute `sirka`, ktorá prislúcha grid systému frameworku *Bootstrap*. Šírku je možné definovať číslami od **1** do **12** pričom finálna šírka je podielom zvoleného čísla a čísla **12** (ako to definuje grid systém frameworku *Bootstrap*).

Každý stĺpec môže obsahovať rôzne množstvo elementov z nasledujúceho zoznamu:
- `<text>` - regulérny text, ktorý je pri transformácii zapuzdrený ako paragraf jazyka html `<p>`
- `<obrazok>` - obrázok ktorý sa zobrazí na slide
	- element `<obrazok>` obsahuje podelementy `<zdroj>`, ktorý definuje cestu k obrázku, ktorý sa má zobraziť, `<vyska>`, ktorý definuje výšku zobrazovaného obrázka, `<sirka>` ktorý definuje sirku definovaného obrázka, `<X>` ktorý definuje  pozíciu obrázka na osi X a `<Y>` ktorý definuje pozíciu obrázka na osi Y
- `<tabulka>` - použitý na zadefinovanie všetkých náležitosti potrebných na korektné zobrazeni tabuľky
	- element `<tabulka>` obsahuje podelementy `<riadok>`, ktorý definuje nový riadok tabuľky
	- element `<riadok>` obsahuje voliteľné množstvo podelementov `<hlavicka>`, ktorý definuje bunku tabuľky typu hlavička (zapuzdrené značkou `<th>`) a `<data>`, ktorý definuje dátovú bunku tabuľky (zapuzdrené značkou `<td>`)
	- vzhľadom k tomu, že riadok môže obsahovať aj hlavičkové bunky a aj dátové bunky, tak je možné zostrojiť aj vertikálnu tabuľku, aj horizontálnu tabuľku a aj maticovú tabuľku (viď slide `TRANSPOZIČNÉ ŠIFROVANIE`)
- `<zoznam>` - použitý na zostrojenie zoznamu položiek (ekvivalent `html` značky `<ul>`)
	- obsahuje voliteľné množstvo podelementov `<položka>` ktorý definuje položku zoznamu (ekvivalent `html` značky `<li>`) alebo ďalších zoznamov položiek (`<zoznam>`)
	- každá položka zoznamu obsahuje podelement `<text>` v ktorom je zadefinovaný text položky
- `<literatura>` - zobrazuje „korektné“ formatovanie bibliografických záznamov
	- obsahuje element `<dielo>` ktoré reprezentuje dielo, resp. literatúru ktorá má byť uvedená
	- element `<dielo>` následne obsahuje podelementy `<autor>` definujúci autora diela, `<nazov>` definujúci názov diela, `<rok>` definujúci rok vydania diela a voliteľný atribút `<vydavatel>` definujúci vydavateľa daného diela

Valídnosť `XML` dokumentu podľa priloženého Relax NG dokumentu `prezentacia.rng` bola riadne skontrolovaná validátorom `jing`. Validácia prebehla úspešne.

Zostrojený `XML` strom prezentácie je následne transformovaný do XHTML dokumentu pomocou súboru `nenechaj_sa_vydr.bat`. Pri transformácii `XML` stromu prezentácie do XHTML je je použitá technológia `XSL`, ktorá definuje kroky transformácie. Prvotne sú všetky slidy prezentácie iterované a generované do samostatných `html` súborov v adresári `prezentacia`. Každý slide podľa svojho typu dostane stanovenú štruktúru, ktorá je následne vizuálne vylepšená pomocou kaskádových štýlov obsiahnutých v súbore `custome.css`. V tele html dokumentu `<body>` je inline štýl definujúci (prepisujúci pôvodné štyly) veľkosť textu slidov, veľkosť fontu nadpisov, farbu všetkého textu, obrázok pozadia prezentácie. Hodnoty daných `CSS` atribútov sú definované ako parametre transformácie definované v súbore `hyperparametre.xsl`. Súbor obsahujúci všetky parametre transformácie `hyperparametre.xsl` importuje súbor `prezentacia.xsl`, kde sú zadefinované jednotlivé transformácie `XML` elementov do finálnej podoby `XHTML`. Číslovanie jednotlivých slidov je možné vidieť napríklad v názve súborov slidov (`slide_1.html`, `slide_2.html`). Ďalšie číslovanie je doplnené do názvu jednotlivých slidov, kdežto úvodný a koncový slide nie sú číslované.

Každý slide prezentácie obsahuje navigáciu v podobe šípiek, ktoré po kliknutí presmerujú na nasledujúci, resp. predchadzajúci slide, ak je slide dostupný. Prvý slide prezentácie neobsahuje odkaz na predchádzajpci slide (pretože neexistuje) a posledný slide prezentácie neobsahuje odkaz na nasledujúci slide (pretože tiež neexistuje). Dostupnosť nasledujúceho a predchádzajúceho slidu sa zisťuje `XSL` podmienkovou značkou `<xsl:if text="...podmienka...">`, kde sa zisťuje, či aktuálny slide prezentácie je väčší ako 1 (zobrazí sa šípka predchadzajúci) a následne sa zisťuje, či aktuálny slide je menší ako hodnota posledného slidu (`last()`)(zobrazí sa šípka nasledujúci). Zobrazenie navigácie je možné vypnuť v nastavení parametrov transformácie (v súbore `hyperparametre.xsl`), nastavením parametra `allowArrows` na hodnotu inú ako `hej, chcem`, napríklad `ne, nechcem`.

Výstupom transformácie sú súbory s príponou `.html`. Toto riešenie sme zvolili kvôli nevhodnému zobrazeniu súborov s príponou `.xhtml` prehliadačom Google Chrome.