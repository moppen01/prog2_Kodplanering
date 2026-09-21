# OOP-projekt – Spelidéer
---

# Färdiga projektidéer

Dessa projekt innehåller en tydlig plan för hur OOP ska användas, men du behöver fortfarande skriva pseudokoden och implementera spelet själv.

---

# 1. Monster Arena

## Spelet

Spelaren har ett monster och möter andra monster i turbaserade strider.

Varje monster har:

* Namn
* HP
* Level
* Attack

Under sin tur kan spelaren exempelvis välja:

* Attack
* Heal

Striden fortsätter tills ett monster har 0 HP.

Börja med ett väldigt enkelt stridssystem. Lägg sedan till fler funktioner om du hinner.

## Arv

Skapa en superklass:

```text
Monster
```

och olika typer av monster:

```text
Monster
├── Dragon
├── Slime
└── Ghost
```

Alla monster ska ärva gemensamma egenskaper från `Monster`, exempelvis:

```text
name
hp
level
```

De olika monstertyperna kan sedan ha egna egenskaper.

## Polymorfism

Alla monster ska ha en metod:

```text
attack()
```

Men attacken ska fungera olika beroende på vilken typ av monster det är.

Exempel:

```text
Dragon.attack()
    → gör fire damage

Slime.attack()
    → gör poison damage

Ghost.attack()
    → gör ghost damage
```

Spelet ska kunna göra:

```text
monster.attack()
```

utan att Battle-klassen behöver veta exakt vilken typ av monster det är.

## Inkapsling

Monsterets HP ska inte kunna ändras direkt från resten av programmet.

Undvik exempelvis:

```text
monster.hp = -500
```

Använd istället metoder:

```text
monster.take_damage(20)
monster.heal(10)
```

Monster-klassen bestämmer själv hur HP får förändras.

## Relationer

En `Player` har ett monster.

En `Battle` har två deltagare.

Exempel:

```text
Player
└── har → Monster

Battle
├── har → Player
└── har → Monster
```

## Minsta fungerande version

Spelet behöver minst kunna:

1. Skapa en spelare
2. Skapa ett monster
3. Starta en strid
4. Låta spelaren attackera
5. Låta monstret attackera
6. Avsluta striden när någon får 0 HP

### Fördjupning

Om du vill bygga vidare:

* Flera monster
* Olika attacker
* Critical hits
* XP
* Leveling
* Specialförmågor
* Olika typer av damage

---

# 2. Café Simulator

## Spelet

Du driver ett café.

Spelaren börjar med en viss mängd pengar och ska tjäna pengar genom att köpa ingredienser, tillverka produkter och sälja dem.

Börja exempelvis med:

```text
Mjöl + Ägg + Socker
        ↓
      Kaka
        ↓
      Sälj
        ↓
     Pengar
```

## Arv

Skapa en superklass:

```text
Product
```

och olika produkter:

```text
Product
├── Coffee
├── Cake
└── Sandwich
```

Alla produkter delar exempelvis:

```text
name
price
```

men varje produkt kan ha olika ingredienser och tillagningsprocess.

## Polymorfism

Alla produkter ska ha en metod:

```text
prepare()
```

Men metoden fungerar olika beroende på produkt.

Exempel:

```text
Coffee.prepare()
    → använd kaffe och mjölk

Cake.prepare()
    → använd mjöl, ägg och socker

Sandwich.prepare()
    → använd bröd, ost och skinka
```

Caféet ska kunna göra:

```text
product.prepare()
```

utan att behöva veta vilken specifik produkt det är.

## Inkapsling

Caféets pengar och lager ska inte kunna ändras direkt.

Undvik exempelvis:

```text
cafe.money += 10000
```

Använd istället metoder som:

```text
cafe.buy_ingredient(...)
cafe.sell_product(...)
```

Café-klassen ansvarar själv för att pengarna och lagret förändras korrekt.

## Relationer

Caféet har ingredienser och produkter och tar emot kunder.

Exempel:

```text
Cafe
├── har → Ingredients
├── har → Products
└── tar emot → Customers

Player
└── driver → Cafe
```

## Minsta fungerande version

Spelet behöver minst kunna:

1. Skapa ett café
2. Ge spelaren pengar
3. Köpa ingredienser
4. Tillverka en produkt
5. Sälja produkten
6. Få pengar från försäljningen

### Fördjupning

* Fler produkter
* Recept
* Kunder
* Beställningar
* Lager
* Olika priser
* Uppgraderingar
* Olika kundtyper

---

# Bygg själv

Här får du en tydlig spelidé och vissa krav.

Du behöver själv bestämma exakt vilka klasser och metoder du behöver och hur OOP-koncepten ska användas.

---

# 3. Djurhem

## Spelet

Du driver ett djurhem.

Djur kommer till djurhemmet och du behöver ta hand om dem tills de kan adopteras.

Djur kan exempelvis behöva:

* Mat
* Lek
* Vila
* Veterinärvård

Olika djur kan ha olika behov.

## Krav

Spelet ska innehålla:

* Minst 3 klasser
* Minst en superklass med subklasser
* Polymorfism
* Inkapsling
* Relationer mellan objekt
* Någon form av spel-loop

### Exempel

Du skulle kunna ha:

```text
Animal
├── Dog
├── Cat
└── Rabbit
```

Men exakt vilka klasser och beteenden du använder bestämmer du själv.

---

# 4. Dungeon Adventure

## Spelet

Spelaren utforskar en dungeon med olika rum.

I rummen kan det finnas exempelvis:

* Föremål
* Dörrar
* Skatter
* Pussel
* Fiender

Målet är att hitta en skatt och ta sig ut ur dungeonen.

Battle är valfritt.

## Krav

Spelet ska innehålla:

* Minst 4 klasser
* Arv
* Polymorfism
* Inkapsling
* Relationer mellan objekt
* Ett tydligt mål
* Någon form av spel-loop

### Exempel

Du skulle kunna ha:

```text
Item
├── Key
├── Potion
└── Treasure
```

Men hur du bygger systemet är upp till dig.

---

# Friare spelidéer

Här får du bara en idé.

Du ansvarar själv för att designa spelet och bestämma hur kraven på OOP ska uppfyllas.

---

# 5. Supermarket Manager

Du driver en liten butik.

Köp in varor, sätt priser och sälj till kunder för att försöka tjäna pengar.

---

# 6. Racing Manager

Du driver ett racingteam.

Köp fordon, anställ förare, uppgradera fordon och tävla i olika lopp.

---

# 7. Hotel Manager

Du driver ett hotell.

Hantera rum, gäster och bokningar och försök få hotellet att gå med vinst.

---

# 8. Potion Shop

Du driver en magisk butik där du tillverkar och säljer olika potions.

Samla eller köp ingredienser och skapa egna recept.

---

# 9. Pirate Trading

Du har ett skepp och reser mellan olika öar.

Köp varor billigt på en plats och försök sälja dem dyrare någon annanstans.

---

# 10. Sports Manager

Du driver ett sportlag.

Hantera spelare, träning, matcher, ekonomi och lagets utveckling.

---

