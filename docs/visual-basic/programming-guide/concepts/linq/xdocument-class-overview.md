---
title: "Información general de la clase XDocument (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 41b09335ae124ac290d8cd51afda71dfd935b7ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xdocument-class-overview-visual-basic"></a>Información general de la clase XDocument (Visual Basic)
En este tema se presenta la clase <xref:System.Xml.Linq.XDocument>.  
  
## <a name="overview-of-the-xdocument-class"></a>Información general acerca de la clase XDocument  
 La clase <xref:System.Xml.Linq.XDocument> contiene la información necesaria para un documento XML válido. Incluye una declaración XML, instrucciones de procesamiento y comentarios.  
  
 Tenga en cuenta que solo debe crear objetos <xref:System.Xml.Linq.XDocument> si necesita la funcionalidad específica que proporciona la clase <xref:System.Xml.Linq.XDocument>. En muchas circunstancias, puede trabajar directamente con <xref:System.Xml.Linq.XElement>. Trabajar directamente con <xref:System.Xml.Linq.XElement> constituye un modelo de programación más simple.  
  
 <xref:System.Xml.Linq.XDocument> se deriva de <xref:System.Xml.Linq.XContainer>. Por lo tanto, puede contener nodos secundarios. Sin embargo, los objetos <xref:System.Xml.Linq.XDocument> solo pueden tener un nodo <xref:System.Xml.Linq.XElement> secundario. Esto refleja el estándar XML: solo puede haber un elemento raíz en un documento XML.  
  
## <a name="components-of-xdocument"></a>Componentes de XDocument  
 Un objeto <xref:System.Xml.Linq.XDocument> puede contener los siguientes elementos:  
  
-   Un objeto <xref:System.Xml.Linq.XDeclaration>. <xref:System.Xml.Linq.XDeclaration> permite especificar las partes pertinentes de una declaración XML: la versión XML, la codificación del documento y si el documento XML es independiente.  
  
-   Un objeto <xref:System.Xml.Linq.XElement>. Es el nodo raíz del documento XML.  
  
-   Cualquier número de objetos <xref:System.Xml.Linq.XProcessingInstruction>. Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.  
  
-   Cualquier número de objetos <xref:System.Xml.Linq.XComment>. Los comentarios serán del mismo nivel que el elemento raíz. El objeto <xref:System.Xml.Linq.XComment> no puede ser el primer argumento de la lista, ya que no es válido que el documento XML empiece con un comentario.  
  
-   Un elemento <xref:System.Xml.Linq.XDocumentType> para el DTD.  
  
 Al serializar un objeto <xref:System.Xml.Linq.XDocument>, aunque `XDocument.Declaration` sea `null`, el resultado generará una declaración XML, siempre y cuando el redactor haya establecido `Writer.Settings.OmitXmlDeclaration` en `false` (valor predeterminado).  
  
 De manera predeterminada, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] establece la versión en "1.0" y la codificación en "utf-8".  
  
## <a name="using-xelement-without-xdocument"></a>Usar XElement sin XDocument  
 Tal como se indicó anteriormente, la clase <xref:System.Xml.Linq.XElement> es la clase principal de la interfaz de programación [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. En muchos casos, la aplicación no requerirá la creación de un documento. Mediante la clase <xref:System.Xml.Linq.XElement>, puede crear un árbol XML, agregarle otros árboles XML, modificar el árbol XML o guardarlo.  
  
## <a name="using-xdocument"></a>Usar XDocument  
 Para construir un objeto <xref:System.Xml.Linq.XDocument>, use la construcción funcional, al igual que cuando se construyen objetos <xref:System.Xml.Linq.XElement>.  
  
 El código siguiente crea un objeto <xref:System.Xml.Linq.XDocument> y sus objetos contenidos asociados.  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
                       <!--This is a comment.-->  
                       <?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
                       <Pubs>  
                           <Book>  
                               <Title>Artifacts of Roman Civilization</Title>  
                               <Author>Moreno, Jordao</Author>  
                           </Book>  
                           <Book>  
                               <Title>Midieval Tools and Implements</Title>  
                               <Author>Gazit, Inbar</Author>  
                           </Book>  
                       </Pubs>  
                       <!--This is another comment.-->  
doc.Save("test.xml")  
```  
  
 Al examinar el archivo test.xml, obtendrá el siguiente resultado:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML de información general de programación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
