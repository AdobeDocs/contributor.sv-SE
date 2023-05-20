---
lastModified: 2018-06-28T00:00:00Z
title: Använda länkar i dokumentation
seo-title: Using links in Adobe Git/Markdown documentation
description: I den här artikeln finns anvisningar om hur du skapar länkar till innehåll och bilder.
seo-description: This article provides guidance on creating links to content and images for Adobe documentation.
exl-id: f9d61aa9-931c-4654-ab21-c6e47936954e
source-git-commit: dad1df81797e6078645449501ed0661cf4bcf3ce
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Använda länkar i dokumentation

I den här artikeln beskrivs användningen av hyperlänkar på dokumentationssidor. Länkar är enkla att lägga till i markeringar med några olika konventioner. Länkar pekar användare mot innehåll på samma sida, pekar ut mot andra angränsande sidor eller pekar på externa webbplatser och URL:er.

>[!IMPORTANT]
>Alla länkar bör helst vara säkra länkar (`https` vs `http`) när målet stöder det (vilket den övervägande majoriteten bör).

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

Ett tips är att bilder och filer lagras i en `assets` på samma nivå som markeringsfilen som länkar till den.

- En artikel länkar till en bild i `assets` underkatalog:

   `![alt text](assets/image-name.png)`

- En artikel länkar till en bild i `assets/no-localize` underkatalog:

   `![alt text](assets/no-localize/image-name.png)`
