---
lastModified: 2018-06-28T00:00:00Z
title: Använda länkar i dokumentation
seo-title: Använda länkar i Adobe Git/Markdown-dokumentation
description: I den här artikeln finns anvisningar om hur du skapar länkar till innehåll och bilder.
seo-description: I den här artikeln finns anvisningar om hur du skapar länkar till innehåll och bilder för Adobe-dokumentation.
translation-type: tm+mt
source-git-commit: df6c4152df0c1ee87c9fc4ca22e36a3f13cb620b
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Använda länkar i dokumentation

I den här artikeln beskrivs användningen av hyperlänkar på dokumentationssidor. Länkar är enkla att lägga till i markeringar med några olika konventioner. Länkar pekar användare mot innehåll på samma sida, pekar ut mot andra angränsande sidor eller pekar på externa webbplatser och URL:er.

>[!IMPORTANT]
>Alla länkar bör helst vara säkra länkar (`https` vs `http`) när målet stöder det (vilket den allra största parten bör göra).

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

Ett tips är att bilder och filer lagras i en `assets`-katalog på samma nivå som den Markdown-fil som länkar till den.

- En artikel länkar till en bild i underkatalogen `assets`:

   `![alt text](assets/image-name.png)`

- En artikel länkar till en bild i underkatalogen `assets/no-localize`:

   `![alt text](assets/no-localize/image-name.png)`
