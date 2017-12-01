---
title: Tipos de nodos XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3914a2c5c06a2cc73f14bc473984094b474d537e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-xml-nodes"></a>Tipos de nodos XML
Cuando se lee un documento XML en la memoria como un árbol de nodos, el tipo de nodo se decide al crear los nodos. El modelo de objetos de documento (DOM) dispone de varias clases de tipos de nodos, determinados por el World Wide Web Consortium (W3C) y enumerados en la sección 1.1.1 El modelo de estructura DOM. En la tabla siguiente se muestran los tipos de nodo, el objeto asignado a dicho tipo de nodo y una breve descripción de cada uno.  
  
|Tipo de nodo DOM|Objeto|Descripción|  
|-------------------|------------|-----------------|  
|Documento|<xref:System.Xml.XmlDocument>|Contenedor de todos los nodos del árbol. También se conoce como la raíz del documento, que no siempre coincide con el elemento raíz.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|Contenedor temporal de uno o varios nodos sin estructura de árbol.|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|Representa el nodo `<!DOCTYPE…>`.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|Representa el texto de referencias a entidades sin expandir.|  
|Elemento|<xref:System.Xml.XmlElement>|Representa un nodo de elemento.|  
|Attr|<xref:System.Xml.XmlAttribute>|Atributo de un elemento.|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|Nodo de instrucción de procesamiento.|  
|Comentario|<xref:System.Xml.XmlComment>|Nodo de comentario.|  
|Texto|<xref:System.Xml.XmlText>|Texto que pertenece a un elemento o atributo.|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|Representa CDATA.|  
|Entity|<xref:System.Xml.XmlEntity>|Representa las declaraciones `<!ENTITY…>` de un documento XML, desde un subconjunto de definición de tipo de documento (DTD) interno o desde DTD externas y entidades de parámetros.|  
|Notation|<xref:System.Xml.XmlNotation>|Representa una notación declarada en la DTD.|  
  
 Aunque un atributo (*attr*) aparece en el nivel 1 de DOM del W3C sección 1.2 Interfaces de fundamentales como un nodo, no se considera un elemento secundario de cualquier nodo de elemento.  
  
 La tabla siguiente muestran tipos de nodo adicionales no definidos por el W3C, sin embargo, están disponibles para su uso en el modelo de objetos de Microsoft .NET Framework como **XmlNodeType** enumeraciones. Por tanto, no hay columna Tipo de nodo DOM equivalente para estos tipos de nodo.  
  
|Tipo de nodo|Descripción|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Representa el nodo de declaración `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Representa un espacio en blanco significativo, que es un espacio en blanco en contenido mixto.|  
|<xref:System.Xml.XmlWhitespace>|Representa un espacio en blanco en el contenido de un elemento.|  
|EndElement|Devuelve cuando **XmlReader** llega al final de un elemento.<br /><br /> XML de ejemplo:  **\< /artículo >**<br /><br /> Para obtener más información, consulta <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Devuelve cuando **XmlReader** llega al final del reemplazo de entidad como resultado de una llamada a <xref:System.Xml.XmlReader.ResolveEntity%2A>. Para obtener más información, consulta <xref:System.Xml.XmlNodeType>.|  
  
 Para ver un ejemplo de código que lee XML y se utiliza un constructor case en los tipos de nodo para imprimir información acerca del nodo y su contenido, consulte <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.  
  
 Para obtener más información sobre la jerarquía de objetos de los tipos de nodo y su nombre de objeto equivalente, vea [jerarquía del modelo de objetos de documento (DOM) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md). Para obtener más información sobre los objetos creados en el árbol de nodos, vea [asignar la jerarquía de objetos a datos XML](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
