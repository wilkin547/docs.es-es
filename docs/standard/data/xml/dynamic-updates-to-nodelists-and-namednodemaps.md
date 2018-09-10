---
title: Actualizaciones dinámicas en NodeLists y NamedNodeMaps
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f56ba8711988f2f7d743dc4ff7b69272e2642a2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207413"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="390a1-102">Actualizaciones dinámicas en NodeLists y NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="390a1-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="390a1-103">Puesto que **XmlNodeList** y **XmlNamedNodeMap** contienen un conjunto de nodos, el documento XML se carga en la memoria y se modifica, el World Wide Web Consortium (W3C) establece que es necesario que estos objetos que contienen conjuntos de nodos sean dinámicos.</span><span class="sxs-lookup"><span data-stu-id="390a1-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="390a1-104">Es decir, si el documento subyacente cambia, deberían cambiar también los datos incluidos en estos dos objetos.</span><span class="sxs-lookup"><span data-stu-id="390a1-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="390a1-105">Por lo tanto, si tiene una clase **XmlNodeList** que contiene todos los elementos secundarios de un elemento en particular (por ejemplo, elemento X), entonces añade un elemento adicional, elemento Q, al documento bajo el elemento X. La clase **XmlNodeList** debería tener el nuevo elemento Q añadido a esta colección.</span><span class="sxs-lookup"><span data-stu-id="390a1-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="390a1-106">Lo mismo sucede a la inversa.</span><span class="sxs-lookup"><span data-stu-id="390a1-106">The same is true in reverse.</span></span> <span data-ttu-id="390a1-107">Si se agrega un nodo a **XmlNodeList**, el documento subyacente también se actualiza.</span><span class="sxs-lookup"><span data-stu-id="390a1-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390a1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="390a1-108">See also</span></span>

- [<span data-ttu-id="390a1-109">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="390a1-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
