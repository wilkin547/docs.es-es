---
title: "Generar clases de tipos de datos a partir de XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Generar clases de tipos de datos a partir de XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] incluye una nueva característica para generar clases de tipo de datos de XML.  Este tema describe cómo generar automáticamente tipos de datos para la fuente RSS de MSDN Library.  
  
### Obtener XML desde la fuente RSS de MSDN Library  
  
1.  En Internet Explorer, vaya a la [fuente RSS de MSDN](http://go.microsoft.com/fwlink/?LinkId=225209).  
  
2.  Haga clic con el botón secundario en la página y seleccione **Ver código fuente**.  
  
3.  Copie el texto de la fuente presionando **Ctrl\+A** para seleccionar todo el texto y **Ctrl\+C** para copiar.  
  
### Crear los tipos de datos  
  
1.  Abra un archivo de código donde se vaya a usar el proxy.  Este archivo debe formar parte de un proyecto de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  
  
2.  Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.  
  
3.  Seleccione **Edición**, **Pegado especial**, **Pegar XML como clases**.  
  
4.  Las clases denominadas `rss`, `rssChannel`, `rssChannelImage` y `rssChannelItem` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.  
  
### Usar las clases generadas  
  
1.  Una vez que se generan las clases, se pueden usar en código como cualquier otra clase.  En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
  
    ```