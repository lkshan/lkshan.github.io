---
layout: page
title: Dokumentácia
description: Dokumentácia 1. zadania z WPUB
background: '/img/bg-dokumentacia.jpg'
---
## Zadanie 1

V prvom rade by som chcel poukázať na splnenie všetkých nevyhnutných kritérií splnenia tohoto projektu. Moje sídlo obsahuje všetky tieto podstránky:
- [Úvodná Stránka]({{ "/" | relative_url }})
- [Stránka O mne]({{ "about" | relative_url }})
- [Stránka o mojích pracovných projektoch]({{ "job_projects" | relative_url }})
- [Stránka o mojích školských projektoch]({{ "school_projects" | relative_url }})
- [Detailná stránka projektu]({% post_url 2019-03-02-raiffeisen-centro-bank %})
- [RSS súbor]({{ 'feed.xml' | relative_url }})

V rámci implementácie som využil 4 layouty a to 
- default layout obsahujúci hmtl hlavičky, navigáciu a pätičky - `_layouts/default.html`
- layout pre úvdonú stránku ktorá obsahuje časť môjho životopisu a moje profesijné zručnosti - `_layouts/home.html`
- layout pre bežnú podstránku ktorá obsahuje veľký obrázok (hero image) - `_layouts/page.html`
- layout pre detailný opis každého môjho projektu - `_layouts/post.html`

### Využitie aspoň 5 premenných

Premenné som si zadefinoval v súbore `_config.yml`, kde používam premenné
- **title** - názov stránky ktorý sa zobrazuje v záhlavi karty prehliadača
- **description** - popis stránky ktorý sa zobrazuje na domovskej stránke
- **author** - moje meno ako autora projektu
- **github_username** - názov účtu na GitHube, ktorý sa využíva v tlačidlách pätičky na presmerovanie na sociálne siete
- **facebook-username** - názov účtu na Facebook, ktorý sa využíva v tlačidlách pätičky na presmerovanie na sociálne siete
- **instagram_username** - názov účtu na Instagrame, ktorý sa využíva v tlačidlách pätičky na presmerovanie na sociálne siete

### Využitie kolekcie

Kolekciu som použil v rámci prezentácie mojích idolov. Kolekcie som zadefinoval v súbore `_config.yml` ako
```
collections:
    - my_idols
```
Pozostávajú z troch *front-matter* premenných a to meno/*name*, profesia/*proffesion* a cesta k obrázku, *link*. Kolekcie sú použité na spodnej strane stránky [O mne]({{ 'about' | prepend: site.baseurl | replace: '//', '/' }}).

### Využitie aspoň 5 filtrov

V rámci použitia filtrov som sa snažil využiť rôzne možnosti ktoré sú opísané na oficiálnej stránke [Jekyl](https://jekyllrb.com/docs/liquid/filters/). Príklady použitia *Jekyll* filtrov je možné vidieť v súbore `school_projects/index.html` na riadku 7, kde sú filtrované všetky projekty ktoré patria do skupiny školské (specification == school). Analogicky sú filtrované aj proijekty v súbore `job_projects/index.html` na riadku 7, kde sú filtrované všetky projekty ktoré patria do skupiny pracovné (specification == job). 

Špeciálne filtrovanie je vytvorené v oboch vyššie spomenutých súboroch na riadkoch č. 6. Ide o filtrovanie aktívnych projektov. Táto možnosť bola implementovaná kvôli prípadom, kedy používateľ chce vytvoriť nejaký projekt ale nechcel ho ešte zverejniť. Tým pádom stačí, ak do *front-matter* definície zadeklaruje premennú `active: 0`. Týmto sa vypne viditeľnosť daného projektu v prehľade projektov. Projekt je ale dosiahnuteľný pomocou manuálne zapísanej URL v prehliadači, napr. [skrytá stránka]({% post_url 2019-01-01-test-for-hiding %}).

Ďalšie filtre sú použité v súboroch `_includes/head.html` na riadku 18 a 19, kde pomocou filtra `relativbe_url` vytváram relátivné cesty k *css* súborom. V súbore `_layouts/home.html` je použitý filter *date* na riadkoch 98, 99 a 101 ktorým sa snažím vybrať z aktuálneho dátumu jednotlivé položky (deň, mesiac, rok).

### Využitie pluginu

V rámci implementácie filtra som skúšal rôzne možnosti, no z oficiálnej [stránky GitHub Pages](https://help.github.com/en/articles/configuring-jekyll-plugins) som zistil, že nie všetky filtre fungujú aj na GitHub pages. Z tejto stránky som si zistil, že podporovaný je napríklad plugin `jekyll-feed`. Po nainštalovaní uvedeného pluginu do konzoly som si tento plugin zadefinoval aj v `_config.yml` súbore.  Výsledkom pluginu je vygenerovaný *RSS* súbor ktorý je určený na čítanie noviniek na webových stránkach a všeobecne o syndikácii obsahu. Vygenerovaný *RSS* súbor je možné vidieť na [tomto odkaze]({{ 'feed.xml' | relative_url }}).

### Dodatočné a nepovinné časti

Okrem základných požiadaviek som na stránku pridal aj takzvaný *favicon*. Ide o malé logo môjho webu ktoré sa zobrazuje v záhlaví karty prehliadača na ktorej je moja stránka otvorená.

![Príklad zobrazenia favicon]({{ "img/favicon_example.png" }})

Pre zjednodušenie prístupu a prehľadnosť kódu som si rôzne komponenty layoutov rozdelil na menšie časti a uložil si ich do priečinka `_includes`. Medzi tieto komponenty patria napríklad HTML hlavičky na linkovanie *CSS* a *JS* súborov. Tiež som si osobitne uložil aj navigáciu a pätičku webového sídla.

Pri vyhotovovaní zadania som použil dizajnovací framework Bootstrap, ktorý je uložený v adresári `assets/vendor/bootstrap`. Kvôli zlepšeniu vizualizácie tlačidiel som použil ikonický font zvaný FontAwesome uložený v adresári `assets/vendor/fontawesome-free`. Okrem Bootstrapu som si vytváral aj vlastné štýly ktoré som uložil v adresári `assets/custom.css`.

V projekte som okrem iného použil aj odkazy na extérne stránky ale tiež odkazy aj na vnútorné stránky ako napríklad na rôzne konkrétne projekty na ktoré sa odvolávam v iných projektoch. Príklad využitia vytvorenej linky na inú stránku je možné vidieť aj v otmto súbore na riadku 46.

Už spomínaný ikonický font FontAwesome som nalinkoval z extérneho zdroja. Zdroj je overovaný pomocou SHA integrity. FontAwesome načítavam z externého súboru z dôvodu šetrenia pamäťovým priestorom a tiež, lebo systém AIS nedovoľuje posielanie súborov väčších ako 20MB, tak som musel zmazať nejaké redundantné moduly. 