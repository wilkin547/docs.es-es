---
title: 'Cómo: Modificar literales XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 17da86d6d10fb1602c16fc2a8c4d6f9f8acf8ff7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Cómo: Modificar literales XML (Visual Basic)
Visual Basic proporciona formas adecuadas para modificar literales XML. Puede agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente con un nuevo elemento XML. Este tema proporciona varios ejemplos de cómo modificar un literal XML existente.  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a>Para modificar el valor de un literal XML  
  
1.  Para modificar el valor de un literal XML, obtenga una referencia al XML literal y establezca el `Value` en el valor deseado.  
  
     En el ejemplo de código siguiente se actualiza el valor de todos los \<precio > elementos en un documento XML.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     A continuación muestra el origen XML de ejemplo y modifica XML de este ejemplo de código.  
  
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
    >  El `Value` propiedad hace referencia al primer elemento XML de una colección. Si hay más de un elemento que tiene el mismo nombre en una colección, al establecer el `Value` propiedad afecta únicamente el primer elemento de la colección.  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a>Para agregar un atributo a un literal XML  
  
1.  Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML. A continuación, puede agregar un atributo mediante la adición de una nueva propiedad de eje de atributo XML. También puede agregar un nuevo <xref:System.Xml.Linq.XAttribute> objeto al XML literal utilizando el <xref:System.Xml.Linq.XContainer.Add%2A> método. El ejemplo siguiente muestra ambas opciones.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     A continuación muestra el origen XML de ejemplo y modifica XML de este ejemplo de código.  
  
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
  
     Para obtener más información acerca de las propiedades de eje de atributo XML, vea [propiedad Axis para atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### <a name="to-add-an-element-to-an-xml-literal"></a>Para agregar un elemento a un literal XML  
  
1.  Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML. A continuación, puede agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el último elemento secundario del elemento mediante el uso de la <xref:System.Xml.Linq.XContainer.Add%2A> método. Puede agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el primer subelemento mediante el uso de la <xref:System.Xml.Linq.XContainer.AddFirst%2A> método.  
  
     Para agregar un nuevo elemento en una ubicación específica en relación con otros subelementos, primero hay que obtener una referencia a un subelemento adyacente. A continuación, puede agregar la nueva <xref:System.Xml.Linq.XElement> objeto antes del subelemento adyacente mediante el uso de la <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> método. También puede agregar la nueva <xref:System.Xml.Linq.XElement> objeto después del subelemento adyacente mediante el uso de la <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> método.  
  
     En el ejemplo siguiente se muestra ejemplos de cada una de estas técnicas.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     A continuación muestra el origen XML de ejemplo y modifica XML de este ejemplo de código.  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>Para quitar un elemento o atributo de un literal XML  
  
1.  Para quitar un elemento o un atributo de un literal XML, obtenga una referencia para el elemento o atributo y llame a la `Remove` método, tal como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     A continuación muestra el origen XML de ejemplo y modifica XML de este ejemplo de código.  
  
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
      </Book></Catalog>  
    ```  
  
     Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al literal XML y llame a la <xref:System.Xml.Linq.XElement.RemoveAll%2A> método.  
  
### <a name="to-modify-an-xml-literal"></a>Para modificar un literal XML  
  
1.  Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento. A continuación, puede crear un nuevo <xref:System.Xml.Linq.XElement> objeto que tiene un nuevo nombre y pase el nuevo <xref:System.Xml.Linq.XElement> el objeto a la <xref:System.Xml.Linq.XNode.ReplaceWith%2A> método existente <xref:System.Xml.Linq.XElement> objeto.  
  
     Si el elemento que se va a sustituir tiene subelementos que se deben mantener, establezca el valor de la nueva <xref:System.Xml.Linq.XElement> el objeto a la <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del elemento existente. Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente. En caso contrario, puede establecer el valor del nuevo elemento a la `Value` propiedad del elemento existente.  
  
     En el ejemplo de código siguiente se reemplaza toda \<descripción > elementos con un \<abstracta > elemento. El contenido de la \<descripción > elemento se conserva en el nuevo \<abstracta > elemento utilizando el <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad de la \<descripción > <xref:System.Xml.Linq.XElement> objeto.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     A continuación muestra el origen XML de ejemplo y modifica XML de este ejemplo de código.  
  
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
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
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
  
## <a name="see-also"></a>Vea también  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Cargar XML desde un archivo, cadena o secuencia](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
