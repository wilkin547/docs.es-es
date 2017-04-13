---
title: "Tipos de nodos XML | Microsoft Docs"
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
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Tipos de nodos XML
Cuando se lee un documento XML en la memoria como un árbol de nodos, el tipo de nodo se decide al crear los nodos.  El modelo de objetos de documento \(DOM\) dispone de varias clases de tipos de nodos, determinados por el World Wide Web Consortium \(W3C\) y enumerados en la sección 1.1.1 El modelo de estructura DOM.  En la tabla siguiente se muestran los tipos de nodo, el objeto asignado a dicho tipo de nodo y una breve descripción de cada uno.  
  
|Tipo de nodo DOM|Objeto|Descripción|  
|----------------------|------------|-----------------|  
|Document|[Clase XmlDocument](frlrfSystemXmlXmlDocumentClassTopic)|Contenedor de todos los nodos del árbol.  También se conoce como la raíz del documento, que no siempre coincide con el elemento raíz.|  
|DocumentFragment|[Clase XmlDocumentFragment](frlrfSystemXmlXmlDocumentFragmentClassTopic)|Contenedor temporal de uno o varios nodos sin estructura de árbol.|  
|DocumentType|[Clase XmlDocumentType](frlrfSystemXmlXmlDocumentTypeClassTopic)|Representa el nodo `<!DOCTYPE…>`.|  
|EntityReference|[Clase XmlEntityReference](frlrfSystemXmlXmlEntityReferenceClassTopic)|Representa el texto de referencias a entidades sin expandir.|  
|Elemento|[Clase XmlElement](frlrfSystemXmlXmlElementClassTopic)|Representa un nodo de elemento.|  
|Attr|[Clase XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic)|Atributo de un elemento.|  
|ProcessingInstruction|[Clase XmlProcessingInstruction](frlrfSystemXmlXmlProcessingInstructionClassTopic)|Nodo de instrucción de procesamiento.|  
|Comentario|[Clase XmlComment](frlrfSystemXmlXmlCommentClassTopic)|Nodo de comentario.|  
|Texto|[Clase XmlText](frlrfSystemXmlXmlTextClassTopic)|Texto que pertenece a un elemento o atributo.|  
|CDATASection|[Clase XmlCDataSection](frlrfSystemXmlXmlCDataSectionClassTopic)|Representa CDATA.|  
|Entity|[Clase XmlEntity](frlrfSystemXmlXmlEntityClassTopic)|Representa las declaraciones `<!ENTITY…>` de un documento XML, desde un subconjunto de definición de tipo de documento \(DTD\) interno o desde DTD externas y entidades de parámetros.|  
|Notation|[Clase XmlNotation](frlrfSystemXmlXmlNotationClassTopic)|Representa una notación declarada en la DTD.|  
  
 Aunque un atributo \(*attr*\) aparezca como nodo en la sección 1.2: Interfaces fundamentales de DOM del W3C Level 1, se considera un nodo secundario de cualquier nodo elemento.  
  
 En la tabla siguiente se muestran tipos de nodo adicionales no definidos por el W3C, aunque se pueden utilizar en el Modelo de objetos .NET como enumeraciones **XmlNodeType**.  Por tanto, no hay columna Tipo de nodo DOM equivalente para estos tipos de nodo.  
  
|Tipo de nodo|Descripción|  
|------------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Representa el nodo de declaración `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Representa un espacio en blanco significativo, que es un espacio en blanco en contenido mixto.|  
|<xref:System.Xml.XmlWhitespace>|Representa un espacio en blanco en el contenido de un elemento.|  
|EndElement|Se devuelve cuando **XmlReader** llega al final de un elemento.<br /><br /> XML de ejemplo: **\<\/item\>**<br /><br /> Para obtener más información, vea [XmlNodeType Enumeration](frlrfSystemXmlXmlNodeTypeClassTopic).|  
|EndEntity|Se devuelve cuando **XmlReader** llega al final del reemplazo de la entidad como resultado de una llamada a <xref:System.Xml.XmlReader.ResolveEntity%2A>.  Para obtener más información, vea [XmlNodeType Enumeration](frlrfSystemXmlXmlNodeTypeClassTopic).|  
  
 Para ver un ejemplo de código en el que se lee XML y se utiliza un constructor case en los tipos de nodo para imprimir información acerca del nodo y su contenido, vea [XmlSignificantWhitespace.NodeType Property](frlrfSystemXmlXmlSignificantWhitespaceClassNodeTypeTopic).  
  
 Para obtener más información acerca de la jerarquía de objetos de los tipos de nodo y su nombre de objeto equivalente, vea [Jerarquía del Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md).  Para obtener más información acerca de los objetos creados en el árbol de nodos, vea [Asignar la jerarquía de objetos a datos XML](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)