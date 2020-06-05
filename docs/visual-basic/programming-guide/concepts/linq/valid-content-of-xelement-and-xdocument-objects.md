---
title: Contenido válido de XElement y XDocument Objects2
ms.date: 07/20/2015
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
ms.openlocfilehash: d222f19f6f588968a3ef1515dca522a4a80e1ffb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364349"
---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>Contenido válido de objetos XElement y XDocument
En este tema se describen los argumentos válidos que se pueden pasar a los constructores y los métodos que se usan para agregar contenido a elementos y documentos.  
  
## <a name="valid-content"></a>Contenido válido  
 Las consultas a menudo evalúan a <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> o a <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XAttribute>. Se pueden pasar colecciones de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> al constructor <xref:System.Xml.Linq.XElement>. Por lo tanto, resulta conveniente pasar los resultados de una consulta como contenido a los métodos y constructores que use para rellenar árboles XML.  
  
 Al agregar contenido simple, se pueden pasar varios tipos a este método. Entre los tipos válidos se incluyen los siguientes:  
  
- <xref:System.String>  
  
- <xref:System.Double>  
  
- <xref:System.Single>  
  
- <xref:System.Decimal>  
  
- <xref:System.Boolean>  
  
- <xref:System.DateTime>  
  
- <xref:System.TimeSpan>  
  
- <xref:System.DateTimeOffset>  
  
- Cualquier tipo que implemente `Object.ToString`.  
  
- Cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Al agregar contenido complejo, se pueden pasar varios tipos a este método:  
  
- <xref:System.Xml.Linq.XObject>  
  
- <xref:System.Xml.Linq.XNode>  
  
- <xref:System.Xml.Linq.XAttribute>  
  
- Cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>  
  
 Si un objeto implementa <xref:System.Collections.Generic.IEnumerable%601>, se enumera la colección del objeto y se agregan todos los elementos de la colección. Si la colección contiene objetos <xref:System.Xml.Linq.XNode> o <xref:System.Xml.Linq.XAttribute>, cada elemento de la colección se agrega por separado. Si la colección contiene texto (u objetos convertidos a texto), el texto de la colección se concatena y se agrega como un nodo de texto.  
  
 Si el contenido es `null`, no se agrega nada. Al pasar una colección, se permite que los elementos de la colección sean `null`. Un elemento `null` de la colección no tiene ningún efecto en el árbol.  
  
 Un atributo agregado debe tener un nombre único en el elemento contenedor.  
  
 Cuando se asocian objetos <xref:System.Xml.Linq.XNode> o <xref:System.Xml.Linq.XAttribute>, si el contenido nuevo no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML. Si el contenido nuevo ya tiene un elemento primario y forma parte de otro árbol XML, el nuevo contenido se clonará y dicho clon se adjuntará al árbol XML.  
  
## <a name="valid-content-for-documents"></a>Contenido válido para documentos  
 Los atributos y el contenido simple no se pueden agregar a un documento.  
  
 No existen muchos escenarios que requieran la creación de un objeto <xref:System.Xml.Linq.XDocument>. En su lugar, normalmente puede crear los árboles XML con un nodo raíz <xref:System.Xml.Linq.XElement>. A menos que exista un requisito específico de crear un documento (por ejemplo, porque deba crear instrucciones y comentarios de procesamiento en el nivel superior, o bien deba admitir tipos de documento), a menudo resulta más conveniente usar <xref:System.Xml.Linq.XElement> como nodo raíz.  
  
 El contenido válido para un documento incluye lo siguiente:  
  
- Cero o un objeto <xref:System.Xml.Linq.XDocumentType>. Los tipos de documento deben ir antes del elemento.  
  
- Cero o un elemento.  
  
- Cero o más comentarios.  
  
- Cero o más instrucciones de procesamiento.  
  
- Cero o más nodos de texto que contengan solo espacios en blanco.  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>Constructores y funciones que permiten agregar contenido  
 Los métodos siguientes permiten agregar contenido secundario a un objeto <xref:System.Xml.Linq.XElement> o a un objeto <xref:System.Xml.Linq.XDocument>:  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|Construye un objeto <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|Construye un objeto <xref:System.Xml.Linq.XDocument>.|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Agrega al final del contenido secundario del objeto <xref:System.Xml.Linq.XElement> o del objeto <xref:System.Xml.Linq.XDocument>.|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Añade un contenido detrás de <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Agrega contenido antes de <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Agrega un contenido al comienzo de los contenidos secundarios del <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Reemplaza todo el contenido (atributos y nodos secundarios) de un objeto <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Reemplaza los atributos de un objeto <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Reemplaza los nodos secundarios por contenido nuevo.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Reemplaza un nodo por contenido nuevo.|  
  
## <a name="see-also"></a>Consulte también

- [Crear árboles XML (Visual Basic)](creating-xml-trees.md)
