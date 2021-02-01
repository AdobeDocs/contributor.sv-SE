---
title: Grundläggande om dokumentation för Git och GitHub
description: I den här artikeln förklaras en översikt över Git-, GitHub-databasen och hur innehåll är organiserat samt namnkonventioner som används för Adobe-dokumentation.
translation-type: tm+mt
source-git-commit: df6c4152df0c1ee87c9fc4ca22e36a3f13cb620b
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---


# Grundläggande om dokumentation för Git och GitHub

## Översikt

Om du bara behöver göra mindre ändringar i artiklar som bara innehåller text behöver du inte förstå detaljerna i den här artikeln. I den här artikeln beskrivs arbetsflödet för att göra större redigeringar, till exempel skapa nya artiklar, lägga till bilder eller göra pågående redigeringar i Adobe-dokumentationen.

Som medverkande på dokumentationsmaterial från Adobe kan du interagera med flera verktyg och processer. Du kan arbeta parallellt med andra medarbetare i samma projekt, eventuellt med exakt samma innehåll, även samtidigt. Allt detta aktiveras via Git och GitHub.

Git är ett versionshanteringssystem med öppen källkod som möjliggör samarbete. Flera medarbetare kan arbeta med filer som finns i *databaser*.

GitHub är en webbaserad värdtjänst för Git-databaser, till exempel sådana som används för att lagra [docs.adobe.com](https://docs.adobe.com)-innehåll. För alla projekt är GitHub värd för huvuddatabasen, där medarbetare kan göra kopior för eget arbete.

## Git

Git har ett unikt arbetsflöde och en unik terminologi för bidrag som stöder den distribuerade modellen. Det finns till exempel ingen fillåsning som normalt är kopplad till utchecknings-/incheckningsåtgärder. Med Git kan ändringar lösas på ännu finare nivå genom att filer jämförs byte för byte.

Git använder också en nivåindelad struktur för att lagra och hantera innehåll för ett projekt:

- *Databas*: Det här är också en  *repo* som är den högsta lagringsenheten. En databas innehåller en eller flera grenar.
- *Förgrening*: Alla databaser innehåller en standardförgrening (vanligtvis kallad&quot;överordnad&quot;) och en eller flera förgreningar som ska sammanfogas till den överordnad förgreningen. Den överordnad grenen fungerar som den aktuella versionen och källan som innehållet publiceras från. Det är det överordnade objekt som alla andra grenar i databasen skapas från.

Medarbetare interagerar med Git för att uppdatera och ändra databaser på både lokal nivå och GitHub-nivå:

- Lokalt via verktyg som GitHub Desktop.
- Via [www.github.com](https://www.github.com), som integrerar Git för att hantera avstämningen av bidrag som flödar tillbaka till huvuddatabasen.

## GitHub

Alla arbetsflöden börjar och slutar på GitHub-nivå, där huvuddatabasen för alla Adobe-dokumentationsprojekt lagras. Kopiorna som medverkande skapar för eget bruk distribueras till flera datorer. De här kopiorna avstäms så småningom tillbaka till projektets huvudsakliga GitHub-databas.

### Katalogorganisation

Ett projekts standardgren/överordnad gren fungerar som den aktuella versionen av projektinnehåll. Innehållet i den överordnad grenen - och grenar som skapats utifrån den - är anpassat till artikelämnesstrukturen. Underkataloger används för att ordna innehåll och bildresurser.

Du kan vanligtvis hitta en huvudkatalog för `help` från databasens rot. Artikelkatalogen innehåller en uppsättning underkataloger. Artiklar i underkatalogerna formateras som markeringsfiler som använder ett *.md*-tillägg.

I den här katalogens rot finns allmänna artiklar som relaterar till den övergripande tjänsten eller produkten. Och vanligtvis kan du hitta ytterligare en serie underkataloger som matchar funktionerna/tjänsterna eller vanliga scenarier.

### Resurskatalog

Kataloger med användarhandböcker innehåller `/assets` underkataloger för bildfiler som refereras inom en katalog.

<!---
### Markdown file template

For convenience, the root directory of each repository typically contains a Markdown template file named `template.md`. You can use this template file as a "starter file" if you need to create a new article for submission to the repository. The file contains:

- A **metadata header** at the top of the file, delineated by two, 3-hyphen lines. It contains the various tags used for tracking information related to the article. It also includes SEO optimizations and reporting processes that Adobe uses to evaluate the performance of the content. So the metadata is important!
- Various **examples of using Markdown** to format the elements of an article.
- General **instructions on the use of Markdown extensions**, which you can use for various types of alerts.
- Examples of **embedding video** by using an iframe.
- General **instructions on the use of docs.adobe.com extensions**, which you can use for special controls such as buttons and selectors.
-->

## Dra in begäranden

En *pull-begäran* är ett bekvämt sätt för en medarbetare att föreslå en uppsättning ändringar som ska tillämpas på standardgrenen. Ändringarna (kallas även *implementeringar*) lagras i en medarbetares gren, så GitHub kan först modellera effekten av *sammanslagning* till standardgrenen. En pull-begäran fungerar också som en mekanism för att ge medarbetaren feedback från en bygg-/valideringsprocess, granskaren av pull-begäran, för att lösa potentiella problem eller frågor innan ändringarna sammanfogas i standardgrenen.

Det finns två sätt att bidra med pull-begäran, beroende på storleken på de ändringar du vill föreslå. Vi kommer att gå igenom detta i detalj senare, i avsnittet [GitHub-arbetsflöde](local-repo.md) i den här handboken.
