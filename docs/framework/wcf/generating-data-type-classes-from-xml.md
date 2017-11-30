---
title: Generar clases de tipos de datos a partir de XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0362673ebb7d686822fae594b3a41435ceb9a4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="ba87a-102">Generar clases de tipos de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="ba87a-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="ba87a-103"> incluye una nueva característica para generar clases de tipo de datos de XML.</span><span class="sxs-lookup"><span data-stu-id="ba87a-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="ba87a-104">Este tema describe cómo generar automáticamente tipos de datos para la fuente RSS de Blog. NET.</span><span class="sxs-lookup"><span data-stu-id="ba87a-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="ba87a-105">Obtener el XML de RSS del Blog de .NET de fuentes de distribución</span><span class="sxs-lookup"><span data-stu-id="ba87a-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="ba87a-106">En Internet Explorer, vaya a la [fuente RSS del Blog de .NET](https://blogs.msdn.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="ba87a-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="ba87a-107">Haga clic en la página y seleccione **ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="ba87a-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="ba87a-108">Copie el texto de la fuente presionando **CTRL+a** para seleccionar todo el texto, y **Ctrl + C** para copiar.</span><span class="sxs-lookup"><span data-stu-id="ba87a-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="ba87a-109">Crear los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="ba87a-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="ba87a-110">Abra un archivo de código donde se vaya a usar el proxy.</span><span class="sxs-lookup"><span data-stu-id="ba87a-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="ba87a-111">Este archivo debe formar parte de un proyecto de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba87a-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="ba87a-112">Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.</span><span class="sxs-lookup"><span data-stu-id="ba87a-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="ba87a-113">Seleccione **editar**, **Pegado especial**, **pegar XML como clases**.</span><span class="sxs-lookup"><span data-stu-id="ba87a-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="ba87a-114">Las clases denominadas `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.</span><span class="sxs-lookup"><span data-stu-id="ba87a-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="ba87a-115">Usar las clases generadas</span><span class="sxs-lookup"><span data-stu-id="ba87a-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="ba87a-116">Una vez que se generan las clases, se pueden usar en código como cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="ba87a-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="ba87a-117">En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="ba87a-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
