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
# <a name="xml-document-object-model-dom-hierarchy"></a>Jerarquía del Modelo de objetos de documento XML (DOM)
En la ilustración siguiente se muestra la jerarquía de clases para DOM, con el nombre del W3C entre paréntesis y el nombre de la clase cuando sea relevante.  
  
 ![Modelo de objetos de documento XML &#40; DOM &#41; jerarquía](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Jerarquía del Modelo de objetos de documento XML (DOM)  
  
 Las siguientes clases no heredan de la **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 El **XmlImplementation** clase se utiliza para crear un documento XML. Para obtener más información, consulte [creación de documentos XML](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 El **XmlNamedNodeMap** clase controla un conjunto de nodos desordenados. Para obtener más información, consulte [recuperación de nodos desordenados por nombre o índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 El **XmlNodeList** clase administra una lista ordenada de nodos. Para obtener más información, consulte [recuperación de nodos ordenados por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 El **XmlNodeChangedEventArgs** clase controla controladores de eventos registrados en el **XmlDocument**. Para obtener más información, consulte [control de eventos en un documento XML mediante XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 El **XmlLinkedNode** clase hereda de **XmlNode**. Su objetivo es invalidar dos métodos de **XmlNode**: el **PreviousSibling** y **NextSibling** métodos. Estos métodos invalidados, a continuación, se heredan y utilizan **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, y **XmlProcessingInstruction**, que son clases que tienen nodos relacionados anteriores y siguientes.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
