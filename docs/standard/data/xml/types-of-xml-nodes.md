---
title: Tipos de nodos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
ms.openlocfilehash: 83b8c09323e73a9b3ba7dea8d272d7d41d03add1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710094"
---
# <a name="types-of-xml-nodes"></a>Tipos de nodos XML
Cuando se lee un documento XML en la memoria como un árbol de nodos, el tipo de nodo se decide al crear los nodos. El modelo de objetos de documento (DOM) dispone de varias clases de tipos de nodos, determinados por el World Wide Web Consortium (W3C) y enumerados en la sección 1.1.1 El modelo de estructura DOM. En la tabla siguiente se muestran los tipos de nodo, el objeto asignado a dicho tipo de nodo y una breve descripción de cada uno.  
  
|Tipo de nodo DOM|Objeto de|Descripción|  
|-------------------|------------|-----------------|  
|Documento|<xref:System.Xml.XmlDocument>|Contenedor de todos los nodos del árbol. También se conoce como la raíz del documento, que no siempre coincide con el elemento raíz.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|Contenedor temporal de uno o varios nodos sin estructura de árbol.|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|Representa el nodo `<!DOCTYPE…>`.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|Representa el texto de referencias a entidades sin expandir.|  
|Elemento|<xref:System.Xml.XmlElement>|Representa un nodo de elemento.|  
|Attr|<xref:System.Xml.XmlAttribute>|Atributo de un elemento.|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|Nodo de instrucción de procesamiento.|  
|Comentario|<xref:System.Xml.XmlComment>|Nodo de comentario.|  
|Text|<xref:System.Xml.XmlText>|Texto que pertenece a un elemento o atributo.|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|Representa CDATA.|  
|Entity|<xref:System.Xml.XmlEntity>|Representa las declaraciones `<!ENTITY…>` de un documento XML, desde un subconjunto de definición de tipo de documento (DTD) interno o desde DTD externas y entidades de parámetros.|  
|Notation|<xref:System.Xml.XmlNotation>|Representa una notación declarada en la DTD.|  
  
 Aunque un atributo (*attr*) aparezca como nodo en la sección 1.2: Interfaces fundamentales de DOM del W3C Level 1, se considera un nodo secundario de cualquier nodo elemento.  
  
 En la tabla siguiente se muestran tipos de nodo adicionales no definidos por el W3C, aunque se pueden utilizar en el modelo de objetos .NET como enumeraciones **XmlNodeType**. Por tanto, no hay columna Tipo de nodo DOM equivalente para estos tipos de nodo.  
  
|Tipo de nodo|Descripción|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Representa el nodo de declaración `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Representa un espacio en blanco significativo, que es un espacio en blanco en contenido mixto.|  
|<xref:System.Xml.XmlWhitespace>|Representa un espacio en blanco en el contenido de un elemento.|  
|EndElement|Se devuelve cuando **XmlReader** llega al final de un elemento.<br /><br /> XML de ejemplo: **\</item>**<br /><br /> Para obtener más información, vea <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Se devuelve cuando **XmlReader** llega al final del reemplazo de la entidad como resultado de una llamada a <xref:System.Xml.XmlReader.ResolveEntity%2A>. Para obtener más información, vea <xref:System.Xml.XmlNodeType>.|  
  
 Para ver un ejemplo de código en el que se lee XML y se utiliza un constructor case en los tipos de nodo para imprimir información acerca del nodo y su contenido, vea <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.  
  
 Para obtener más información acerca de la jerarquía de objetos de los tipos de nodo y su nombre de objeto equivalente, vea [Jerarquía de Document Object Model (DOM) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md). Para obtener más información acerca de los objetos creados en el árbol de nodos, vea [Asignar la jerarquía de objetos a datos XML](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
