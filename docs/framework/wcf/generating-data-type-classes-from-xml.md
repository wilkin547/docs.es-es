---
title: Generar clases de tipos de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: b99bb40105398dbd91b910c4a19828d069c3d9e7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380218"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="83b57-102">Generar clases de tipos de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="83b57-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="83b57-103">.NET framework 4.5 se incluye una nueva característica para generar clases de tipos de datos a partir de XML.</span><span class="sxs-lookup"><span data-stu-id="83b57-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="83b57-104">Este tema describe cómo generar automáticamente los tipos de datos para la fuente RSS de blogs. NET.</span><span class="sxs-lookup"><span data-stu-id="83b57-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="83b57-105">Obtener XML desde el RSS del Blog de .NET de fuente</span><span class="sxs-lookup"><span data-stu-id="83b57-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="83b57-106">En Internet Explorer, vaya a la [fuente de RSS del Blog .NET](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="83b57-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="83b57-107">Haga clic en la página y seleccione **ver código fuente**.</span><span class="sxs-lookup"><span data-stu-id="83b57-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="83b57-108">Copie el texto de la fuente presionando **CTRL+a** para seleccionar todo el texto, y **Ctrl + C** para copiar.</span><span class="sxs-lookup"><span data-stu-id="83b57-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="83b57-109">Crear los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="83b57-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="83b57-110">Abra un archivo de código donde se vaya a usar el proxy.</span><span class="sxs-lookup"><span data-stu-id="83b57-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="83b57-111">Este archivo debe formar parte de un proyecto de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="83b57-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="83b57-112">Coloque el cursor en una ubicación en el archivo fuera de las clases existentes.</span><span class="sxs-lookup"><span data-stu-id="83b57-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="83b57-113">Seleccione **editar**, **Pegado especial**, **pegar XML como clases**.</span><span class="sxs-lookup"><span data-stu-id="83b57-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="83b57-114">Las clases denominadas `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` y `rssChannelItemGuid` se crean con los miembros necesarios para tener acceso a los elementos de la fuente RSS.</span><span class="sxs-lookup"><span data-stu-id="83b57-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="83b57-115">Usar las clases generadas</span><span class="sxs-lookup"><span data-stu-id="83b57-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="83b57-116">Una vez que se generan las clases, se pueden usar en código como cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="83b57-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="83b57-117">En el siguiente ejemplo de código se devuelve una nueva instancia de la clase `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="83b57-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
