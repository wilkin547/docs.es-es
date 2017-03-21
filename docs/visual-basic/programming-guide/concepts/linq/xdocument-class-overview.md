---
title: "Información general de la clase XDocument (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31111b23adb019aad3ad55787c073dc02446291d
ms.lasthandoff: 03/13/2017

---
# <a name="xdocument-class-overview-visual-basic"></a>Información general de la clase XDocument (Visual Basic)
Este tema presenta la <xref:System.Xml.Linq.XDocument>clase.</xref:System.Xml.Linq.XDocument>  
  
## <a name="overview-of-the-xdocument-class"></a>Información general acerca de la clase XDocument  
 La <xref:System.Xml.Linq.XDocument>clase contiene la información necesaria para un documento XML válido.</xref:System.Xml.Linq.XDocument> Incluye una declaración XML, instrucciones de procesamiento y comentarios.  
  
 Tenga en cuenta que sólo tiene que crear <xref:System.Xml.Linq.XDocument>objetos si necesita la funcionalidad específica proporcionan por la <xref:System.Xml.Linq.XDocument>clase.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument> En muchas circunstancias, puede trabajar directamente con <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> Trabajar directamente con <xref:System.Xml.Linq.XElement>es un modelo de programación más simple.</xref:System.Xml.Linq.XElement>  
  
 <xref:System.Xml.Linq.XDocument>se deriva de <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XDocument> Por lo tanto, puede contener nodos secundarios. Sin embargo, <xref:System.Xml.Linq.XDocument>objetos pueden tener sólo un elemento secundario <xref:System.Xml.Linq.XElement>nodo.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> Esto refleja el estándar XML: solo puede haber un elemento raíz en un documento XML.  
  
## <a name="components-of-xdocument"></a>Componentes de XDocument  
 Un <xref:System.Xml.Linq.XDocument>puede contener los siguientes elementos:</xref:System.Xml.Linq.XDocument>  
  
-   Una <xref:System.Xml.Linq.XDeclaration>objeto.</xref:System.Xml.Linq.XDeclaration> <xref:System.Xml.Linq.XDeclaration>permite especificar las partes pertinentes de una declaración XML: la versión XML, la codificación del documento, y si el documento XML es independiente.</xref:System.Xml.Linq.XDeclaration>  
  
-   Una <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement> Es el nodo raíz del documento XML.  
  
-   Cualquier número de <xref:System.Xml.Linq.XProcessingInstruction>objetos.</xref:System.Xml.Linq.XProcessingInstruction> Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.  
  
-   Cualquier número de <xref:System.Xml.Linq.XComment>objetos.</xref:System.Xml.Linq.XComment> Los comentarios serán del mismo nivel que el elemento raíz. La <xref:System.Xml.Linq.XComment>objeto no puede ser el primer argumento en la lista, porque no es válido para un documento XML empiece con un comentario.</xref:System.Xml.Linq.XComment>  
  
-   Un <xref:System.Xml.Linq.XDocumentType>para el DTD.</xref:System.Xml.Linq.XDocumentType>  
  
 Cuando serializa un <xref:System.Xml.Linq.XDocument>, incluso si `XDocument.Declaration` es `null`, la salida tendrá una declaración XML si el sistema de escritura `Writer.Settings.OmitXmlDeclaration` establecido en `false` (valor predeterminado).</xref:System.Xml.Linq.XDocument>  
  
 De manera predeterminada, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] establece la versión en "1.0" y la codificación en "utf-8".  
  
## <a name="using-xelement-without-xdocument"></a>Usar XElement sin XDocument  
 Como se mencionó anteriormente, la <xref:System.Xml.Linq.XElement>clase es la clase principal de la [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] interfaz de programación.</xref:System.Xml.Linq.XElement> En muchos casos, la aplicación no requerirá la creación de un documento. Mediante el uso de la <xref:System.Xml.Linq.XElement>(clase), puede crear un árbol XML, agregarle otros árboles XML, modificar el árbol XML y guardar lo</xref:System.Xml.Linq.XElement>  
  
## <a name="using-xdocument"></a>Usar XDocument  
 Para construir un <xref:System.Xml.Linq.XDocument>, use la construcción funcional, al igual que para construir <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 El código siguiente crea un <xref:System.Xml.Linq.XDocument>objeto y sus objetos contenidos asociados.</xref:System.Xml.Linq.XDocument>  
  
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
