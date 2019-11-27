---
title: 'Cómo: Modificar literales XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330856"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Cómo: Modificar literales XML (Visual Basic)

Visual Basic proporciona métodos cómodos para modificar los literales XML. Puede Agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente por un nuevo elemento XML. En este tema se proporcionan varios ejemplos de cómo modificar un literal XML existente.

### <a name="to-modify-the-value-of-an-xml-literal"></a>Para modificar el valor de un literal XML

1. Para modificar el valor de un literal XML, obtenga una referencia al literal XML y establezca la propiedad `Value` en el valor deseado.

    En el siguiente ejemplo de código se actualiza el valor de todos los elementos de \<Price > de un documento XML.

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.

    XML de origen:

    ```xml
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
    ```

    XML modificado:

    ```xml
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
    > La propiedad `Value` hace referencia al primer elemento XML de una colección. Si hay más de un elemento con el mismo nombre en una colección, el establecimiento de la propiedad `Value` afecta solo al primer elemento de la colección.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>Para agregar un atributo a un literal XML

1. Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML. Después, puede Agregar un atributo agregando una nueva propiedad de eje de atributo XML. También puede Agregar un nuevo objeto <xref:System.Xml.Linq.XAttribute> al literal XML mediante el método <xref:System.Xml.Linq.XContainer.Add%2A>. En el ejemplo siguiente se muestran ambas opciones.

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.

    XML de origen:

    ```xml
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
    ```

    XML modificado:

    ```xml
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

    Para obtener más información sobre las propiedades del eje de atributo XML, consulte [propiedad del eje de atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).

### <a name="to-add-an-element-to-an-xml-literal"></a>Para agregar un elemento a un literal XML

1. Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML. Después, puede Agregar un nuevo objeto <xref:System.Xml.Linq.XElement> como el último elemento secundario del elemento mediante el método <xref:System.Xml.Linq.XContainer.Add%2A>. Puede Agregar un nuevo objeto <xref:System.Xml.Linq.XElement> como primer subelemento mediante el método <xref:System.Xml.Linq.XContainer.AddFirst%2A>.

    Para agregar un nuevo elemento en una ubicación específica relativa a otros subelementos, primero obtenga una referencia a un subelemento adyacente. Después, puede Agregar el nuevo objeto <xref:System.Xml.Linq.XElement> antes del subelemento adyacente mediante el método <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>. También puede Agregar el nuevo objeto <xref:System.Xml.Linq.XElement> después del subelemento adyacente mediante el método <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>.

    En el ejemplo siguiente se muestran ejemplos de cada una de estas técnicas.

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.

    XML de origen:

    ```xml
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
    ```

    XML modificado:

    ```xml
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

1. Para quitar un elemento o un atributo de un literal XML, obtenga una referencia al elemento o atributo y llame al método `Remove`, como se muestra en el ejemplo siguiente.

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.

    XML de origen:

    ```xml
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
    ```

    XML modificado:

    ```xml
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

    Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al literal XML y llame al método <xref:System.Xml.Linq.XElement.RemoveAll%2A>.

### <a name="to-modify-an-xml-literal"></a>Para modificar un literal XML

1. Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento. Después, puede crear un nuevo objeto <xref:System.Xml.Linq.XElement> con un nuevo nombre y pasar el nuevo objeto <xref:System.Xml.Linq.XElement> al método <xref:System.Xml.Linq.XNode.ReplaceWith%2A> del objeto <xref:System.Xml.Linq.XElement> existente.

    Si el elemento que se va a reemplazar tiene subelementos que se deben conservar, establezca el valor del nuevo objeto <xref:System.Xml.Linq.XElement> en la propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> del elemento existente. Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente. De lo contrario, puede establecer el valor del nuevo elemento en la propiedad `Value` del elemento existente.

    En el ejemplo de código siguiente se reemplazan todos los elementos de la descripción \<> por un elemento \<Abstract >. El contenido de la \<Descripción > elemento se conserva en el nuevo elemento \<Abstract > mediante la propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> de la descripción \<> objeto <xref:System.Xml.Linq.XElement>.

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.

    XML de origen:

    ```xml
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
    ```

    XML modificado:

    ```xml
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

- [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Cargar XML desde un archivo, cadena o secuencia](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
