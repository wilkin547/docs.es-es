---
title: Generar clases de tipos de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184132"
---
# <a name="generating-data-type-classes-from-xml"></a>Generar clases de tipos de datos a partir de XML
.NET Framework 4.5 incluye una nueva característica para generar clases de tipo de datos a partir de XML. En este tema se describe cómo generar automáticamente tipos de datos para la fuente RSS del blog de .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Obtención del XML de la fuente RSS del blog de .NET  
  
1. En Internet Explorer, vaya a la [fuente RSS del blog de .NET.](https://devblogs.microsoft.com/dotnet/feed/)  
  
2. Haga clic con el botón derecho en la página y seleccione **Ver origen**.  
  
3. Copie el texto de la fuente presionando **Ctrl+A** para seleccionar todo el texto y **Ctrl+C** para copiar.  
  
### <a name="creating-the-data-types"></a>Crear los tipos de datos  
  
1. Abra un archivo de código donde se vaya a usar el proxy. Este archivo debe formar parte de un proyecto de .NET Framework 4.5.  
  
2. Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.  
  
3. Seleccione **Editar**, **Pegado especial**, Pegar XML como **clases**.  
  
4. Las `link`clases denominadas `rss`, , `rssChannel`, `rssChannelImage`, `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.  
  
### <a name="using-the-generated-classes"></a>Usar las clases generadas  
  
1. Una vez que se generan las clases, se pueden usar en código como cualquier otra clase. En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
