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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a7abbb7344530ca993b8d07b774da17e6d0349b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="2fe5b-102">Actualizaciones dinámicas en NodeLists y NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="2fe5b-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="2fe5b-103">Puesto que **XmlNodeList** y **XmlNamedNodeMap** contienen un conjunto de nodos, el documento XML se carga en la memoria y se modifica, el World Wide Web Consortium (W3C) establece que es necesario que estos objetos que contienen conjuntos de nodos sean dinámicos.</span><span class="sxs-lookup"><span data-stu-id="2fe5b-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="2fe5b-104">Es decir, si el documento subyacente cambia, deberían cambiar también los datos incluidos en estos dos objetos.</span><span class="sxs-lookup"><span data-stu-id="2fe5b-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="2fe5b-105">Por lo tanto, si tiene una clase **XmlNodeList** que contiene todos los elementos secundarios de un elemento en particular (por ejemplo, elemento X), entonces añade un elemento adicional, elemento Q, al documento bajo el elemento X. La clase **XmlNodeList** debería tener el nuevo elemento Q añadido a esta colección.</span><span class="sxs-lookup"><span data-stu-id="2fe5b-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="2fe5b-106">Lo mismo sucede a la inversa.</span><span class="sxs-lookup"><span data-stu-id="2fe5b-106">The same is true in reverse.</span></span> <span data-ttu-id="2fe5b-107">Si se agrega un nodo a **XmlNodeList**, el documento subyacente también se actualiza.</span><span class="sxs-lookup"><span data-stu-id="2fe5b-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe5b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fe5b-108">See Also</span></span>  
 [<span data-ttu-id="2fe5b-109">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="2fe5b-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
