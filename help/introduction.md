---
title: Contributor guide for Adobe Documentation
seo-title: Contributor guide overview for Adobe Experience Cloud technical documentation
description: I guiden beskrivs hur du kan bidra med förslag och tillägg till dokumentationswebbplatsen för Adobe.
seo-description: The guide describes how you can contribute to the [!UICONTROL Adobe Experience Cloud] technical documentation.
exl-id: 1294d0c6-897e-49c0-bf27-fd7d122f1fc8
source-git-commit: 2721a71924c46e1536394625c945bdd791e8ac70
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 0%

---

# Contributor Guide for Adobe Documentation

I den här guiden beskrivs hur du kan bidra till Adobe Enterprise-hjälp på Experience League.

## Vad är samarbetsdokumentation?

Den tekniska dokumentationen och aktiveringsinnehållet för Adobe Experience Cloud och andra Adobe Enterprise-produkter bygger på principer med öppen källkod som använder GitHub-, Markdown- och Adobe Experience Cloud-lösningar.

Denna modell med öppen källkod förbättrar innehållskvaliteten och kommunikationen mellan kunder, dokumentationsteam och produktteam. På varje sida kan du nu betygsätta innehållets användbarhet, logga problem och till och med lägga in förslag på innehåll i takt med att Git-förfrågningar skickas (PR). Dokumentationsteamen i Adobe övervakar dagligen bidragen och problemen och gör uppdateringar, förbättringar och justeringar efter behov.

## Arbeta med samarbetsdokumentation

Som användare av det här materialet - oavsett om du är anställd, partner, kund eller till och med presumtiv kund - kan du välja att bidra till den här dokumentationen på flera enkla sätt.

* Betygsätt hur hjälpsam sidan är ❶ och skriv en valfri ❷
* Rapportera ett problem mot en viss sida (kräver Git-inloggning) ❸
* Skicka in en snabb redigering till hela artiklar, komplett med resurser och kodexempel (kräver Git-inloggning) ❹

![Feedback](assets/feedback-options.png)

Dessa alternativ visas längst ned på sidan några sekunder efter att den har öppnats. Om du stänger feedbackområdet kan du läsa in sidan igen för att få tillbaka den.

Den här guiden innehåller allt du behöver veta för att interagera med och bidra till materialuppsättningen.

<!--
>[!IMPORTANT]
>All repositories that publish to docs.adobe.com have adopted the [Adobe Open Source Code of Conduct](../code-of-conduct.md) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct). For more information, see the [Contributing](../contributing.md) article.
>
> Minor corrections or clarifications to documentation and code examples in public repositories are covered by the [Adobe Documentation Terms of Use](https://www.adobe.com/legal/terms.html). New or significant changes generate a comment in the pull request, asking you to submit an online Contribution License Agreement (CLA) if you are not an employee of Adobe. We need you to complete the online form before we can review or accept your pull request.
-->

## Betygsätt hur hjälpsam sidan är och skriv en kommentar

Några sekunder efter att du har öppnat en sida visas ett feedbackområde längst ned på sidan. Klicka uppåt eller nedåt för att ange om sidan var till hjälp.

Lämna gärna en kommentar för att lämna ytterligare feedback.

## Redigera snabbt befintliga dokument

Om du vill ge mer detaljerad feedback är det ett bra sätt att åtgärda små fel och utelämnanden i dokument genom att göra snabba ändringar. När du föreslår en redigering skickar du en pull-begäran (PR) för att skicka korrigeringen/förslaget till oss, och vi kan granska, godkänna och publicera förslaget.

1. Underteckna [Contributor-licensavtalet (CLA)](http://opensource.adobe.com/cla.html) om det går.

   Du behöver bara skicka ett Adobe CLA en gång.

1. I det feedbackområde som visas längst ned i artikeln klickar du på **[!UICONTROL Detailed feedback options]** och sedan på **[!UICONTROL Suggest an edit]** för att gå till markeringskällfilen på GitHub.

   ![Redigera den här sidikonen](/help/assets/feedback-suggest-edit.png)

1. Klicka på pennikonen för att redigera artikeln.

   >[!NOTE]
   >
   >Om pennikonen är nedtonad måste du logga in på ditt GitHub-konto eller skapa ett nytt konto.

   ![Placering av pennikonen](assets/git_edit.png)

1. Gör ändringarna i webbredigeraren.

   Du kan klicka på fliken **[!UICONTROL Preview changes]** för att kontrollera formateringen av ändringen.

1. När du har gjort ändringarna bläddrar du längst ned på sidan.

   Ange en rubrik och beskrivning för din PR och klicka sedan på **[!UICONTROL Propose file change]** så som visas i följande bild:

   ![föreslår din ändring](assets/submit-pull-request.png)

   >[!NOTE]
   >
   >Om du får ett valideringsfelmeddelande om signering av ett CLA-avtal (Contributor License Agreement) klickar du på **[!UICONTROL Details]** för att öppna licensavtalet. Signera avtalet, om det accepteras. Stäng och öppna pull-begäran och fortsätt.

Det är allt som finns för det. Dokumentationsteamets medlemmar granskar och sammanfogar din pull-förfrågan. Tack!

## Rapportera ett problem

Ett annat enkelt sätt att informera oss om ett problem med ett innehåll är att använda **[!UICONTROL Report an issue]**.

1. I det feedbackområde som visas längst ned i artikeln klickar du på **[!UICONTROL Detailed feedback options]** och sedan på **[!UICONTROL Report an issue]** för att gå till markeringskällfilen på GitHub.

   ![Rapportera problem](assets/feedback-report-issue.png)

   >[!NOTE]
   >
   >Om du vill rapportera ett problem måste du logga in på ditt GitHub-konto eller skapa ett konto.

   Om du klickar på den här länken kan du logga en snabbbiljett med Experience League med hjälp av gränssnittet för Github Issue.

   URL:en för sidan med problemet fylls i automatiskt i beskrivningsfältet.

1. Fyll i rubriken, skriv en kort beskrivning av problemet och klicka sedan på *Skicka nytt problem*.

   ![](assets/git_issue_example.png)

Om du skickar in ett problem meddelas innehållsteamet för den här sidan, som kan åtgärda problemet. När vi har uppdaterat innehållet får du veta det i gränssnittet för Github Issues och du får ett e-postmeddelande när det uppdateras eller stängs.

## Förstå GitHub-behörigheter

Gränssnittet för GitHub-redigering anpassas till dina databasbehörigheter. Bilderna ovan gäller för medarbetare som inte har skrivbehörighet till måldatabasen. GitHub skapar automatiskt en gaffel av måldatabasen i ditt konto. Om du har skrivåtkomst till måldatabasen skapar GitHub en ny gren i målrapporten.

Adobe använder pull-begäranden för alla ändringar, även för medarbetare som har skrivbehörighet. De flesta databaser har grenen `main` skyddad så att uppdateringar måste skickas som pull-begäranden.

Redigeringsfunktionen i webbläsaren passar bäst för smärre eller ovanliga ändringar. Om du ger stora bidrag eller använder avancerade Git-funktioner rekommenderar vi att du [förser ombudet och arbetar lokalt](setup/full-workflow.md).

## Ge feedback

Med en lösning som är lika stor som Adobe är dokumentationen alltid ett pågående arbete. Om du upptäcker fel bör du logga ett problem och informera oss om du har förslag på material. Berätta vilken information du sökte efter. Meddela oss om du inte hittar det du behöver, eller om du har problem med att slutföra din uppgift, var vänlig och tala om för oss hur vi kan hjälpa dig att lära dig våra lösningar.

Tack från Collaborative Documentation-teamet och alla skribenter och innehållsproducenter i Experience League.
