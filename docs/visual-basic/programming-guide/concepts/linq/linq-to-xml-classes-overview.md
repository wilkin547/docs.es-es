---
title: "Introducción (Visual Basic) de las clases LINQ to XML | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 12885f93bb7e56dd66d36090d41700195313e944
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-classes-overview-visual-basic"></a>LINQ to XML de información general de clases (Visual Basic)
Este tema proporciona una lista de los [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] clases en el <xref:System.Xml.Linq>espacio de nombres y una breve descripción de cada uno.</xref:System.Xml.Linq>  
  
## <a name="linq-to-xml-classes"></a>Clases de LINQ to XML  
  
### <a name="xattribute-class"></a>Clase XAttribute  
 <xref:System.Xml.Linq.XAttribute>Representa un atributo XML.</xref:System.Xml.Linq.XAttribute> Para obtener información detallada y ejemplos, vea [general sobre la clase XAttribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>Clase XCData  
 <xref:System.Xml.Linq.XCData>Representa un nodo de texto CDATA.</xref:System.Xml.Linq.XCData>  
  
### <a name="xcomment-class"></a>Clase XComment  
 <xref:System.Xml.Linq.XComment>Representa un comentario XML.</xref:System.Xml.Linq.XComment>  
  
### <a name="xcontainer-class"></a>Clase XContainer  
 <xref:System.Xml.Linq.XContainer>es una clase base abstracta para todos los nodos que pueden tener nodos secundarios.</xref:System.Xml.Linq.XContainer> Las siguientes clases se derivan de la <xref:System.Xml.Linq.XContainer>clase:</xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>Clase XDeclaration  
 <xref:System.Xml.Linq.XDeclaration>Representa una declaración XML.</xref:System.Xml.Linq.XDeclaration> Una declaración XML se utiliza para declarar la versión de XML y la codificación de un documento. Asimismo, una declaración XML especifica si el documento XML es independiente. Si un documento es independiente, no hay declaraciones de marcado externas, ya sea en un DTD externo o en una entidad de parámetro externa a la que se hace referencia desde el subconjunto interno.  
  
### <a name="xdocument-class"></a>Clase XDocument  
 <xref:System.Xml.Linq.XDocument>Representa un documento XML.</xref:System.Xml.Linq.XDocument> Para obtener información detallada y ejemplos, vea [general sobre la clase XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>Clase XDocumentType  
 <xref:System.Xml.Linq.XDocumentType>Representa una definición de tipo de documento (DTD) XML.</xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xelement-class"></a>Clase XElement  
 <xref:System.Xml.Linq.XElement>Representa un elemento XML.</xref:System.Xml.Linq.XElement> Para obtener información detallada y ejemplos, vea [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>Clase XName  
 <xref:System.Xml.Linq.XName>representa nombres de elementos (<xref:System.Xml.Linq.XElement>) y atributos (<xref:System.Xml.Linq.XAttribute>).</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XName> Para obtener información detallada y ejemplos, vea [general sobre la clase XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] se ha diseñado para hacer que los nombres XML sean tan sencillos como sea posible. Debido a su complejidad, los nombres XML a menudo se consideran un tema avanzado en XML. Puede argumentarse que la complejidad no proviene de los espacios de nombres, que los desarrolladores usan regularmente en la programación, sino de los prefijos de los espacios de nombres. Los prefijos de los espacios de nombres pueden ser útiles para reducir las pulsaciones de teclas necesarias cuando se especifica código XML o hacer que el código XML sea más fácil de leer. No obstante, a menudo los prefijos son un acceso directo al espacio de nombres XML completo y no son necesarios en la mayoría de los casos. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]simplifica los nombres XML resolviendo todos los prefijos a su espacio de nombres XML correspondiente. Los prefijos están disponibles, si son necesarios, a través de la <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>método.</xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>  
  
 Si es necesario es posible controlar los prefijos de espacios de nombres. En algunas circunstancias, si trabaja con otros sistemas XML, como XSLT o XAML, debe controlar los prefijos de espacio de nombres. Por ejemplo, si tiene una expresión XPath que utiliza los prefijos del espacio de nombres que está incrustado en una hoja de estilos XSLT, deberá asegurarse de que el documento XML esté serializado con prefijos de espacio de nombres que coinciden con los que se utilizan en la expresión XPath.  
  
### <a name="xnamespace-class"></a>Clase XNamespace  
 <xref:System.Xml.Linq.XNamespace>Representa un espacio de nombres para un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XNamespace> Espacios de nombres son un componente de un <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName>  
  
### <a name="xnode-class"></a>Clase XNode  
 <xref:System.Xml.Linq.XNode>es una clase abstracta que representa los nodos de un árbol XML.</xref:System.Xml.Linq.XNode> Las siguientes clases se derivan de la <xref:System.Xml.Linq.XNode>clase:</xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XText></xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType></xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>Clase XNodeDocumentOrderComparer  
 <xref:System.Xml.Linq.XNodeDocumentOrderComparer>Proporciona funcionalidad para comparar el orden de los nodos documento.</xref:System.Xml.Linq.XNodeDocumentOrderComparer>  
  
### <a name="xnodeequalitycomparer-class"></a>Clase XNodeEqualityComparer  
 <xref:System.Xml.Linq.XNodeEqualityComparer>Proporciona funcionalidad para comparar la igualdad de valores de los nodos.</xref:System.Xml.Linq.XNodeEqualityComparer>  
  
### <a name="xobject-class"></a>Clase XObject  
 <xref:System.Xml.Linq.XObject>es una clase base abstracta de <xref:System.Xml.Linq.XNode>y <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XObject> Proporciona funcionalidad de evento y anotación.  
  
### <a name="xobjectchange-class"></a>Clase XObjectChange  
 <xref:System.Xml.Linq.XObjectChange>Especifica el tipo de evento cuando se produce un evento para un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObjectChange>  
  
### <a name="xobjectchangeeventargs-class"></a>Clase XObjectChangeEventArgs  
 <xref:System.Xml.Linq.XObjectChangeEventArgs>Proporciona datos para el <xref:System.Xml.Linq.XObject.Changing>y <xref:System.Xml.Linq.XObject.Changed>eventos.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObjectChangeEventArgs>  
  
### <a name="xprocessinginstruction-class"></a>Clase XProcessingInstruction  
 <xref:System.Xml.Linq.XProcessingInstruction>Representa una instrucción de procesamiento de XML.</xref:System.Xml.Linq.XProcessingInstruction> Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.  
  
### <a name="xtext-class"></a>Clase XText  
 <xref:System.Xml.Linq.XText>Representa un nodo de texto.</xref:System.Xml.Linq.XText> En la mayoría de casos no tiene que usar esta clase. Esta clase se utiliza principalmente para el contenido mixto.  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML de información general de programación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
