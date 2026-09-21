# OOP-projekt – Spelidéer

Här är några olika idéer på små spel och program som du kan utgå från.

Projekten är olika mycket styrda. På de första idéerna får du mer hjälp med hur OOP kan användas. Längre ner får du större frihet att själv bestämma hur programmet ska byggas.

**Tänk litet!** Du behöver inte skapa ett stort eller avancerat spel. Målet är att göra en liten fungerande prototyp där du får möjlighet att träna på OOP.

---

# Mer styrda projekt

Dessa projekt innehåller en tydlig idé och exempel på hur OOP-koncepten kan användas. Du behöver fortfarande planera programmet, skriva pseudokod och implementera det själv.

---

# 1. Monster Arena

## Spelet

Spelaren har ett monster och möter ett annat monster i en enkel turbaserad strid.

Ett monster kan exempelvis ha:

* Namn
* HP
* Level
* Attack

Under sin tur kan spelaren exempelvis välja att:

* Attackera
* Läka

Striden fortsätter tills någon får 0 HP.

**Håll striden enkel!** Du behöver inte skapa ett avancerat stridssystem.

## Exempel på arv

Du kan skapa en superklass:

```text
Monster
├── Dragon
├── Slime
└── Ghost
```

`Monster` kan innehålla gemensamma egenskaper som:

```text
name
hp
level
```

De olika monstertyperna kan sedan ha egna egenskaper eller beteenden.

## Exempel på polymorfism

Alla monster kan ha en metod:

```text
attack()
```

Men attacken kan fungera olika beroende på vilken typ av monster det är.

```text
Dragon.attack()
    → gör mycket skada

Slime.attack()
    → gör mindre skada

Ghost.attack()
    → gör en speciell attack
```

Programmet ska kunna anropa:

```text
monster.attack()
```

utan att behöva veta exakt vilken typ av monster det är.

## Exempel på inkapsling

Monsterets HP kan vara privat.

I stället för att låta andra delar av programmet ändra HP direkt:

```text
monster.hp = -500
```

kan monsterklassen själv kontrollera hur HP förändras:

```text
monster.take_damage(20)
monster.heal(10)
```

## Exempel på relationer

En `Player` kan ha ett `Monster`.

En `Battle` kan ha två monster.

```text
Player
└── har → Monster

Battle
├── har → Monster
└── har → Monster
```

## Lagom första version

En liten version kan exempelvis:

1. Skapa en spelare
2. Skapa två monster
3. Starta en strid
4. Låta monstren attackera varandra
5. Avsluta när någon får 0 HP

### Om du blir klar

Du kan exempelvis lägga till:

* Flera monster
* Olika attacker
* Specialförmågor
* Level
* XP
* Critical hits

---

# 2. Café Simulator

## Spelet

Du driver ett litet café.

Du har pengar och kan köpa ingredienser, tillverka produkter och sälja dem.

Exempel:

```text
Ingredienser
     ↓
  Tillverka
     ↓
   Produkt
     ↓
    Sälj
     ↓
   Pengar
```

Börja med bara några få produkter och ingredienser.

## Exempel på arv

Du kan skapa:

```text
Product
├── Coffee
├── Cake
└── Sandwich
```

Alla produkter kan exempelvis ha:

```text
name
price
```

men de kan tillverkas på olika sätt.

## Exempel på polymorfism

Alla produkter kan ha:

```text
prepare()
```

men metoden fungerar olika för olika produkter.

```text
Coffee.prepare()
    → tillverka kaffe

Cake.prepare()
    → baka kaka

Sandwich.prepare()
    → gör smörgås
```

Caféet kan då arbeta med olika produkter utan att behöva känna till exakt vilken typ av produkt det är.

## Exempel på inkapsling

Caféets pengar kan vara privat.

I stället för:

```text
cafe.money += 10000
```

kan caféet själv ansvara för hur pengarna förändras:

```text
cafe.buy_ingredient(...)
cafe.sell_product(...)
```

## Exempel på relationer

```text
Cafe
├── har → Ingredients
└── har → Products

Player
└── driver → Cafe
```

## Lagom första version

En liten version kan exempelvis:

1. Skapa ett café
2. Ge spelaren pengar
3. Köpa en ingrediens
4. Tillverka en produkt
5. Sälja produkten
6. Uppdatera pengarna

### Om du blir klar

Du kan exempelvis lägga till:

* Fler produkter
* Recept
* Kunder
* Beställningar
* Lager
* Olika priser
* Uppgraderingar

---

# 3. Djurhem

## Spelet

Du driver ett litet djurhem.

Olika djur kommer till djurhemmet och behöver tas om hand innan de kan adopteras.

Djur kan exempelvis behöva:

* Mat
* Lek
* Vila
* Veterinärvård

Olika djur kan ha olika behov och beteenden.

## Exempel

Du skulle kunna ha:

```text
Animal
├── Dog
├── Cat
└── Rabbit
```

Men du bestämmer själv vilka klasser och beteenden som behövs.

## Lagom första version

Du kan exempelvis göra ett system där spelaren:

1. Ser vilka djur som finns
2. Väljer ett djur
3. Tar hand om djuret
4. Förbättrar djurets behov
5. Försöker få djuret redo för adoption

### Om du blir klar

Du kan exempelvis lägga till:

* Fler djur
* Adoptioner
* Flera behov
* Olika djurbeteenden
* Djur som reagerar olika på aktiviteter

---

# Mer fria projekt

Här får du en spelidé och några ramar, men du behöver själv bestämma hur programmet ska byggas.

Tänk på att hålla projektet litet.

---

# 4. Dungeon Adventure

## Spelet

Spelaren utforskar en liten dungeon med olika rum.

I rummen kan det exempelvis finnas:

* Föremål
* Dörrar
* Skatter
* Pussel
* Fiender

Målet kan vara att hitta en skatt och ta sig ut.

Du behöver inte skapa en stor dungeon. Några få rum räcker.

## Exempel

Du skulle exempelvis kunna ha:

```text
Item
├── Key
├── Potion
└── Treasure
```

Men hur du bygger systemet bestämmer du själv.

### Kom ihåg

Försök hitta:

* En arvshierarki
* En relation mellan objekt
* Ett ställe där polymorfism passar
* Några privata attribut

---

# 5. Potion Shop

Du driver en liten magisk butik där du tillverkar och säljer potions.

Du kan exempelvis:

* Köpa ingredienser
* Tillverka potions
* Sälja potions
* Hantera pengar

Du behöver inte skapa ett stort ekonomisystem.

### Exempel

Du skulle kunna ha olika typer av potions:

```text
Potion
├── HealthPotion
├── SpeedPotion
└── StrengthPotion
```

Men du bestämmer själv hur OOP ska användas.

---

# 6. Supermarket Manager

Du driver en liten butik.

Du kan exempelvis:

* Köpa in varor
* Ha ett lager
* Sätta priser
* Sälja varor
* Hantera pengar

Börja med några få varor och en enkel butik.

Fundera på vilka saker som kan vara klasser och vilka objekt som behöver samarbeta.

---

# 7. Racing Manager

Du driver ett litet racingteam.

Du kan exempelvis hantera:

* Förare
* Fordon
* Lopp
* Uppgraderingar

Du behöver inte skapa ett avancerat racingspel. Det kan räcka att simulera resultatet av ett lopp.

Fundera på vilka saker som är olika typer av samma sak och var arv eller polymorfism kan passa.

---

# 8. Hotel Manager

Du driver ett litet hotell.

Du kan exempelvis hantera:

* Rum
* Gäster
* Bokningar
* Betalningar

Börja med några få rum och en enkel bokningsfunktion.

Fundera på vilka objekt som behöver känna till varandra och vilka egenskaper som bör vara privata.

---

# 9. Pirate Trading

Du har ett skepp och reser mellan några olika öar.

På olika platser kan du köpa och sälja varor.

Exempel:

```text
Ö → köp vara → res → sälj vara
```

Du kan exempelvis ha:

* Skepp
* Öar
* Varor
* Spelare

Börja med två eller tre öar och några få varor.

---

# 10. Sports Manager

Du driver ett litet sportlag.

Du kan exempelvis hantera:

* Spelare
* Tränare
* Matcher
* Träning

Du behöver inte skapa en avancerad sportsimulator. En enkel simulering av matcher räcker.

Fundera på vilka typer av personer eller spelare som kan ha gemensamma egenskaper och beteenden.

---

# Egen idé

Har du en egen spelidé går det också bra!

Tänk bara på att **göra den mindre än du först tror**.

Ett bra projekt kan exempelvis bestå av:

```text
3–4 klasser
↓
några objekt
↓
några metoder
↓
en enkel spel-loop
↓
ett tydligt mål
```

Du behöver inte skapa ett komplett spel.

Om din idé börjar bli väldigt stor: **förenkla den.**

Exempel:

> "Jag vill göra ett Pokémon-spel."

kan bli:

> "Jag gör en liten strid mellan två monster."

---

# Kom ihåg

Oavsett vilket projekt du väljer ska du försöka hitta naturliga användningsområden för:

**Inkapsling**
Vilken information ska klassen själv kontrollera?

**Arv**
Vilka klasser är olika typer av samma sak?

**Relationer**
Vilka objekt behöver ha eller använda andra objekt?

**Polymorfism**
Var kan olika objekt reagera olika på samma metodanrop?

**Planering**
Hur kan du dela upp arbetet i små steg?
