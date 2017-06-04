---
title: "Jerarqu&#237;a del Modelo de objetos de documento XML (DOM) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Jerarqu&#237;a del Modelo de objetos de documento XML (DOM)
En la ilustración siguiente se muestra la jerarquía de clases para DOM, con el nombre del W3C entre paréntesis y el nombre de la clase cuando sea relevante.  
  
 ![Jerarquía del Modelo de objetos de documento XML &#40;DOM&#41;](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom\_class\_hierarchy")  
Jerarquía del Modelo de objetos de documento XML \(DOM\)  
  
 Las siguientes clases no heredan de la clase **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 La clase **XmlImplementation** se utiliza para crear un documento XML.  Para obtener más información, vea [Creación de documentos XML](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 La clase **XmlNamedNodeMap** controla un conjunto de nodos desordenados.  Para obtener más información, vea [Recuperación de nodos desordenados por nombre o índice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 La clase **XmlNodeList** controla una lista de nodos ordenados.  Para obtener más información, vea [Recuperación de nodos ordenados por índice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 La clase **XmlNodeChangedEventArgs** controla controladores de eventos registrados en **XmlDocument**.  Para obtener más información, vea [Controlar eventos en un documento XML mediante XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 La clase **XmlLinkedNode** hereda de la clase **XmlNode**.  Su objetivo es invalidar dos métodos desde **XMLNode**: los métodos **NextSibling** y **PreviousSibling**.  Estos métodos invalidados los heredan y utilizan las clases **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, y **XmlProcessingInstruction**, que tienen nodos relacionados anteriores y siguientes.  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)