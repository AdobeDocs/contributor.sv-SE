---
title: Använda Markdown för att skriva dokumentation
description: den här artikeln innehåller grundläggande information och referensinformation för det markeringsspråk som används för att skriva artiklar.
exl-id: 3e5726e2-139e-4e44-ae5b-8a3ae4782faf
source-git-commit: 4104aa1481263dabe20f2e3a117944f55a6fd800
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 1%

---

# Använda Markdown för att skriva teknisk dokumentation

Adobe tekniska dokumentationsartiklar är skrivna på ett lättviktsmarkeringsspråk med namnet [Markdown](https://daringfireball.net/projects/markdown/), som är både enkelt att läsa och lätt att lära sig.

När vi lagrar Adobe Docs-innehåll i GitHub kan den använda en Markdown-version med namnet [GitHub Flavred Markdown (GFM)](https://help.github.com/categories/writing-on-github/), som har ytterligare funktioner för vanliga formateringsbehov. Dessutom har Adobe extended Markdown flera sätt att stödja vissa hjälprelaterade funktioner som anteckningar, tips och inbäddade videor.

## Grunderna i markdown

### Rubriker

Om du vill skapa en rubrik använder du ett hash-märke (#) i början av en rad:

```
# This is level 1 (article title)
## This is level 2
### This is level 3
#### This is level 4
##### This is level 5
```

### Grundläggande text

Ett stycke kräver ingen speciell syntax i Markdown.

Om du vill formatera text som **fet** omger du den med två asterisker. Om du vill formatera text som *kursiv* omsluter du den med en enkel asterisk:

```markdown
   This text is **bold**.
   This text is *italic*.
   This text is both ***bold and italic***.
```

Om du vill ignorera markeringsformateringstecken använder du \ före tecknet:

```markdown
This is not \*italicized\* type.
```

### Numrerade listor och punktlistor

Om du vill skapa numrerade listor börjar du en rad med `1.` eller `1)`, men använder inte båda formaten i samma lista. Du behöver inte ange siffrorna. GitHub gör det åt dig.

```markdown
1. This is step 1.
1. This is the next step.
1. This is yet another step, the third.
```

Visas:

1. Detta är steg 1.
1. Detta är nästa steg.
1. Detta är ännu ett steg, det tredje.

Om du vill skapa punktlistor börjar du en rad med \* eller - eller +, men blandar inte formaten i samma lista. (Blanda inte punktformat som \* och \+ i samma dokument.)

```markdown
* First item in an unordered list.
* Another item.
* Here we go again.
```

Visas:

* Första objektet i en osorterad lista.
* Ett annat objekt.
* Här är vi igen.

Du kan även bädda in listor i listor och lägga till innehåll mellan listobjekt.

```markdown
1. Set up your table and code blocks.
1. Perform this step.

   ![screen](assets/no-localize/adobe_standard_logo.png)
1. Make sure that your table looks like this: 

   | Hello | World |
   |---|---|
   | How | are you? |  
1. This is the fourth step.

   >[!NOTE]
   >
   >This is note text.

1. Do another step.
```

Visas:

1. Skapa tabeller och kodblock.
1. Utför det här steget.

   ![screen](assets/no-localize/adobe_standard_logo.png)
1. Se till att tabellen ser ut så här:

   | Hej | World |
   |---|---|
   | Hur | Är du? |
1. Detta är det fjärde steget.

   >[!NOTE]
   >
   >Det här är anteckningstext.

1. Gör ett steg till.

### Tabeller

Tabeller ingår inte i den centrala markeringsspecifikationen, men Adobe stöder dem i viss utsträckning. Markering stöder inte flera rader i celler. Det bästa sättet är att undvika att använda flera rader i tabeller. Du kan skapa tabeller genom att använda vertikalstrecket (|) för att avgränsa kolumner och rader. Bindestreck skapar varje kolumns sidhuvud, medan rörledningar avgränsar varje kolumn. Inkludera en tom rad före tabellen så att den återges korrekt.

```markdown
| Header | Another header | Yet another header |
|--- |--- |--- |
| row 1 | column 2 | column 3 |
| row 2 | row 2 column 2 | row 2 column 3 |
```

Visas:

| Sidhuvud | En annan rubrik | Ännu en rubrik |
|--- |--- |--- |
| rad 1 | kolumn 2 | kolumn 3 |
| rad 2 | rad 2 kolumn 2 | rad 2 kolumn 3 |

Enkla tabeller fungerar korrekt i Markdown. Tabeller som innehåller flera stycken eller listor i en cell är emellertid svåra att arbeta med. För sådant innehåll rekommenderar vi att du använder ett annat format, t.ex. rubriker och text.

Mer information om hur du skapar tabeller finns i:

* GitHub&#39;s [Organisera information med tabeller](https://help.github.com/articles/organizing-information-with-tables/)
* Webbprogrammet [Markup Tables Generator](https://www.tablesgenerator.com/markdown_tables)
* [Konvertera HTML-tabeller till markering](https://jmalarcon.github.io/markdowntables/)

### Länkar

Markeringssyntaxen för en infogad länk består av `[link text]`-delen, som är den text som hyperlänkas, följt av `(file-name.md)`-delen, som är den URL eller det filnamn som länkas till:

`[link text](file-name.md)`

```markdown
[Adobe](https://www.adobe.com)
```

Visas:

[Adobe](https://www.adobe.com)

Använd relativa länkar för länkar till artiklar (korsreferenser) i databasen. Du kan använda alla relativa länkoperander, till exempel ./ (aktuell katalog), ../ (bakåt en katalog) och ../../ (bakåt två kataloger).

```markdown
See [Overview example article](../../overview.md)
```

Mer information om hur du länkar finns i artikeln [Länkar](linking.md) i den här guiden för att länka syntax.

### Bilder

```markdown
![Adobe Logo](assets/no-localize/adobe_standard_logo.png "Hover text")
```

Visas:

![Adobe ](assets/no-localize/adobe_standard_logo.png "LogoHover-text")

**Obs!** För bilder som inte ska lokaliseras skapar du en separat  `do-not-localize` mapp i resursmappen. Vanligtvis placeras bilder utan text eller bilder som bara innehåller exempelinnehåll där. Detta tar bort&quot;brus&quot; från resursmappen och minskar antalet frågor.

### Kodblock

Markdown stöder placeringen av kodblock både textbundet i en mening och som ett separat&quot;fenced&quot;-block mellan meningar. Mer information finns i [Markeringens inbyggda stöd för kodblock](https://daringfireball.net/projects/markdown/syntax#precode)

Använd bakåttickningar (&amp;stämpel;grav;) ) för att skapa textbundna kodformat i ett stycke. Om du vill skapa ett specifikt flerradskodblock lägger du till tre bakåtmarkeringar (&amp;grave;&amp;grave;) före och efter kodblocket (kallas för ett&quot;fenced code block&quot; i Markdown och bara en&quot;code block&quot;-komponent i AEM). För avgränsade kodblock lägger du till kodspråket efter den första uppsättningen bakåtfästingar så att Markdown markerar kodsyntaxen korrekt. Exempel: &amp;Klona;grav;&amp;grav;&amp;grav;javascript

Exempel:

```markdown
This is `inline code` within a paragraph of text.
```

Visas:

Detta är `inline code` i ett textstycke.

Detta är ett avgränsat kodblock:

```javascript
function test() {
 console.log("notice the blank line before this function?");
```

## Anpassade markeringstillägg

I Adobe-artiklar används standardmarkering för de flesta artikelformat, som stycken, länkar, listor och rubriker. För mer omfattande formatering kan artiklar använda utökade markeringsfunktioner som:

* Anteckningsblock
* Inbäddade videoklipp
* Lokalisera inte
* Komponentegenskaper, som att tilldela ett annat rubrik-ID till en rubrik

Använd markeringsblockcitattecken ( > ) i början av varje rad för att knyta samman en utökad komponent, t.ex. en anteckning. Om du behöver använda underkomponenter i komponenter lägger du till en extra nivå med blockcitattecken (> >) för det underkomponentavsnittet. En NOTE i ett DONOTLOCALIZE-avsnitt ska till exempel börja med >    >.

Vissa vanliga markeringselement som rubriker och kodblock innehåller utökade egenskaper. Om du behöver ändra standardegenskaperna lägger du till parametrarna inom franska klammerparenteser /{ /} efter komponenten. Utökade egenskaper beskrivs i sitt sammanhang.

### Anteckningsblock

Du kan välja mellan följande typer av anteckningsblock för att dra uppmärksamheten till specifikt innehåll:

* `[!NOTE]`
* `[!TIP]`
* `[!IMPORTANT]`
* `[!CAUTION]`
* `[!WARNING]`
* `[!ADMINISTRATION]`
* `[!AVAILABILITY]`
* `[!PREREQUISITES]`

I allmänhet bör anteckningsblock användas sparsamt eftersom de kan vara störande. Även om de även har stöd för kodblock, bilder, listor och länkar kan du försöka göra anteckningsblocken enkla och enkla.


```markdown
>[!NOTE]
>
>This is a standard NOTE block.
```

Visas:

>[!NOTE]
>
>Det här är ett vanligt NOTE-block.

```markdown
>[!TIP]
>
>This is a standard tip.
```

Visas:

>[!TIP]
>
>Det här är ett standardtips.

### Videor

Inbäddade videofilmer återges inte direkt i Markdown, men du kan använda det här Markdown-tillägget.

```markdown
>[!VIDEO](https://video.tv.adobe.com/v/29770/?quality=12)
```

Visas:

>[!VIDEO](https://video.tv.adobe.com/v/29770/?quality=12)

### Mer som detta

Komponenten &quot;Mer som den här&quot; i AEM visas i slutet av en artikel. Här visas relaterade länkar. När artikeln återges kan den formateras på samma sätt som rubriker på nivå 2 (##) utan att läggas till i miniinnehållsförteckningen.

```markdown
>[!MORELIKETHIS]
>* [Article 1](https://helpx.adobe.com/support/analytics.html)
>* [Article 2](https://helpx.adobe.com/support/audience-manager.html)
```

Visas:

>[!MORELIKETHIS]
>* [Artikel 1](https://helpx.adobe.com/se/support/analytics.html)
>* [Artikel 2](https://helpx.adobe.com/se/support/audience-manager.html)


### UICONTROL och DNL

Allt vårt Markdown-hjälpinnehåll lokaliseras till att börja med med med maskinöversättning. Om hjälpen aldrig har lokaliserats behåller vi maskinöversättningen. Om hjälpinnehållet tidigare har lokaliserats fungerar maskinöversatt innehåll som platshållare medan innehållet håller på att översättas av människor.

**``**

Under maskinöversättning kontrolleras objekt som är taggade med `` mot en lokaliseringsdatabas för korrekt översättning. Om användargränssnittet inte är lokaliserat kommer den här taggen att göra det möjligt för systemet att lämna användargränssnittsreferensen på engelska för det språket (dvs. Analysreferenser på italienska).

**Exempel:**

1. Gå till skärmen **[!UICONTROL Run Process]**.
1. Välj **[!UICONTROL File > Print > Print All]** om du vill skriva ut alla filer på servern.
1. Dialogrutan [!UICONTROL Processing Rules] visas.

**Källa:**

```markdown
1. Go to the **[!UICONTROL Run Process]** screen.
1. Choose **[!UICONTROL File > Print > Print All]** to print all the files on your server.
1. The [!UICONTROL Processing Rules] dialog box appears.
```

**Obs!** Bland de tre taggningsalternativen är detta det viktigaste för att få hög kvalitet och det är obligatoriskt.

**`[!DNL]`**

I regel använder vi en&quot;Do not translate&quot;-lista för att tala om för maskinöversättningsmotorerna vad de ska behålla på engelska. De vanligaste är långa lösningsnamn som&quot;Adobe Analytics&quot;,&quot;Adobe Campaign&quot; och&quot;Adobe Target&quot;. Det kan dock finnas fall där vi måste tvinga motorn att använda engelska eftersom termen i fråga kan användas på ett specifikt eller allmänt sätt. Det mest uppenbara fallet är korta namn på lösningar som&quot;Analytics&quot;,&quot;Campaign&quot;,&quot;Target&quot; osv. Det skulle vara svårt för en maskin att förstå att det här är lösningens namn och inte allmänna termer. Taggen kan även användas för namn/funktioner från tredje part som alltid finns kvar på engelska eller för kortare textavsnitt, som fraser eller meningar, som måste vara på engelska.

**Exempel:**

* Med [!DNL Target] kan du skapa A/B-tester för att hitta det optimala
* Adobe Analytics är en kraftfull lösning för att samla in analyser på er webbplats. [!DNL Analytics] kan också hjälpa er med att rapportera så att ni enkelt kan sammanställa dessa data.

**Källa:**

```markdown
* With [!DNL Target], you can create A/B tests to find the optimal 
* Adobe Analytics is a powerful solution to collect analytics on your site. [!DNL Analytics] can also help you with reporting to easily digest that data.
```

## Gotchas och felsökning

### Alt-text

Alt-text som innehåller understreck återges inte korrekt. I stället för att använda detta:

```markdown
![Settings_Step_2](/assets/settings_step_2.png)
```

Det bästa sättet är att använda bindestreck (-) i stället för understreck (_) i filnamn.

```markdown
![Settings-Step-2](/assets/settings-step-2.png)
```

### Apostrofer och citattecken

Om du kopierar text till en markeringsredigerare kan texten innehålla&quot;smarta&quot; (typografiska) apostrofer eller citattecken. Dessa måste kodas eller ändras till apostrofer eller citattecken. Annars får du udda tecken som detta när filen publiceras: Itâ€™s

Här är kodningarna för de&quot;smarta&quot; versionerna av dessa skiljetecken:

* Vänster (inledande) citattecken: `&#8220;`
* Höger (avslutande) citattecken: `&#8221;`
* Höger (avslutande) enkelt citattecken eller apostrof: `&#8217;`
* Vänster (inledande) apostroftecken (används sällan): `&#8216;`

### Vinkelparenteser

Om du använder vinkelparenteser i text (inte kod) i filen, till exempel för att ange en platshållare, måste du koda vinkelparenteserna manuellt. Annars tror Markdown att de är avsedda att vara en HTML-tagg.

Koda till exempel `<script name>` som `&lt;script name&gt;`

### Förtexter

et-tecken (&amp;) tillåts inte i titlar. Använd&quot;och&quot; i stället, eller använd kodningen `&amp;`.

## Se även

### Markeringsresurser

* [Introduktion till markering](https://daringfireball.net/projects/markdown/syntax)
* [GitHub&#39;s Markdown Basics](https://help.github.com/articles/markdown-basics/)
