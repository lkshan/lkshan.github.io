---
layout: page
title: Zadanie 2
description: Dokumentácia 2. zadania z WPUB
background: '/img/bg-dokumentacia.jpg'
---
## Zadanie 2

Zadanie 2 som vypracovával na základe šablóny stiahnutej z webového sídla predmetu WPUB. Stiahnutú šablónu som upravoval a obohaťoval o môj vlastný text z bakalárskeho projektu. Úpravy štýlov som vyklonával v súbore *thesis.xsl*. Prednú stranu dokumentu som štýloval rôznymi štýlmi v súbore *thesis-tp-fo.xsl* Na úvod by som sa rád vyjadril k povinným bodom zadania č. 2.

### Štandardné členenie textu

Text som členil na tri úrovne - kapitola (chapter), podkapitola (section), podpodkapitola (section.section). Hlavným korpustom každej kapitoly je `<chapter></chapter>`. Na vytvorenie podkapitoly hlavnej kapitoly som využil tag `<section></section>` ktorý bol vnorený v tagoch hlavnej kapitoly. Podpodkapitoly sa generovali automaticky postupným vnáraním tagov `<section></section>` v iných tagoch `<section></section>`. Hlvka vnorenia predstavuje úroveď podkapitoly.

Na záver celého dokumentu som uviedol prílohu (Dodatok). Dodatok bol vytvorený tagmi `<appendix></appendix>`. Automaticky generovaný obsah je zadefinovaný v súbore *thesis.xsl* ako `<xsl:param name="generate.toc">`, kde som si zadefinoval, ktoré všetky druhy obsahu chcem aby boli generované automaticky. V mojom prípade som si povolil generovanie tabuľky obsahu (kapitol, podkapitol, ...), zoznamu obrázkov a zoznamu tabuliek.

### Zvýraznenie slov

V texte používam zvýrazňovanie slov pomerne často, predovšetkým pri metematických vzorcov, ktoré podľa štandardu by mali byť vyznačené štýlom *italic*. Taktiež som použil štýl písma **bold**, ktorý je možno vidieť v závere kapitoly *Syntetický gradient*.

V úvode práce som tiež použil zvýraznienie textu odrážkami a v podkapitole *Modul syntetického gradientu a DNI* som použil aj zvýraznenie textu číslovaním.

### Odkazy na iné časti dokumentu

Rovnako ako v pôvodnej verzii bakalárskeho projektu, aj v tejto kópii sa častokrát odkazujem na použitú literatúru. Okrem iného sa v rámci textu odkazujem aj na obrázky, tabuľky a kapitoly v mojom vlastnom dokumente. Odkazovanie na iné časti dokumentu som realizoval pomocou tagu `<xref linkend="xxxx"\>`, kde som ako hodnotu atribútu *linkend* nastavil identifikátor kapitoly/obrázka/tabuľky.

V práci som tiež použil aj prelinkovanie na webovú stránku ktoré je možné vyskúšať v kapitole Literatúra, kde sa odkazujem na webové sídlo autora, mnou použitej literatúry, LeCunn Yanna.

### Poznámka pod čiarou

Poznámku pod čiarou som použil na strane 13, kde som pôvodný odsek nahradil poznámkou pod čiarou. Obsahom poznámky je pôvodný odsek, ktorý vysvetľuje bližšie súvislosti k odseku ktorý sa na danú poznámku odkazuje.

### Zoznam použitej literatúry

Zoznam použitej literatúry sa nachádza na konci hlavnej časti dokumentu (pred Dodatkom). Zoznam použitej literatúry som zadefinoval pomocou tagu `<bibliography></bibliography>`, do ktorého som postupne vkladal konkrétne odkazy na použitú literatúru pomocou tagov `<bibliomixed></bibliomixed>`. Na všetky tieto uvedené zdroje sa v texte riadne odkazujem pomocou už uvedeného spôsobu `<xref linkend="xxx"\>`, kde ako hodnotu parametra *linkend* nastavuje identifikátor literatúry. 

Zoznam použitej literatúry som odstránil z tabuľky obsahuj pomocou *xsl* definície `<xsl:template match="bibliography" mode="toc"\>`

### Vloženie obrázku a tabuliek

V texte je možné vidieť použitie rôznych obrázkov, ktoré prislúchajú kontextu v ktorom sú umiestnené. Okrem pôvodných obrázkov som do textu vložil aj neformálne obrázky ktorým som nastavil fixnú pozíciu. Tieto neformálne obrázku predstavuju náhradu za matematické vzorce ktoré sa nachádzajú v pôvodnom dokumnete. V závere kapitoly *Syntetický gradient* je uvedená tabuľka. Táto tabuľka je fiktívna a bola vložená len kvôli splneniu podmienok tohoto zadania. V pôvodom dokumente sa táto tabuľka nachádza v ďalších prílohách.

V úvode dokumentu je možné vidieť zoznam použitých obrázkov (formálnych) a tiež zoznám tabuliek (formálnych). Na všetky obrázky a tabuľky sa v texte riadne odkazujem pomocou už uvedeného spôsobu `<xref linkend="xxx"\>`, kde ako hodnotu parametra *linkend* nastavuje identifikátor obrázka/tabuľky.

### Vloženie registra pojmov

V závere dokumentu je uvedený register pojmov, ktorý obsahuje obmedzené množstvo všetkých pojmov, ktoré sa v dokumente nachádzajú. Register pojmov som vytvoril pomocou tagu `<index\>` do ktorého sa vkladá automatický generovaný obsah. Generovanie registra pojmov je realizované pomocou tagov `<indexterm></indexterm>`, ktorý definuje termín, ktorý chceme indexovať. V tomto tagu je vnorený tag `<primary></primary>` a `<secondary></secondary>` ktorý definuje úroveň termínu v registri.

Tento register bol použitý len kvôli splneniu podmienok zadania 2 a v pôvodnom dokumente sa nenachádza.