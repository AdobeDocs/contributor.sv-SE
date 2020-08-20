---
lastModified: 2018-06-28T00:00:00Z
title: Använda Markdown för att skriva dokumentation
seo-title: Använda Markdown för att skriva Adobe-dokumentation
description: den här artikeln innehåller grundläggande information och referensinformation för det markeringsspråk som används för att skriva artiklar.
seo-description: I den här artikeln finns grundläggande information och referensinformation för det markeringsspråk som används för att skriva artiklar för Adobe-dokumentation.
translation-type: tm+mt
source-git-commit: 27ba164070996d192c84493d83232484d2badb28
workflow-type: tm+mt
source-wordcount: '1329'
ht-degree: 1%

---


# Använda Markdown för att skriva teknisk dokumentation

Adobe tekniska dokumentationsartiklar är skrivna på ett lättviktsmarkeringsspråk som kallas [Markdown](https://daringfireball.net/projects/markdown/), som både är lätt att läsa och lätt att lära sig.

När vi lagrar Adobe Docs-innehåll i GitHub kan den använda en version av Markdown som kallas [GitHub Flavred Markdown (GFM)](https://help.github.com/categories/writing-on-github/), som har ytterligare funktioner för vanliga formateringsbehov. Dessutom har Adobe extended Markdown flera sätt att stödja vissa hjälprelaterade funktioner som anteckningar, tips och inbäddade videor.

## Grunderna i markeringar

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

Om du vill formatera text som **fet** omsluter du den med två asterisker. Om du vill formatera text som *kursiv* omsluter du den med en asterisk:

```markdown
    This text is **bold**.
    This text is *italic*.
    This text is both ***bold and italic***.
```

<!--
To format superscript (H<sub>2</sub>O) and subscript (e=mc<sup>2</sup>) text:

```markdown
This is subscript H<sub>2</sub>O and superscript e=mc<sup>2</sup>.
```
-->

Om du vill ignorera markeringsformateringstecken använder du \ före tecknet:

```markdown
This is not \*italicized\* type.
```

### Numrerade listor och punktlistor

Om du vill skapa numrerade listor börjar du en linje med `1.` eller `1)`men använder inte båda formaten i samma lista. Du behöver inte ange siffrorna. GitHub gör det åt dig.

```markdown
1. This is step 1.
1. This is the next step.
1. This is yet another step, the third.
```

Visas:

1. Detta är steg 1.
1. Detta är nästa steg.
1. Detta är ännu ett steg, det tredje.

<!-- markdownlint-disable MD037 -->
Om du vill skapa punktlistor börjar du en rad med \* eller - eller +, men blandar inte formaten i samma lista. (Blanda inte punktformat som \* och \+ i samma dokument.)
<!-- markdownlint-disable MD037 -->

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

* GitHub&#39;s [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)
* Webbprogrammet [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)
* [Konvertera HTML-tabeller till markering](https://jmalarcon.github.io/markdowntables/)

### Länkar

Markeringssyntaxen för en infogad länk består av `[link text]` delen, som är den text som ska hyperlänkas, följt av `(file-name.md)` delen, som är den URL eller det filnamn som länkas till:

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

Mer information om länkning finns i artikeln [Länkar](linking.md) i den här guiden för att länka syntax.

### Bilder

```markdown
![Adobe Logo](assets/no-localize/adobe_standard_logo.png "Hover text")
```

Visas:

![Adobe](assets/no-localize/adobe_standard_logo.png "LogoHover-text")

### Kodblock

Markdown stöder placeringen av kodblock både textbundet i en mening och som ett separat&quot;fenced&quot;-block mellan meningar. Mer information finns i [Markeringens inbyggda stöd för kodblock](https://daringfireball.net/projects/markdown/syntax#precode)

Använd bakåtmarkeringar ( \`) för att skapa textbundna kodformat i ett stycke. Om du vill skapa ett specifikt flerradigt kodblock lägger du till tre bakåtfästingar (\`\`\`) före och efter kodblocket (kallas &quot;fenced code block&quot; i Markdown och bara en &quot;code block&quot;-komponent i AEM). För avgränsade kodblock lägger du till kodspråket efter den första uppsättningen bakåtfästingar så att Markdown markerar kodsyntaxen korrekt. Exempel: \`\`\`javascript

Exempel:

```markdown
This is `inline code` within a paragraph of text.
```

Visas:

Detta är `inline code` inom ett textstycke.

Detta är ett avgränsat kodblock:

```markdown
\```javascript
function test() {
 console.log("notice the blank line before this function?");
\```
```

Visas:

```javascript
function test() {
 console.log("notice the blank line before this function?");
```

### Definitionslistor

En definitionslista är ett markeringstillägg som har stöd för definitionslistekomponenten i AEM. En definitionslista består av en term och dess definition.

<!--

```markdown
Frog
: An amphibious green creature. Likes flies.

Cat
: A less amphibious creature than frogs.
```

Displayed:

Frog
: An amphibious green creature. Likes flies.

Cat
: A less amphibious creature than frogs.
--->

#### Anmärkningar och kommentarer

Kommentarer (kommentarer) visas inte i de offentliga hjälpartiklarna. Kommentarer visas emellertid i de offentliga Markdown-filerna som användarna kan visa och redigera.

## Anpassade markeringstillägg

I Adobe-artiklar används standardmarkering för de flesta artikelformat, som stycken, länkar, listor och rubriker. För mer omfattande formatering kan artiklar använda utökade markeringsfunktioner som:

* Anteckningsblock
* Inbäddade videoklipp
* Lokalisera inte
* Komponentegenskaper, som att tilldela ett annat rubrik-ID till en rubrik

Använd markeringsblockcitattecken ( > ) i början av varje rad för att knyta samman en utökad komponent, t.ex. en anteckning. Om du behöver använda underkomponenter i komponenter lägger du till en extra nivå med blockcitattecken (> >) för det underkomponentavsnittet. En NOTE i ett DONOTLOCALIZE-avsnitt ska till exempel börja med > >.

Vissa vanliga markeringselement som rubriker och kodblock innehåller utökade egenskaper. Om du behöver ändra standardegenskaperna lägger du till parametrarna inom franska klammerparenteser /{ /} efter komponenten. Utökade egenskaper beskrivs i sitt sammanhang.

### Anteckningsblock

Du kan välja mellan fyra typer av anteckningsblock för att dra uppmärksamheten till specifikt innehåll:

* `[!NOTE]`
* `[!CAUTION]`
* `[!TIP]`
* `[!IMPORTANT]`

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
>[!VIDEO](https://www.youtube.com/watch?v=A0EcD2AxvJE)
```

Visas:

>[!VIDEO](https://www.youtube.com/watch?v=A0EcD2AxvJE)

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


### DNL - lokalisera inte - och UICONTROL

I vissa fall måste vi flagga vissa avsnitt av innehållet i en artikel som enbart ska vara engelska.
Ord, fraser och andra element måste deklareras till våra översättningssystem och skapar en möjlighet att hantera en kontrollerad lexikon.

För ord och fraser som inte ska lokaliseras använder du tillägget för att radbryta ordet eller avsnittet. `[!DNL]`

För element i användargränssnittet och menyer i en lösning använder vi `` tillägget.

**Exempel:**

I [!DNL Adobe Target] kan du skapa testerna direkt på en [!DNL Target]aktiverad sida.

**Källa:**

```markdown
In [!DNL Adobe Target] you can create your tests directly on a [!DNL Target]-enabled page.
```

**Exempel**

Använd [!UICONTROL Visual Experience Composer] ikonen i [!DNL Target] för att skapa ett test direkt på en sida.

**Källa:**

```markdown
Use the [!UICONTROL Visual Experience Composer] in [!DNL Target] to create your test directly on a page.
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

Koda `<script name>` som `&lt;script name&gt;`

### Förtexter

et-tecken (&amp;) tillåts inte i titlar. Använd&quot;och&quot; i stället, eller använd `&amp;` kodningen.

## Se även

### Markeringsresurser

* [Introduktion till markering](https://daringfireball.net/projects/markdown/syntax)
* [GitHub&#39;s Markdown Basics](https://help.github.com/articles/markdown-basics/)
