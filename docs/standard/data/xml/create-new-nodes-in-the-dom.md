---
title: "Creaci&#243;n de nuevos nodos en el DOM | Microsoft Docs"
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
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Creaci&#243;n de nuevos nodos en el DOM
El <xref:System.Xml.XmlDocument> tiene un método de creación para todos los tipos de nodos. Para crear el nodo, proporcione el método con un nombre cuando sea preciso, y el contenido y otros parámetros para aquellos nodos que tengan contenido (por ejemplo, los nodos de texto). Los siguientes métodos son los que necesitan que se proporcione un nombre y otros cuantos parámetros para crear un nodo apropiado.  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 Otros tipos de nodos tienen más requisitos aparte de que se proporcionen datos a los parámetros.  
  
 Para obtener información sobre atributos, vea [crear nuevos atributos para elementos en DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md). Para obtener información sobre la validación de nombre de elemento y atributo, vea [elemento XML y la comprobación de nombre de atributo al crear nuevos nodos](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md). Para crear referencias de entidad, vea [crear nuevas referencias de entidad](../../../../docs/standard/data/xml/creating-new-entity-references.md). Para obtener información sobre cómo afectan los espacios de nombres a la expansión de referencias de entidad, vea [Namespace efecto en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).  
  
 Una vez creados los nuevos nodos, hay disponibles varios métodos para insertarlos en el árbol. En la tabla se enumeran los métodos con una descripción de dónde aparece el nuevo nodo en el Modelo de objetos de documento (DOM).  
  
|Método|Colocación del nodo|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|Insertado antes del nodo de referencia. Por ejemplo, para insertar el nuevo nodo en la posición 5:<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> Para obtener más información, consulte el <xref:System.Xml.XmlNode.InsertBefore%2A> método.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|Insertado después del nodo de referencia. Por ejemplo:<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> Para obtener más información, consulte el <xref:System.Xml.XmlNode.InsertAfter%2A> método.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|Agrega el nodo al final de la lista de nodos secundarios del nodo especificado. Si el nodo se agrega un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo. Para obtener más información, consulte el <xref:System.Xml.XmlNode.AppendChild%2A> método.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|Agrega el nodo al principio de la lista de nodos secundarios del nodo especificado. Si el nodo se agrega un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo. Para obtener más información, consulte el <xref:System.Xml.XmlNode.PrependChild%2A> método.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|Anexa una <xref:System.Xml.XmlAttribute> nodo al final de la colección de atributos asociada con un elemento. Para obtener más información, consulte el <xref:System.Xml.XmlAttributeCollection.Append%2A> método.|  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)