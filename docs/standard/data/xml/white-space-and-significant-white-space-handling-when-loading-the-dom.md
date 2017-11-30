---
title: Control de espacios en blanco y de espacios en blanco significativos al cargar DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="930bd-102">Control de espacios en blanco y de espacios en blanco significativos al cargar DOM</span><span class="sxs-lookup"><span data-stu-id="930bd-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="930bd-103">Al cargar el documento, puede establecer la opción de conservar los espacios en blanco y crear **XmlWhitespace** nodos en el árbol del documento.</span><span class="sxs-lookup"><span data-stu-id="930bd-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="930bd-104">Para crear nodos de espacio en blanco, establezca la **PreserveWhitespace** propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="930bd-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="930bd-105">Si la propiedad se establece en **false**, que es el valor predeterminado, no se crean nodos de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="930bd-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="930bd-106">Siempre se conservan los nodos de espacios en blanco significativos y **XmlSignificantWhitespace** nodos siempre se crean en la memoria para representar estos datos, independientemente de la configuración de la **PreserveWhitespace** marca.</span><span class="sxs-lookup"><span data-stu-id="930bd-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="930bd-107">Si el documento se carga desde un lector, a continuación, configuración de la **PreserveWhitespace** marca de propiedad en el **XmlDocument** clase afecta a la creación de **XmlWhitespace** nodos solo cuando la **WhitespaceHandling** propiedad en el **XmlTextReader** no está establecido en **WhitespaceHandling.None**.</span><span class="sxs-lookup"><span data-stu-id="930bd-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="930bd-108">Es el valor de la **WhitespaceHandling** propiedad en el lector que tiene prioridad sobre la configuración de dicha marca en el **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="930bd-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="930bd-109">Para obtener más información sobre **XmlSignificantWhitespace**, consulte <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="930bd-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930bd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="930bd-110">See Also</span></span>  
 [<span data-ttu-id="930bd-111">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="930bd-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
