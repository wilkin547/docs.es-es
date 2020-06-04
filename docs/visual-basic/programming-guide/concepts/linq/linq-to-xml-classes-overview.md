---
title: Información general sobre las clases de LINQ to XML
ms.date: 07/20/2015
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
ms.openlocfilehash: 468435a0dfac64c85b3447f15f9cde63eb98aeb0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368886"
---
# <a name="linq-to-xml-classes-overview-visual-basic"></a>Información general sobre las clases de LINQ to XML (Visual Basic)
En este tema se proporciona una lista de las clases de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en el espacio de nombres <xref:System.Xml.Linq> y proporciona una breve descripción de cada una.  
  
## <a name="linq-to-xml-classes"></a>Clases de LINQ to XML  
  
### <a name="xattribute-class"></a>Clase XAttribute  
 <xref:System.Xml.Linq.XAttribute> representa un atributo XML. Para obtener información detallada y ejemplos, consulte información general de la [clase XAttribute (Visual Basic)](xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>Clase XCData  
 <xref:System.Xml.Linq.XCData> representa un nodo de texto CDATA.  
  
### <a name="xcomment-class"></a>Clase XComment  
 <xref:System.Xml.Linq.XComment> representa un comentario XML.  
  
### <a name="xcontainer-class"></a>Clase XContainer  
 <xref:System.Xml.Linq.XContainer> es una clase base abstracta para todos los nodos que pueden tener nodos secundarios. Las siguientes clases se derivan de la clase <xref:System.Xml.Linq.XContainer>:  
  
- <xref:System.Xml.Linq.XElement>  
  
- <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>Clase XDeclaration  
 <xref:System.Xml.Linq.XDeclaration> representa una declaración XML. Una declaración XML se utiliza para declarar la versión de XML y la codificación de un documento. Asimismo, una declaración XML especifica si el documento XML es independiente. Si un documento es independiente, no hay declaraciones de marcado externas, ya sea en un DTD externo o en una entidad de parámetro externa a la que se hace referencia desde el subconjunto interno.  
  
### <a name="xdocument-class"></a>Clase XDocument  
 <xref:System.Xml.Linq.XDocument> representa un documento XML. Para obtener información detallada y ejemplos, consulte información general de la [clase XDocument (Visual Basic)](xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>Clase XDocumentType  
 <xref:System.Xml.Linq.XDocumentType> representa una definición de tipo del documento (DTD) XML.  
  
### <a name="xelement-class"></a>Clase XElement  
 <xref:System.Xml.Linq.XElement> representa un elemento XML. Para obtener información detallada y ejemplos, consulte información general de la [clase XElement (Visual Basic)](xelement-class-overview.md).  
  
### <a name="xname-class"></a>Clase XName  
 <xref:System.Xml.Linq.XName> representa nombres de elementos (<xref:System.Xml.Linq.XElement>) y atributos (<xref:System.Xml.Linq.XAttribute>). Para obtener información detallada y ejemplos, consulte información general de la [clase XDocument (Visual Basic)](xdocument-class-overview.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se ha diseñado para hacer que los nombres XML sean tan sencillos como sea posible. Debido a su complejidad, los nombres XML a menudo se consideran un tema avanzado en XML. Puede argumentarse que la complejidad no proviene de los espacios de nombres, que los desarrolladores usan regularmente en la programación, sino de los prefijos de los espacios de nombres. Los prefijos de los espacios de nombres pueden ser útiles para reducir las pulsaciones de teclas necesarias cuando se especifica código XML o hacer que el código XML sea más fácil de leer. No obstante, a menudo los prefijos son un acceso directo al espacio de nombres XML completo y no son necesarios en la mayoría de los casos. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica los nombres XML resolviendo todos los prefijos a su espacio de nombres XML correspondiente. Los prefijos están disponibles, si son necesarios, a través del método <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>.  
  
 Si es necesario es posible controlar los prefijos de espacios de nombres. En algunas circunstancias, si trabaja con otros sistemas XML, como XSLT o XAML, debe controlar los prefijos de espacio de nombres. Por ejemplo, si tiene una expresión XPath que utiliza los prefijos del espacio de nombres que está incrustado en una hoja de estilos XSLT, deberá asegurarse de que el documento XML esté serializado con prefijos de espacio de nombres que coinciden con los que se utilizan en la expresión XPath.  
  
### <a name="xnamespace-class"></a>Clase XNamespace  
 <xref:System.Xml.Linq.XNamespace> representa un espacio de nombres para un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>. Los espacios de nombres son un componente de un <xref:System.Xml.Linq.XName>.  
  
### <a name="xnode-class"></a>Clase XNode  
 <xref:System.Xml.Linq.XNode> es una clase abstracta que representa los nodos de un árbol XML. Las siguientes clases se derivan de la clase <xref:System.Xml.Linq.XNode>:  
  
- <xref:System.Xml.Linq.XText>  
  
- <xref:System.Xml.Linq.XContainer>  
  
- <xref:System.Xml.Linq.XComment>  
  
- <xref:System.Xml.Linq.XProcessingInstruction>  
  
- <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>Clase XNodeDocumentOrderComparer  
 <xref:System.Xml.Linq.XNodeDocumentOrderComparer> proporciona la funcionalidad para comparar el orden de documentos de los nodos.  
  
### <a name="xnodeequalitycomparer-class"></a>Clase XNodeEqualityComparer  
 <xref:System.Xml.Linq.XNodeEqualityComparer> proporciona la funcionalidad para comparar la igualdad del valor de los nodos.  
  
### <a name="xobject-class"></a>Clase XObject  
 <xref:System.Xml.Linq.XObject> es una clase base abstracta de <xref:System.Xml.Linq.XNode> y <xref:System.Xml.Linq.XAttribute>. Proporciona funcionalidad de evento y anotación.  
  
### <a name="xobjectchange-class"></a>Clase XObjectChange  
 <xref:System.Xml.Linq.XObjectChange> especifica el tipo de evento cuando se produce para un <xref:System.Xml.Linq.XObject>.  
  
### <a name="xobjectchangeeventargs-class"></a>Clase XObjectChangeEventArgs  
 <xref:System.Xml.Linq.XObjectChangeEventArgs> proporciona datos de los eventos <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.  
  
### <a name="xprocessinginstruction-class"></a>Clase XProcessingInstruction  
 <xref:System.Xml.Linq.XProcessingInstruction> representa una instrucción de procesamiento de XML. Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.  
  
### <a name="xtext-class"></a>Clase XText  
 <xref:System.Xml.Linq.XText> representa un nodo de texto. En la mayoría de casos no tiene que usar esta clase. Esta clase se utiliza principalmente para el contenido mixto.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la programación de LINQ to XML (Visual Basic)](linq-to-xml-programming-overview.md)
