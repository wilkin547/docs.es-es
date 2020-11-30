---
title: Jerarquía del Modelo de objetos de documento XML (DOM)
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 24ef51a18392fe3034e64bd585d879941fca4b95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718363"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="fd175-102">Jerarquía del Modelo de objetos de documento XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="fd175-102">XML Document Object Model (DOM) Hierarchy</span></span>

<span data-ttu-id="fd175-103">En la ilustración siguiente se muestra la jerarquía de clases para DOM, con el nombre del W3C entre paréntesis y el nombre de la clase cuando sea relevante.</span><span class="sxs-lookup"><span data-stu-id="fd175-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="fd175-104">![Jerarquía del Modelo de objetos de documento &#40;DOM&#41; de XML](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="fd175-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="fd175-105">Jerarquía del Modelo de objetos de documento XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="fd175-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="fd175-106">Las siguientes clases no heredan de la clase **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="fd175-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="fd175-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="fd175-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="fd175-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="fd175-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="fd175-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="fd175-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="fd175-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="fd175-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="fd175-111">La clase **XmlImplementation** se utiliza para crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="fd175-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="fd175-112">Para obtener más información, vea [Creación de documentos XML](xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="fd175-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="fd175-113">La clase **XmlNamedNodeMap** controla un conjunto de nodos desordenados.</span><span class="sxs-lookup"><span data-stu-id="fd175-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="fd175-114">Para obtener más información, vea [Recuperación de nodos desordenados por nombre o índice](unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="fd175-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="fd175-115">La clase **XmlNodeList** controla una lista de nodos ordenados.</span><span class="sxs-lookup"><span data-stu-id="fd175-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="fd175-116">Para obtener más información, vea [Recuperación de nodos ordenados por índice](ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="fd175-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="fd175-117">La clase **XmlNodeChangedEventArgs** controla controladores de eventos registrados en **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="fd175-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="fd175-118">Para obtener más información, vea [Controlar eventos en un documento XML mediante XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="fd175-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="fd175-119">La clase **XmlLinkedNode** hereda de la clase **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="fd175-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="fd175-120">Su objetivo es invalidar dos métodos desde **XmlNode**: los métodos **PreviousSibling** y **NextSibling**.</span><span class="sxs-lookup"><span data-stu-id="fd175-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="fd175-121">Estos métodos invalidados los heredan y utilizan las clases **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** y **XmlProcessingInstruction**, que tienen nodos relacionados anteriores y siguientes.</span><span class="sxs-lookup"><span data-stu-id="fd175-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd175-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd175-122">See also</span></span>

- [<span data-ttu-id="fd175-123">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="fd175-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
