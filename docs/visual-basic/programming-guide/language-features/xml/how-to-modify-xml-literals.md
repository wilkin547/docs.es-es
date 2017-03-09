---
title: "C&#243;mo: Modificar literales XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "eje XML [Visual Basic], Value"
  - "literales XML [Visual Basic]"
  - "literales XML [Visual Basic], modificar"
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Modificar literales XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona las formas adecuadas para modificar literales XML.  Puede agregar o eliminar elementos y atributos, así como reemplazar un elemento existente por un nuevo elemento XML.  En este tema se proporcionan varios ejemplos sobre cómo modificar un literal XML existente.  
  
### Para modificar el valor de un literal XML  
  
1.  Para modificar el valor de un literal XML, obtenga una referencia al literal XML y establezca el valor de la propiedad `Value` en el valor deseado.  
  
     El ejemplo de código siguiente actualiza el valor de todos los elementos \<Price\> de un documento XML.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#4)]  
  
     A continuación se muestra un XML de origen y un XML modificado de ejemplo a partir de este código de ejemplo.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  La propiedad `Value` hace referencia al primer elemento XML de una colección.  Si se establece el valor de la propiedad `Value`, se aplica sólo al primer elemento de una colección cuando hay más de un elemento con el mismo nombre en la colección.  
  
### Para agregar un atributo a un literal XML  
  
1.  Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML.  Después puede agregar un atributo agregando una nueva propiedad de eje de atributo XML.  También puede agregar un nuevo objeto <xref:System.Xml.Linq.XAttribute> al literal XML mediante el método <xref:System.Xml.Linq.XContainer.Add%2A>.  El ejemplo siguiente muestra ambas opciones.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#5)]  
  
     A continuación se muestra un XML de origen y un XML modificado de ejemplo a partir de este código de ejemplo.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     Para obtener más información sobre las propiedades de eje de atributo XML, vea [Propiedad Axis para atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### Para agregar un elemento a un literal XML  
  
1.  Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML.  Después puede agregar un nuevo objeto <xref:System.Xml.Linq.XElement> como el último subelemento del elemento mediante el método <xref:System.Xml.Linq.XContainer.Add%2A>.  Puede agregar un nuevo objeto <xref:System.Xml.Linq.XElement> como el primer subelemento mediante el método <xref:System.Xml.Linq.XContainer.AddFirst%2A>.  
  
     Para agregar un nuevo elemento en una ubicación concreta relativa a otros subelementos, primero obtenga una referencia a un subelemento adyacente.  Después puede agregar el nuevo objeto <xref:System.Xml.Linq.XElement> delante del subelemento adyacente mediante el método <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>.  Asimismo puede agregar el nuevo objeto <xref:System.Xml.Linq.XElement> a continuación del subelemento adyacente mediante el método <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>.  
  
     El ejemplo siguiente muestra ejemplos de cada una de estas técnicas.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#6)]  
  
     A continuación se muestra un XML de origen y un XML modificado de ejemplo a partir de este código de ejemplo.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### Quitar un elemento o atributo de un literal XML  
  
1.  Para quitar un elemento o un atributo de un literal XML, obtenga una referencia al elemento o atributo y llame al método `Remove`, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#7)]  
  
     A continuación se muestra un XML de origen y un XML modificado de ejemplo a partir de este código de ejemplo.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book> </Catalog>  
    ```  
  
     Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al literal XML y llame al método <xref:System.Xml.Linq.XElement.RemoveAll%2A>.  
  
### Para modificar un literal XML  
  
1.  Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento.  Después puede crear un nuevo objeto <xref:System.Xml.Linq.XElement> que tenga un nuevo nombre y pase el nuevo objeto <xref:System.Xml.Linq.XElement> al método <xref:System.Xml.Linq.XNode.ReplaceWith%2A> del objeto <xref:System.Xml.Linq.XElement> existente.  
  
     Si el elemento que reemplaza tiene subelementos que se deben conservar, establezca el valor del nuevo objeto <xref:System.Xml.Linq.XElement> en la propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> del elemento existente.  De esta forma, se establecerá el valor del nuevo elemento en el XML interno del elemento existente.  De lo contrario, puede establecer el valor del nuevo elemento en la propiedad `Value` del elemento existente.  
  
     El ejemplo de código siguiente reemplaza todos los elementos \<Description\> por un elemento \<Abstract\>.  El contenido del elemento \<Description\> se conserva en el nuevo elemento \<Abstract\> mediante el uso de la propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> del objeto <xref:System.Xml.Linq.XElement> \<Description\>.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#8)]  
  
     A continuación se muestra un XML de origen y un XML modificado de ejemplo a partir de este código de ejemplo.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
        <Description>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Description>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <Description>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>     <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>     <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## Vea también  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Cómo: Cargar XML desde un archivo, cadena o secuencia](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)