---
title: Generar clases de tipos de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: c1b5dfda8aa5370dbc202ab90c75ab5677970467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929576"
---
# <a name="generating-data-type-classes-from-xml"></a>Generar clases de tipos de datos a partir de XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] incluye una nueva característica para generar clases de tipo de datos de XML. Este tema describe cómo generar automáticamente los tipos de datos para la fuente RSS de blogs. NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Obtener XML desde el RSS del Blog de .NET de fuente  
  
1. En Internet Explorer, vaya a la [fuente de RSS del Blog .NET](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Haga clic en la página y seleccione **ver código fuente**.  
  
3. Copie el texto de la fuente presionando **CTRL+a** para seleccionar todo el texto, y **Ctrl + C** para copiar.  
  
### <a name="creating-the-data-types"></a>Crear los tipos de datos  
  
1. Abra un archivo de código donde se vaya a usar el proxy. Este archivo debe formar parte de un proyecto de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  
  
2. Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.  
  
3. Seleccione **editar**, **Pegado especial**, **pegar XML como clases**.  
  
4. Las clases denominadas `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.  
  
### <a name="using-the-generated-classes"></a>Usar las clases generadas  
  
1. Una vez que se generan las clases, se pueden usar en código como cualquier otra clase. En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
