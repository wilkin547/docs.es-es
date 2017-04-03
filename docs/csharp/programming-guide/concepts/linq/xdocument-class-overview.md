---
title: "Información general de la clase XDocument (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f3233a634e358ee227b0adbe30cb05d1efbf8fe0
ms.lasthandoff: 03/13/2017

---
# <a name="xdocument-class-overview-c"></a>Información general de la clase XDocument (C#)
Este tema presenta la clase <xref:System.Xml.Linq.XDocument>.  
  
## <a name="overview-of-the-xdocument-class"></a>Información general acerca de la clase XDocument  
 La clase <xref:System.Xml.Linq.XDocument> contiene la información necesaria para un documento XML válido. Incluye una declaración XML, instrucciones de procesamiento y comentarios.  
  
 Tenga en cuenta que solo tiene que crear objetos <xref:System.Xml.Linq.XDocument> si necesita la función específica que proporciona la clase <xref:System.Xml.Linq.XDocument>. En muchas circunstancias, puede trabajar directamente con <xref:System.Xml.Linq.XElement>. Trabajar directamente con <xref:System.Xml.Linq.XElement> es un modelo de programación más sencillo.  
  
 <xref:System.Xml.Linq.XDocument> deriva de <xref:System.Xml.Linq.XContainer>. Por lo tanto, puede contener nodos secundarios. En cambio, los objetos <xref:System.Xml.Linq.XDocument> solo pueden tener un nodo secundario <xref:System.Xml.Linq.XElement>. Esto refleja el estándar XML: solo puede haber un elemento raíz en un documento XML.  
  
## <a name="components-of-xdocument"></a>Componentes de XDocument  
 Un <xref:System.Xml.Linq.XDocument> puede contener los siguientes elementos:  
  
-   Un objeto <xref:System.Xml.Linq.XDeclaration>. <xref:System.Xml.Linq.XDeclaration> le permite especificar las partes pertinentes de una declaración XML: la versión XML, la codificación del documento y si el documento XML es independiente.  
  
-   Un objeto <xref:System.Xml.Linq.XElement>. Es el nodo raíz del documento XML.  
  
-   Cualquier número de objetos <xref:System.Xml.Linq.XProcessingInstruction>. Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.  
  
-   Cualquier número de objetos <xref:System.Xml.Linq.XComment>. Los comentarios serán del mismo nivel que el elemento raíz. El objeto <xref:System.Xml.Linq.XComment> no puede ser el primer argumento de la lista, ya que no es válido que un documento XML empiece con un comentario.  
  
-   Un <xref:System.Xml.Linq.XDocumentType> para la DTD.  
  
 Al serializar un objeto <xref:System.Xml.Linq.XDocument>, aunque `XDocument.Declaration` sea `null`, el resultado generará una declaración XML si el redactor ha establecido `Writer.Settings.OmitXmlDeclaration` en `false` (el valor predeterminado).  
  
 De manera predeterminada, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] establece la versión en "1.0" y la codificación en "utf-8".  
  
## <a name="using-xelement-without-xdocument"></a>Usar XElement sin XDocument  
 Tal como se ha mencionado anteriormente, la clase <xref:System.Xml.Linq.XElement> es la clase principal de la interfaz de programación [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. En muchos casos, la aplicación no requerirá la creación de un documento. Mediante la clase <xref:System.Xml.Linq.XElement>, puede crear un árbol XML, agregarle otros árboles XML, modificar el árbol XML o guardarlo.  
  
## <a name="using-xdocument"></a>Usar XDocument  
 Para construir un objeto <xref:System.Xml.Linq.XDocument>, use la construcción funcional como lo haría para construir los objetos <xref:System.Xml.Linq.XElement>.  
  
 El código siguiente crea un objeto <xref:System.Xml.Linq.XDocument> y sus objetos contenidos asociados.  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
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
 [Información general sobre la programación de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
