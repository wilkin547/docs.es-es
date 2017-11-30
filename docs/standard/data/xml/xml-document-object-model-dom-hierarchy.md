---
title: "Jerarquía del Modelo de objetos de documento XML (DOM)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="16f9b-102">Jerarquía del Modelo de objetos de documento XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="16f9b-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="16f9b-103">En la ilustración siguiente se muestra la jerarquía de clases para DOM, con el nombre del W3C entre paréntesis y el nombre de la clase cuando sea relevante.</span><span class="sxs-lookup"><span data-stu-id="16f9b-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="16f9b-104">![Modelo de objetos de documento XML &#40; DOM &#41; jerarquía](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="16f9b-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="16f9b-105">Jerarquía del Modelo de objetos de documento XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="16f9b-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="16f9b-106">Las siguientes clases no heredan de la **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="16f9b-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="16f9b-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="16f9b-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="16f9b-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="16f9b-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="16f9b-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="16f9b-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="16f9b-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="16f9b-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="16f9b-111">El **XmlImplementation** clase se utiliza para crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="16f9b-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="16f9b-112">Para obtener más información, consulte [creación de documentos XML](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="16f9b-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="16f9b-113">El **XmlNamedNodeMap** clase controla un conjunto de nodos desordenados.</span><span class="sxs-lookup"><span data-stu-id="16f9b-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="16f9b-114">Para obtener más información, consulte [recuperación de nodos desordenados por nombre o índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="16f9b-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="16f9b-115">El **XmlNodeList** clase administra una lista ordenada de nodos.</span><span class="sxs-lookup"><span data-stu-id="16f9b-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="16f9b-116">Para obtener más información, consulte [recuperación de nodos ordenados por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="16f9b-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="16f9b-117">El **XmlNodeChangedEventArgs** clase controla controladores de eventos registrados en el **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="16f9b-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="16f9b-118">Para obtener más información, consulte [control de eventos en un documento XML mediante XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="16f9b-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="16f9b-119">El **XmlLinkedNode** clase hereda de **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="16f9b-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="16f9b-120">Su objetivo es invalidar dos métodos de **XmlNode**: el **PreviousSibling** y **NextSibling** métodos.</span><span class="sxs-lookup"><span data-stu-id="16f9b-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="16f9b-121">Estos métodos invalidados, a continuación, se heredan y utilizan **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, y **XmlProcessingInstruction**, que son clases que tienen nodos relacionados anteriores y siguientes.</span><span class="sxs-lookup"><span data-stu-id="16f9b-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f9b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="16f9b-122">See Also</span></span>  
 [<span data-ttu-id="16f9b-123">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="16f9b-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
