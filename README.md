# Eget spelprojekt
Nu när vi lärt oss alla byggstenar i OOP ska vi såklart testa våra skills, och hur gör vi det bättre än att få koda ett till spel? Innan vi börjar koda nu däremot, ska vi lära oss hur man kan planera och strukturera upp sitt projekt innan man börjar skriva kod. Vilken typ av spel ni gör är upp till er själva att bestämma, men det finns en rad olika förslag på spel med exempel i md filen "exempel.md" här på detta repo.

## Steg 1: Planering - Pseudokod
När du har bestämt vilken typ av spel du ska göra och bestämt hur det ska se ut ska du göra en grov kodplanering i pseudokod. **Pseodkoden ska skrivas i en .md fil och ska finnas med i ditt repo!** 

Du ska självklart inte behöva skriva exakt varje liten funktionalitet i pseudkod, utan poängen är att få med huvudlogiken i spelet. Till exempel kan du göra något som liknar exemplet här under:

```text
SPEL

    Starta spelet
        Skapa spelare
        Visa startmeny

    Startmeny
        Starta nytt spel
        Ladda spel
        Avsluta

    Spel-loop
        Visa spelvärlden
        Läs spelarens val

        Om spelaren rör sig:
            Flytta spelaren

        Om spelaren möter en fiende:
            Starta strid

        Om spelaren hittar ett föremål:
            Lägg till föremålet i inventory

        Om spelaren når målet:
            Avsluta spelet
```

## Steg 2: Planering - Kanban board
När grovplaneringen är klar och du har skrivit pseudokod så ska du skapa en Kanban board här på GitHub. 

Det finns ett exempel på en Kanban här i mitt repo. Gå in på "project" fliken för att se det! 

<ol>
  <li>Pusha upp din pseudokod och ditt repo så det ligger publikt på GitHub</li>
  <li>Gå in på fliken "Projects" och skapa en ny Canban. Gör projektet Publikt.</li>
  <li>Gå på kugghjulsikonen (view) och välj Board + Spara</li>
  <li>Skapa några huvudtasks! Lek runt lite med det, ha kul!</li>
</ol>

## Steg 3: Let the games begin!
Nu när du har planerat upp ditt projekt är det bara att dra igång med kodandet. Skriv koden i samma repo som din planeringsfil och din board, så allt är samlat på samma ställe. 
