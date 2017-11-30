---
title: "Actualizaciones dinámicas en NodeLists y NamedNodeMaps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="e1958-102">Actualizaciones dinámicas en NodeLists y NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="e1958-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="e1958-103">Dado que la **XmlNodeList** y **XmlNamedNodeMap** contienen un conjunto de nodos, aunque el documento XML se carga en memoria y se modifica, World Wide Web Consortium (W3C) indica que estos objetos que contienen los conjuntos de nodos deben ser dinámicos.</span><span class="sxs-lookup"><span data-stu-id="e1958-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="e1958-104">Es decir, si el documento subyacente cambia, deberían cambiar también los datos incluidos en estos dos objetos.</span><span class="sxs-lookup"><span data-stu-id="e1958-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="e1958-105">Por lo tanto, si tiene una **XmlNodeList** que contiene todos los elementos secundarios de un elemento determinado (por ejemplo, elemento X), a continuación, agregue un elemento adicional, elemento Q, al documento bajo el elemento X. El **XmlNodeList** también debe tener el nuevo elemento Q añadido a esta colección.</span><span class="sxs-lookup"><span data-stu-id="e1958-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="e1958-106">Lo mismo sucede a la inversa.</span><span class="sxs-lookup"><span data-stu-id="e1958-106">The same is true in reverse.</span></span> <span data-ttu-id="e1958-107">Si se agrega un nodo a la **XmlNodeList**, el documento subyacente también se actualiza.</span><span class="sxs-lookup"><span data-stu-id="e1958-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1958-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1958-108">See Also</span></span>  
 [<span data-ttu-id="e1958-109">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="e1958-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
