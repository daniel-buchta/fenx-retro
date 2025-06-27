---
description: Projekt Avoka replacement a.k.a. "Hibernate som zakázal"
---

# ČSOB AREX

## Kontext projektu

### Predmet projektu

Prepis online procesov implementovaných v technológii Avoka do nových technológií&#x20;

* Povodná technológia: Avoka (Temenos)
* Nové technológie: Java, Spring Boot, Camunda...

Na prvý pohľad sa projekt veľmi podobal na FENX, akurát bol jeho uplným opakom.

### Rozsah projektu

* 8 procesov (rôzneho rozsahu)
* 1+ rok práce
* 15 ľudí (Softec tím)

### Výstup projektu

Dodali sme

* 🖥️ 8 FE appka (Angular)
* ⚙️ 4 Mikroslužby / procesné aplikácie (Camunda BPMN) v Java

### Analýza

* na rozdieľ od FENX, kde bolo výstupom analýzy programovanie v Confluence, tu bol výstup priamo Java kód&#x20;

## Technológie

* Onion / hexagonálna architektúra (po ťažkom boji 😁)
* Spring - Spring Boot 3.x, Spring MVC
* Java 17
* Camunda BPMN
* JDBC ("Hibernate som zakázal")
* Flyway
* PostgreSQL
* MapStruct
* Maven
* GitLab CI / Bamboo

### Prostredie

Niekoľko osobitných typov prostredí

* BFF&#x20;
  * NOA - aplikácie pre public web (neautentifikovaných zákazníkov)
  * EIDP - aplikácie pre autentifikovaných zákazníkov
  * AAD - aplikácie pre (autentifikovaných) agentov
  * BOF - aplikácie pre back-office
* DBAPI - aplikácie s prístupom k databáze 😊
  * ostatné aplikácie mohli k databáze pristupovať len cez REST API vystavené cez tieto aplikácie 🤷‍♂️

Typická naša aplikácia bola&#x20;

* rozdelená na 2 samostatne nasadzované aplikácie (BFF + DBAPI) 🤔
* nasadzované do 3 prostredí EIDP + BOF + DBAPI 😮
* nachádzala sa v 4 GIT repozitároch (BFF API + BFF APP + DBAPI API + DBAPI APP) 🤯
