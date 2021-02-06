---
description: Más información acerca de cómo generar clases de tipos de datos a partir de XML
title: Generar clases de tipos de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: c79550b1e4804426267aef33860bc49d5d3b5efa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632144"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="6dac0-103">Generar clases de tipos de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="6dac0-103">Generating Data Type Classes from XML</span></span>

<span data-ttu-id="6dac0-104">.NET Framework 4,5 incluye una nueva característica para generar clases de tipos de datos a partir de XML.</span><span class="sxs-lookup"><span data-stu-id="6dac0-104">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="6dac0-105">En este tema se describe cómo generar automáticamente tipos de datos para la fuente RSS del blog de .NET.</span><span class="sxs-lookup"><span data-stu-id="6dac0-105">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="6dac0-106">Obtener el XML de la fuente RSS del blog de .NET</span><span class="sxs-lookup"><span data-stu-id="6dac0-106">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="6dac0-107">En Internet Explorer, vaya a la [fuente RSS del blog de .net](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="6dac0-107">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="6dac0-108">Haga clic con el botón secundario en la página y seleccione **Ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="6dac0-108">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="6dac0-109">Copie el texto de la fuente presionando **Ctrl +** a para seleccionar todo el texto y **Ctrl + C** para copiar.</span><span class="sxs-lookup"><span data-stu-id="6dac0-109">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="6dac0-110">Crear los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6dac0-110">Creating the data types</span></span>  
  
1. <span data-ttu-id="6dac0-111">Abra un archivo de código donde se vaya a usar el proxy.</span><span class="sxs-lookup"><span data-stu-id="6dac0-111">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="6dac0-112">Este archivo debe formar parte de un proyecto .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="6dac0-112">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="6dac0-113">Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.</span><span class="sxs-lookup"><span data-stu-id="6dac0-113">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="6dac0-114">Seleccione **Editar**, **Pegar especial** y **pegar XML como clases**.</span><span class="sxs-lookup"><span data-stu-id="6dac0-114">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="6dac0-115">Las clases denominadas `link` , `rss` , `rssChannel` , `rssChannelImage` `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.</span><span class="sxs-lookup"><span data-stu-id="6dac0-115">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="6dac0-116">Usar las clases generadas</span><span class="sxs-lookup"><span data-stu-id="6dac0-116">Using the generated classes</span></span>  
  
1. <span data-ttu-id="6dac0-117">Una vez que se generan las clases, se pueden usar en código como cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="6dac0-117">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="6dac0-118">En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="6dac0-118">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
