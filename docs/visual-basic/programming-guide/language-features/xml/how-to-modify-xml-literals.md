---
title: Procedimiento Modificar literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 003715b04f3a5c0fb41e846beb189f117378ea58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053033"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Procedimiento Modificar literales XML (Visual Basic)

Visual Basic ofrece formas cómodas modificar literales XML. Puede agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente con un nuevo elemento XML. Este tema proporcionan varios ejemplos de cómo modificar un literal XML existente.

### <a name="to-modify-the-value-of-an-xml-literal"></a>Para modificar el valor de un literal XML

1. Para modificar el valor de un literal XML, obtenga una referencia al XML literal y establezca el `Value` propiedad en el valor deseado.

    En el ejemplo de código siguiente se actualiza el valor de todos los \<precio > elementos de un documento XML.

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.

    Origen de XML:

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
    > El `Value` propiedad hace referencia al primer elemento XML de una colección. Si hay más de un elemento que tiene el mismo nombre en una colección, al establecer el `Value` propiedad afecta a solo el primer elemento de la colección.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>Para agregar un atributo a un literal XML

1. Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML. A continuación, puede agregar un atributo mediante la adición de una nueva propiedad de eje de atributo XML. También puede agregar un nuevo <xref:System.Xml.Linq.XAttribute> objeto al XML literal mediante el uso de la <xref:System.Xml.Linq.XContainer.Add%2A> método. El ejemplo siguiente muestra ambas opciones.

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.

    Origen de XML:

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

    Para obtener más información acerca de las propiedades de eje de atributo XML, vea [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).

### <a name="to-add-an-element-to-an-xml-literal"></a>Para agregar un elemento a un literal XML

1. Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML. A continuación, puede agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el último elemento secundario del elemento utilizando el <xref:System.Xml.Linq.XContainer.Add%2A> método. Puede agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el primer elemento secundario mediante el uso de la <xref:System.Xml.Linq.XContainer.AddFirst%2A> método.

    Para agregar un nuevo elemento en una ubicación específica en relación con otros subelementos, primero obtenga una referencia a un subelemento adyacente. A continuación, puede agregar el nuevo <xref:System.Xml.Linq.XElement> objeto antes de que el subelemento adyacente mediante el uso de la <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> método. También puede agregar el nuevo <xref:System.Xml.Linq.XElement> objeto después del subelemento adyacente mediante el uso de la <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> método.

    El ejemplo siguiente muestra ejemplos de cada una de estas técnicas.

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.

    Origen de XML:

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

1. Para quitar un elemento o atributo de un literal XML, obtenga una referencia al elemento o atributo y llamada la `Remove` método, como se muestra en el ejemplo siguiente.

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.

    Origen de XML:

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

    Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al XML literal y llame a la <xref:System.Xml.Linq.XElement.RemoveAll%2A> método.

### <a name="to-modify-an-xml-literal"></a>Para modificar un literal XML

1. Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento. A continuación, puede crear un nuevo <xref:System.Xml.Linq.XElement> objeto que tiene un nuevo nombre y pase el nuevo <xref:System.Xml.Linq.XElement> de objeto para el <xref:System.Xml.Linq.XNode.ReplaceWith%2A> método existente <xref:System.Xml.Linq.XElement> objeto.

    Si el elemento que se va a sustituir tiene los subelementos que deben conservarse, establezca el valor de la nueva <xref:System.Xml.Linq.XElement> de objeto para el <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del elemento existente. Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente. En caso contrario, puede establecer el valor del nuevo elemento a la `Value` propiedad del elemento existente.

    El siguiente ejemplo de código reemplaza toda \<descripción > elementos con un \<abstracta > elemento. El contenido de la \<descripción > elemento se conserva en el nuevo \<abstracta > elemento utilizando el <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad de la \<descripción > <xref:System.Xml.Linq.XElement> objeto.

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.

    Origen de XML:

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
- [Cómo: Cargar XML desde un archivo, cadena o Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
