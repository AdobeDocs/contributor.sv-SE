---
title: Contributor guide for Adobe documentation
seo-title: Översikt över Contributor-guiden för Adobe Experience Cloud tekniska dokumentation
description: I guiden beskrivs hur du kan bidra med förslag och tillägg till dokumentationswebbplatsen för Adobe.
seo-description: I guiden beskrivs hur du kan bidra till den [!UICONTROL Adobe Experience Cloud] tekniska dokumentationen.
translation-type: tm+mt
source-git-commit: 8943af2fdf406b2e33db037bb60dfea97df2959a
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 0%

---


# Översikt över Contributor-handboken för Adobe-dokumentation

## Vad är samarbetsdokumentation?

Under 2019 har all teknisk dokumentation och allt aktiveringsinnehåll för Adobe Experience Cloud övergått till en ny plattform som bygger på principer med öppen källkod och använder lösningar från Github, Markdown och Adobe Experience Cloud, inklusive Adobe Experience Manager, Analytics, Launch och Target.

Denna modell med öppen källkod förbättrar innehållskvaliteten och kommunikationen mellan kunder, dokumentationsteam och produktteam. På varje sida kan du nu betygsätta innehållets användbarhet, logga problem och till och med lägga in förslag på innehåll i takt med att Git-förfrågningar skickas (PR). Dokumentationsteamen i Adobe övervakar dagligen bidragen och problemen och gör uppdateringar, förbättringar och justeringar efter behov.

## Arbeta med samarbetsdokumentation

Som användare av det här materialet - oavsett om du är anställd, partner, kund eller till och med presumtiv kund - kan du välja att bidra till den här dokumentationen på flera enkla sätt.

* betygsätta sidans hjälpmedel
* logga ett problem mot en viss sida
* till och med skicka in en snabb redigering till hela artiklar, komplett med resurser och kodexempel

Den här guiden innehåller allt du behöver veta för att interagera med och bidra till materialuppsättningen.

<!--
>[!IMPORTANT]
>All repositories that publish to docs.adobe.com have adopted the [Adobe Open Source Code of Conduct](../code-of-conduct.md) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct). For more information, see the [Contributing](../contributing.md) article.
>
> Minor corrections or clarifications to documentation and code examples in public repositories are covered by the [Adobe Documentation Terms of Use](https://www.adobe.com/legal/terms.html). New or significant changes generate a comment in the pull request, asking you to submit an online Contribution License Agreement (CLA) if you are not an employee of Adobe. We need you to complete the online form before we can review or accept your pull request.
-->

## Redigera snabbt befintliga dokument

Att göra snabba redigeringar är ett bra sätt att åtgärda små fel och utelämnanden i dokument. Om en artikel visar en redigeringsknapp som visas nedan kan du göra en snabbkorrigering själv. När du redigerar dokumentet skickar du en pull-begäran (PR) för att skicka korrigeringen/förslaget till oss, och vi kan granska, godkänna och publicera förslaget.

1. Underteckna [Contributor-licensavtalet (CLA)](http://opensource.adobe.com/cla.html) om det går.

   Du behöver bara skicka ett Adobe CLA en gång.
1. Klicka på **`Edit this page`** ikonen i den högra kolumnen för att gå till markeringskällfilen på GitHub.

   ![Redigera den här sidikonen](/help/assets/git_edit.png)

1. Klicka på pennikonen för att redigera artikeln.

   >[!NOTE]
   >
   >Om pennikonen är nedtonad måste du logga in på ditt GitHub-konto eller skapa ett nytt konto.

   ![Placering av pennikonen](assets/edit-icon.png)

1. Gör ändringarna i webbredigeraren. Du kan klicka på fliken **Förhandsgranska ändringar** för att kontrollera formateringen av ändringen.
1. När du har gjort ändringarna bläddrar du längst ned på sidan. Ange en rubrik och beskrivning för din PR och klicka på **Föreslå filändring** enligt följande figur:

   ![föreslå ändringar](assets/submit-pull-request.png)

   >[!NOTE]
   >
   >Om du får ett meddelande om valideringsfel när du signerar ett CLA-avtal (Contributor License Agreement) klickar du på **Information** för att öppna licensavtalet. Signera avtalet, om det accepteras. Stäng och öppna pull-begäran och fortsätt.

Det är allt som finns för det. Tack! Dokumentationsteamets medlemmar granskar och sammanfogar din begäran.

## Logga ett problem

Ett annat enkelt sätt att informera oss om ett problem med ett visst innehåll är att logga ett problem.

1. Om du ser ett problem med en del av innehållet klickar du på **`Log an Issue`** ikonen i den högra kolumnen.

   ![](assets/git_log_issue.png)

   >[!NOTE]
   >
   >Du måste logga in på ditt GitHub-konto eller skapa ett nytt konto för att kunna logga in på ett problem.

   Om du klickar på den här länken kan du logga en snabbbiljett hos oss med hjälp av gränssnittet för Github Issue.

1. URL:en för sidan med problemet fylls i automatiskt i beskrivningsfältet. Fyll i rubriken, skriv en kort beskrivning av problemet och klicka sedan på *Skicka nytt problem*.

   ![](assets/git_issue_example.png)

Om du skickar in ett problem meddelas innehållsteamet för den här sidan direkt som kan vidta åtgärder. När vi har uppdaterat innehållet får du veta det i gränssnittet för Github Issues och du får ett e-postmeddelande när det uppdateras eller stängs.

## Förstå GitHub-behörigheter

Gränssnittet för GitHub-redigering anpassas till dina databasbehörigheter. Bilderna ovan gäller för medarbetare som inte har skrivbehörighet till måldatabasen. GitHub skapar automatiskt en gaffel av måldatabasen i ditt konto. Om du har skrivåtkomst till måldatabasen skapar GitHub en ny gren i målrapporten.

Adobe använder pull-begäranden för alla ändringar, även för medarbetare som har skrivbehörighet. De flesta databaser har `master` grenen skyddad så att uppdateringar måste skickas som pull-begäranden.

Redigeringsfunktionen i webbläsaren passar bäst för smärre eller ovanliga ändringar. Om du ger stora bidrag eller använder avancerade Git-funktioner rekommenderar vi att du [förser ombudet och arbetar lokalt](setup/full-workflow.md).

## Ge feedback

Med en lösning som är lika stor som Adobe är dokumentationen alltid ett pågående arbete. Om du upptäcker fel bör du logga ett problem och informera oss om du har förslag på material. Berätta vilken information du sökte efter. Meddela oss om du inte hittar det du behöver, eller om du har problem med att slutföra din uppgift, var vänlig och tala om för oss hur vi kan hjälpa dig att lära dig våra lösningar.

Tack från Collaborative Documentation-teamet och alla skribenter och innehållsproducenter i [!UICONTROL Adobe Experience Cloud].
