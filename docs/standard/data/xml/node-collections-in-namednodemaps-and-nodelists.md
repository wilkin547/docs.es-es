---
title: Colecciones de nodos en NamedNodeMaps y NodeLists
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff327c1a450e9ce712d496bdca2cd2ebbff6adda
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="f9689-102">Colecciones de nodos en NamedNodeMaps y NodeLists</span><span class="sxs-lookup"><span data-stu-id="f9689-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="f9689-103">Se puede recuperar un conjunto de nodos y colocarlo en una colección ordenada o desordenada.</span><span class="sxs-lookup"><span data-stu-id="f9689-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="f9689-104">Si se coloca un conjunto de nodos en una colección desordenada, el W3C (World Wide Web Consortium) denomina al conjunto NamedNodeMap; en este tipo de colección puede recuperar los datos por nombre o por índice.</span><span class="sxs-lookup"><span data-stu-id="f9689-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="f9689-105">Si se coloca un conjunto de nodos en una colección ordenada, el W3C denomina al conjunto NodeList y los datos pueden recuperarse mediante un índice que empieza por cero.</span><span class="sxs-lookup"><span data-stu-id="f9689-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="f9689-106">El W3C describe ambos conjuntos, NamedNodeMaps y NodeLists.</span><span class="sxs-lookup"><span data-stu-id="f9689-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="f9689-107">La implementación en Microsoft .NET Framework de NamedNodeMap es **XmlNamedNodeMap** mientras que **XmlNodeList** implementa NodeList.</span><span class="sxs-lookup"><span data-stu-id="f9689-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="f9689-108">Para obtener información sobre la colección desordenada, vea [Recuperación de nodos desordenados por nombre o índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="f9689-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="f9689-109">Para obtener información sobre la colección ordenada, vea [Recuperación de nodos ordenados por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="f9689-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9689-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9689-110">See Also</span></span>  
 [<span data-ttu-id="f9689-111">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="f9689-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
