---
lastModified: 2018-06-28T00:00:00Z
title: Använda länkar i dokumentation
seo-title: Använda länkar i Adobe Git/Markdown-dokumentation
description: I den här artikeln finns anvisningar om hur du skapar länkar till innehåll och bilder.
seo-description: I den här artikeln finns anvisningar om hur du skapar länkar till innehåll och bilder för Adobe-dokumentation.
translation-type: tm+mt
source-git-commit: 73ec3b8b63769a192ee16bec2720930ea6a9aaed
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Använda länkar i dokumentation

I den här artikeln beskrivs användningen av hyperlänkar på dokumentationssidor. Länkar är enkla att lägga till i markeringar med några olika konventioner. Länkar pekar användare mot innehåll på samma sida, pekar ut mot andra angränsande sidor eller pekar på externa webbplatser och URL:er.

>[!IMPORTANT]
>Alla länkar bör helst vara säkra länkar (`https` kontra `http`) när målet stöder det (vilket de flesta bör göra).

## Länka till URL-adresser

Orden som du inkluderar i länktexten ska vara titeln på sidan som du länkar till eller en viss, beskrivande text.

**Exempel:**

- `For more information, see the [overview article](https://github.com/AdobeDocs/target.en/help/overview.md).`

- `For more details, see [Adobe Legal Concerns](https://www.adobe.com/legal).`

## Länka från en artikel till en annan

Använd följande länksyntax för att skapa en textbunden länk från en artikel till en annan artikel i samma databas:

- En artikel i en katalog länkar till en annan artikel i samma katalog:

   `[link text](article-name.md)`

- En artikel länkar från en underkatalog till en artikel i rotkatalogen:

   `[link text](../article-name.md)`

- En artikel länkar från en underkatalog till en artikel i rotkatalogen:

   `[link text](../../article-name.md)`

- En artikel i rotkatalogen länkar till en artikel i en underkatalog:

   `[link text](./directory/article-name.md)`

- En artikel i en underkatalog länkar till en artikel i en annan underkatalog:

   `[link text](../directory/article-name.md)`

- En artikel i en underkatalog länkar till en artikel i en annan underkatalog:

   `[link text](../../directory/article-name.md)`

## Länka till ankarpunkter

Du behöver inte skapa ankare. De genereras automatiskt vid publicering för alla H2-rubriker. Det enda du behöver göra är att skapa länkar till H2-avsnitten (##).

- Så här länkar du till en rubrik i samma artikel:

   `[link](#the-text-of-the-level2-section-separated-by-hyphens)`

   `[Link to anchors](#links-to-anchors)`

- Så här länkar du till en ankarpunkt i en annan artikel i samma underkatalog:

   `[link text](article-name.md#anchor-name)`

   `[Configure your profile](overview.md#getting-started)`

- Så här länkar du till ett ankare i en annan tjänstunderkatalog:

   `[link text](../directory/article-name.md#anchor-name)`

   `[Configure your profile](../overview.md#configure-your-profile)`

## Länka till bilder

Ett tips är att bilder och filer lagras i en `assets` katalog på samma nivå som den markeringsfil som länkar till den.

- En artikel länkar till en bild i `assets` underkatalogen:

   `![alt text](assets/image-name.png)`

- En artikel länkar till en bild i `assets/no-localize` underkatalogen:

   `![alt text](assets/no-localize/image-name.png)`

<!--
## Bob's link test

<table id="table_C27955F6B52A45B28BEEAAF14FFC86D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="filepath"> .csv </span> </p> </td> 
   <td colname="col2"> <p>A comma-separated values file (such as one created in Excel). This is the file that contains the customer attribute data. See [Link TEST](/help/setup/full-workflow.md) </p> <p> <b>Naming requirements:</b> Ensure that file name extensions do not contain white spaces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="filepath"> .fin </span> </p> </td> 
   <td colname="col2"> <p>(Required) The <span class="filepath"> .fin </span> file tells the system that you are finished uploading data. The name of the <span class="filepath"> .fin </span> file must match the name of the <span class="filepath"> .csv </span> file. </p> <p>Adobe recommends creating an empty text file with a <span class="filepath"> .fin </span> extension. An empty file saves space and upload time. </p> <p> <p>Note:  Renaming a <span class="filepath"> .fin </span> file is not allowed after it is uploaded. The <span class="filepath"> .fin </span> file must be uploaded separately and cannot be a renamed, previously uploaded file. </p> </p> <p>After you upload the <span class="filepath"> .fin </span> file in the customer attributes FTP, the system retrieves data quickly (within one minute). This differs from other Adobe FTP-based systems, which pick up data less frequently (around once per hour). </p> <p>The <span class="filepath"> .fin </span> file is not required when using the drag-and-drop upload method. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="filepath"> .gz </span> or <span class="filepath"> .zip </span> </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> .gz </span> (gzip) or <span class="filepath"> .zip </span> - for compressed files. A <span class="filepath"> .zip </span> file cannot contain more than one file in the archive. </p> <p> <b>Naming requirements:</b> The name of the <span class="filepath"> .zip </span> or <span class="filepath"> .gz </span> should match the name of the <span class="filepath"> .csv </span>. For example, if your <span class="filepath"> .csv </span> file is <span class="filepath"> crm_small.csv </span>, the <span class="filepath"> .zip </span> file should be <span class="filepath"> crm_small.csv.zip </span>. </p> <p>The .fin file must match the .csv. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->
