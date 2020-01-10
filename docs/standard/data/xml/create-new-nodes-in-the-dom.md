---
title: Creación de nuevos nodos en el DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
ms.openlocfilehash: f48990286405baee347becef87d0511cd42e9e77
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711004"
---
# <a name="create-new-nodes-in-the-dom"></a>Creación de nuevos nodos en el DOM
<xref:System.Xml.XmlDocument> tiene un método de creación para todos los tipos de nodos. Para crear el nodo, proporcione el método con un nombre cuando sea preciso, y el contenido y otros parámetros para aquellos nodos que tengan contenido (por ejemplo, los nodos de texto). Los siguientes métodos son los que necesitan que se proporcione un nombre y otros cuantos parámetros para crear un nodo apropiado.  
  
- <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
- <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
- <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
- <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
- <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 Otros tipos de nodos tienen más requisitos aparte de que se proporcionen datos a los parámetros.  
  
 Para obtener más información sobre atributos, vea [Crear nuevos atributos para elementos en DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md). Para obtener información sobre la validación de nombres de atributos y elementos, vea [Comprobación de nombres de atributos y elementos XML al crear nuevos nodos](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md). Para crear referencias de entidad, vea [Creación de nuevas referencias de entidad](../../../../docs/standard/data/xml/creating-new-entity-references.md). Para obtener información sobre cómo los espacios de nombres afectan a la expansión de referencias de entidad, vea [Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).  
  
 Una vez creados los nuevos nodos, hay disponibles varios métodos para insertarlos en el árbol. En la tabla se enumeran los métodos con una descripción de dónde aparece el nuevo nodo en el Modelo de objetos de documento (DOM).  
  
|Método|Colocación del nodo|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|Insertado antes del nodo de referencia. Por ejemplo, para insertar el nuevo nodo en la posición 5:<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> Para obtener más información, vea el método <xref:System.Xml.XmlNode.InsertBefore%2A>.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|Insertado después del nodo de referencia. Por ejemplo:<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> Para obtener más información, vea el método <xref:System.Xml.XmlNode.InsertAfter%2A>.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|Agrega el nodo al final de la lista de nodos secundarios del nodo especificado. Si el nodo se agrega como un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo. Para obtener más información, vea el método <xref:System.Xml.XmlNode.AppendChild%2A>.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|Agrega el nodo al principio de la lista de nodos secundarios del nodo especificado. Si el nodo se agrega como un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo. Para obtener más información, vea el método <xref:System.Xml.XmlNode.PrependChild%2A>.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|Agrega un nodo <xref:System.Xml.XmlAttribute> al final de la colección de atributos asociada a un elemento. Para obtener más información, vea el método <xref:System.Xml.XmlAttributeCollection.Append%2A>.|  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
