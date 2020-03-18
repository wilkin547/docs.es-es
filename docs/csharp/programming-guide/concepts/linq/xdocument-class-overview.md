---
title: Información general de la clase XDocument (C#)
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: de49dc071d22dd77dddea29ca114663261e3edda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69590843"
---
# <a name="xdocument-class-overview-c"></a>Información general de la clase XDocument (C#)
En este tema se presenta la clase <xref:System.Xml.Linq.XDocument>.  
  
## <a name="overview-of-the-xdocument-class"></a>Información general acerca de la clase XDocument  
 La clase <xref:System.Xml.Linq.XDocument> contiene la información necesaria para un documento XML válido. Incluye una declaración XML, instrucciones de procesamiento y comentarios.  
  
 Tenga en cuenta que solo debe crear objetos <xref:System.Xml.Linq.XDocument> si necesita la funcionalidad específica que proporciona la clase <xref:System.Xml.Linq.XDocument>. En muchas circunstancias, puede trabajar directamente con <xref:System.Xml.Linq.XElement>. Trabajar directamente con <xref:System.Xml.Linq.XElement> constituye un modelo de programación más simple.  
  
 <xref:System.Xml.Linq.XDocument> se deriva de <xref:System.Xml.Linq.XContainer>. Por lo tanto, puede contener nodos secundarios. Sin embargo, los objetos <xref:System.Xml.Linq.XDocument> solo pueden tener un nodo <xref:System.Xml.Linq.XElement> secundario. Esto refleja el estándar XML: solo puede haber un elemento raíz en un documento XML.  
  
## <a name="components-of-xdocument"></a>Componentes de XDocument  
 Un objeto <xref:System.Xml.Linq.XDocument> puede contener los siguientes elementos:  
  
- Un objeto <xref:System.Xml.Linq.XDeclaration>. <xref:System.Xml.Linq.XDeclaration> permite especificar las partes pertinentes de una declaración XML: la versión XML, la codificación del documento y si el documento XML es independiente.  
  
- Un objeto <xref:System.Xml.Linq.XElement>. Es el nodo raíz del documento XML.  
  
- Cualquier número de objetos <xref:System.Xml.Linq.XProcessingInstruction>. Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.  
  
- Cualquier número de objetos <xref:System.Xml.Linq.XComment>. Los comentarios serán del mismo nivel que el elemento raíz. El objeto <xref:System.Xml.Linq.XComment> no puede ser el primer argumento de la lista, ya que no es válido que el documento XML empiece con un comentario.  
  
- Un elemento <xref:System.Xml.Linq.XDocumentType> para el DTD.  
  
 Al serializar un objeto <xref:System.Xml.Linq.XDocument>, aunque `XDocument.Declaration` sea `null`, el resultado generará una declaración XML, siempre y cuando el redactor haya establecido `Writer.Settings.OmitXmlDeclaration` en `false` (valor predeterminado).  
  
 De manera predeterminada, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] establece la versión en "1.0" y la codificación en "utf-8".  
  
## <a name="using-xelement-without-xdocument"></a>Usar XElement sin XDocument  
 Tal como se indicó anteriormente, la clase <xref:System.Xml.Linq.XElement> es la clase principal de la interfaz de programación [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. En muchos casos, la aplicación no requerirá la creación de un documento. Mediante la clase <xref:System.Xml.Linq.XElement>, puede crear un árbol XML, agregarle otros árboles XML, modificar el árbol XML o guardarlo.  
  
## <a name="using-xdocument"></a>Usar XDocument  
 Para construir un objeto <xref:System.Xml.Linq.XDocument>, use la construcción funcional, al igual que cuando se construyen objetos <xref:System.Xml.Linq.XElement>.  
  
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

- [Información general sobre la programación de LINQ to XML (C#)](./linq-to-xml-overview.md)
