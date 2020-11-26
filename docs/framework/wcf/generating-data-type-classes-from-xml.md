---
title: Generar clases de tipos de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: a7920a8c8c4f279dd3fc52029c5da5e9b685efe2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238254"
---
# <a name="generating-data-type-classes-from-xml"></a>Generar clases de tipos de datos a partir de XML

.NET Framework 4,5 incluye una nueva característica para generar clases de tipos de datos a partir de XML. En este tema se describe cómo generar automáticamente tipos de datos para la fuente RSS del blog de .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Obtener el XML de la fuente RSS del blog de .NET  
  
1. En Internet Explorer, vaya a la [fuente RSS del blog de .net](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Haga clic con el botón secundario en la página y seleccione **Ver código fuente**.  
  
3. Copie el texto de la fuente presionando **Ctrl +** a para seleccionar todo el texto y **Ctrl + C** para copiar.  
  
### <a name="creating-the-data-types"></a>Crear los tipos de datos  
  
1. Abra un archivo de código donde se vaya a usar el proxy. Este archivo debe formar parte de un proyecto .NET Framework 4,5.  
  
2. Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.  
  
3. Seleccione **Editar**, **Pegar especial** y **pegar XML como clases**.  
  
4. Las clases denominadas `link` , `rss` , `rssChannel` , `rssChannelImage` `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.  
  
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
