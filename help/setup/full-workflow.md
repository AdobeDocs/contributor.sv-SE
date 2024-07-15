---
title: Arbetsflöde för GitHub-bidrag för större ändringar
description: Lär dig hur du bidrar till Adobe dokumentation om Experience League.
exl-id: ad467ad4-abd2-4166-8659-e29c48d268ec
source-git-commit: a3c283c5c0d181beacc566262743528d5ff9f7d2
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 0%

---

# Arbetsflöde för GitHub-bidrag för större ändringar

<!--
>[!IMPORTANT]
>All repositories that publish to docs.adobe.com have adopted the [Adobe Open Source Code of Conduct](../../code-of-conduct.md) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct). For more information, see the [Contributing](../../contributing.md) article.
>
> Minor corrections or clarifications to documentation and code examples in public repositories are covered by the [Adobe Documentation Terms of Use](https://www.adobe.com/legal/terms.html). New or significant changes generate a comment in the pull request, asking you to submit an online Contribution License Agreement (CLA) if you are not an employee of Adobe. We need you to complete the online form before we can review or accept your pull request.
--->

## Översikt

Det här arbetsflödet är lämpligt för medarbetare som behöver göra en större ändring eller ofta kommer att bidra till en databas. Vanligtvis har medverkande användare pågående (långvariga) ändringar som går igenom flera bygg-/validerings-/mellanlagringscykler eller sträcker sig över flera dagar innan utdragningsbegäran signeras och sammanfogas.

### Terminologi

Innan du börjar ska vi gå igenom några av Git/GitHub-termerna som används i det här arbetsflödet.

| Namn | Beskrivning |
|-----------|-------------|
| gaffel | Används vanligtvis som ett substantiv när en kopia av en GitHub-huvuddatabas refereras. I praktiken är en gaffel bara en annan databas. Men det är speciellt i den bemärkelsen att GitHub upprätthåller en dubbelriktad anslutning tillbaka till huvuddatabasen/den överordnade databasen. Det används ibland som ett verb, som i&quot;Du måste förfalska databasen först&quot;. |
| fjärr | En namngiven anslutning till en fjärrdatabas, t.ex. &quot;origin&quot;- eller &quot;upstream&quot;-fjärrkontrollen. Git refererar till dessa som fjärrdatabaser eftersom de används för att referera till en databas som finns på en annan dator. I det här arbetsflödet är en fjärr alltid en GitHub-databas. |
| ursprung | Det namn som tilldelats anslutningen mellan din lokala databas och databasen som anslutningen klonades från. I det här arbetsflödet representerar ursprung kopplingen till din gaffel. Det används ibland som en moniker för den ursprungliga databasen, som i&quot;Kom ihåg att överföra dina ändringar till ursprungsläget&quot;. |
| uppströms | Precis som den ursprungliga fjärrkontrollen är upstream en namngiven anslutning till en annan databas. I det här arbetsflödet representerar den överordnade dataströmmen anslutningen mellan din lokala databas och huvuddatabasen som din förgrening skapades från. Det används ibland som en moniker för själva databasen, som i&quot;Kom ihåg att hämta ändringarna från den överordnade databasen&quot;. |

Om du inte känner till Git- och GitHub-koncept som en databas eller en gren bör du först granska [Git- och GitHub-grunder](git-fundamentals.md).

## Arbetsflöde

>[!IMPORTANT]
>
> Om du inte redan har gjort det måste du slutföra stegen i avsnittet [Inställningar](github-signup.md).

I det här arbetsflödet flyter ändringarna i en repetitiv cykel. Med början från enhetens lokala databas flödar de tillbaka till GitHub-gaffeln, in i GitHub-huvuddatabasen och tillbaka lokalt igen när du lägger in ändringar från andra medverkande.

### Använd GitHub-flöde

Kom ihåg från [Git- och GitHub-grunder](git-fundamentals.md) att en Git-databas innehåller en huvudgren, plus eventuella ytterligare pågående grenar som inte har integrerats i huvudgrenen. När du introducerar en uppsättning logiskt relaterade ändringar är det en god vana att skapa en *arbetsgren* för att hantera dina ändringar i arbetsflödet. Vi kallar det här en arbetsgren eftersom det är en arbetsyta som itererar/finjusterar ändringar, tills de kan integreras tillbaka i huvudgrenen.

Genom att isolera relaterade ändringar i en viss gren kan ni styra och införa dessa ändringar oberoende av varandra och inrikta dem på en viss publiceringstid i publiceringscykeln. I verkligheten kan du, beroende på vilken typ av arbete du utför, enkelt få flera arbetsgrenar i databasen. Det är inte ovanligt att arbeta med flera grenar samtidigt, där var och en representerar ett annat projekt.

>[!NOTE]
>
>Att göra ändringar i huvudgrenen *är inte en bra rutin*. Föreställ dig att du använder huvudgrenen för att införa en uppsättning ändringar för en tidsbestämd funktionsrelease. Du slutför ändringarna och väntar på att släppa dem. Under tiden har du en brådskande begäran om att åtgärda något, så du gör ändringen i en fil i huvudgrenen och sedan publicerar ändringen. I det här exemplet publicerar du av misstag både korrigeringen *och* de ändringar som du höll kvar för att släppas på ett visst datum.

Nästa steg är att skapa en ny arbetsgren i din lokala databas för att fånga upp de föreslagna ändringarna. Varje Git-klient är annorlunda, så läs hjälpen för den klient du föredrar. Du kan se en översikt över processen i GitHub-guiden för [GitHub-flödet](https://guides.github.com/introduction/flow/).

## Bearbetning av begäranden

Du skickar in föreslagna ändringar genom att paketera dem i en ny pull-begäran (PR) som läggs till i måldatabasens PR-kö. En pull-begäran möjliggör GitHubs samarbetsmodell genom att be om att ändringarna från din arbetsgren hämtas och sammanfogas till en annan gren. I de flesta fall är den andra grenen standard/huvudgren i huvuddatabasen.

### Validering

Innan din pull-begäran kan sammanfogas i sin målgren kan det vara nödvändigt att gå igenom en eller flera PR-valideringsprocesser. Valideringsprocesserna kan variera beroende på omfattningen av de föreslagna ändringarna och reglerna för måldatabasen. När din pull-begäran har skickats kan du förvänta dig att innehållet ska granskas och, om och när det är lämpligt, sammanfogas i huvuddatabasen.

### Granska och signera

När all PR-bearbetning är klar bör du granska resultatet (PR-kommentarer, förhandsgransknings-URL:er osv.) för att avgöra om det krävs ytterligare ändringar av filerna innan du signerar för sammanslagning. Om en PR-granskare har granskat din pull-begäran kan de även ge feedback via kommentarer om det finns utestående problem/frågor som ska lösas före sammanslagningen.

När pull-begäran är problemfri och signerad sammanfogas dina ändringar i den överordnade grenen och pull-begäran stängs.

### Publicering

Kom ihåg att din pull-begäran måste sammanfogas av en PR-granskare innan ändringarna kan inkluderas i nästa schemalagda publiceringskörning. Dragningsbegäranden granskas/sammanfogas normalt i den ordning som de skickas in. Om din pull-begäran kräver sammanslagning för en viss publiceringskörning måste du arbeta med din PR-granskare i förväg för att säkerställa att sammanslagningen sker före publiceringen.
