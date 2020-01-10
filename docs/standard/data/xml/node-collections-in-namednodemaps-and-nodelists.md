---
title: Colecciones de nodos en NamedNodeMaps y NodeLists
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
ms.openlocfilehash: 6af51d993f8328b4e5d1abb05fcc4b06daa53d7b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710588"
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="063eb-102">Colecciones de nodos en NamedNodeMaps y NodeLists</span><span class="sxs-lookup"><span data-stu-id="063eb-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="063eb-103">Se puede recuperar un conjunto de nodos y colocarlo en una colección ordenada o desordenada.</span><span class="sxs-lookup"><span data-stu-id="063eb-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="063eb-104">Si se coloca un conjunto de nodos en una colección desordenada, el W3C (World Wide Web Consortium) denomina al conjunto NamedNodeMap; en este tipo de colección puede recuperar los datos por nombre o por índice.</span><span class="sxs-lookup"><span data-stu-id="063eb-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="063eb-105">Si se coloca un conjunto de nodos en una colección ordenada, el W3C denomina al conjunto NodeList y los datos pueden recuperarse mediante un índice que empieza por cero.</span><span class="sxs-lookup"><span data-stu-id="063eb-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="063eb-106">El W3C describe ambos conjuntos, NamedNodeMaps y NodeLists.</span><span class="sxs-lookup"><span data-stu-id="063eb-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="063eb-107">La implementación en Microsoft .NET Framework de NamedNodeMap es **XmlNamedNodeMap** mientras que **XmlNodeList** implementa NodeList.</span><span class="sxs-lookup"><span data-stu-id="063eb-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="063eb-108">Para obtener información sobre la colección desordenada, vea [Recuperación de nodos desordenados por nombre o índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="063eb-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="063eb-109">Para obtener información sobre la colección ordenada, vea [Recuperación de nodos ordenados por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="063eb-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063eb-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="063eb-110">See also</span></span>

- [<span data-ttu-id="063eb-111">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="063eb-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
