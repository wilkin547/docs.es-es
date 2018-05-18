---
title: Jerarquía del Modelo de objetos de documento XML (DOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5b4ca249928200ddfc9dcd133ac673261046fb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Jerarquía del Modelo de objetos de documento XML (DOM)
En la ilustración siguiente se muestra la jerarquía de clases para DOM, con el nombre del W3C entre paréntesis y el nombre de la clase cuando sea relevante.  
  
 ![Jerarquía de Document Object Model XML (DOM)](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Jerarquía del Modelo de objetos de documento XML (DOM)  
  
 Las siguientes clases no heredan de la clase **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 La clase **XmlImplementation** se utiliza para crear un documento XML. Para obtener más información, vea [Creación de documentos XML](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 La clase **XmlNamedNodeMap** controla un conjunto de nodos desordenados. Para obtener más información, vea [Recuperación de nodos desordenados por nombre o índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 La clase **XmlNodeList** controla una lista de nodos ordenados. Para obtener más información, vea [Recuperación de nodos ordenados por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 La clase **XmlNodeChangedEventArgs** controla controladores de eventos registrados en **XmlDocument**. Para obtener más información, vea [Controlar eventos en un documento XML mediante XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 La clase **XmlLinkedNode** hereda de la clase **XmlNode**. Su objetivo es invalidar dos métodos desde **XmlNode**: los métodos **PreviousSibling** y **NextSibling**. Estos métodos invalidados los heredan y utilizan las clases **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** y **XmlProcessingInstruction**, que tienen nodos relacionados anteriores y siguientes.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
