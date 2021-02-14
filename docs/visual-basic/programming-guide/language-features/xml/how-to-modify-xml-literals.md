---
description: 'Más información acerca de cómo: modificar literales XML (Visual Basic)'
title: Procedimiento para modificar literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 23b900c3da5864ac7a91e6c7a43f44a0d4ab1a21
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483617"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Cómo: Modificar literales XML (Visual Basic)

Visual Basic proporciona métodos cómodos para modificar los literales XML. Puede Agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente por un nuevo elemento XML. En este tema se proporcionan varios ejemplos de cómo modificar un literal XML existente.

### <a name="to-modify-the-value-of-an-xml-literal"></a>Para modificar el valor de un literal XML

1. Para modificar el valor de un literal XML, obtenga una referencia al literal XML y establezca la `Value` propiedad en el valor deseado.

    En el siguiente ejemplo de código se actualiza el valor de todos los \<Price> elementos de un documento XML.

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
    > La `Value` propiedad hace referencia al primer elemento XML de una colección. Si hay más de un elemento con el mismo nombre en una colección, el establecimiento de la `Value` propiedad afecta solo al primer elemento de la colección.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>Para agregar un atributo a un literal XML

1. Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML. Después, puede Agregar un atributo agregando una nueva propiedad de eje de atributo XML. También puede Agregar un nuevo <xref:System.Xml.Linq.XAttribute> objeto al literal XML mediante el <xref:System.Xml.Linq.XContainer.Add%2A> método. En el ejemplo siguiente se muestran ambas opciones.

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

    Para obtener más información sobre las propiedades del eje de atributo XML, consulte [propiedad del eje de atributo XML](../../../language-reference/xml-axis/xml-attribute-axis-property.md).

### <a name="to-add-an-element-to-an-xml-literal"></a>Para agregar un elemento a un literal XML

1. Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML. Después, puede Agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el último elemento secundario del elemento mediante el <xref:System.Xml.Linq.XContainer.Add%2A> método. Puede Agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como primer subelemento mediante el <xref:System.Xml.Linq.XContainer.AddFirst%2A> método.

    Para agregar un nuevo elemento en una ubicación específica relativa a otros subelementos, primero obtenga una referencia a un subelemento adyacente. Después, puede Agregar el nuevo <xref:System.Xml.Linq.XElement> objeto delante del subelemento adyacente mediante el <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> método. También puede Agregar el nuevo <xref:System.Xml.Linq.XElement> objeto después del subelemento adyacente mediante el <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> método.

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

1. Para quitar un elemento o un atributo de un literal XML, obtenga una referencia al elemento o atributo y llame al `Remove` método, tal y como se muestra en el ejemplo siguiente.

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

    Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al literal XML y llame al <xref:System.Xml.Linq.XElement.RemoveAll%2A> método.

### <a name="to-modify-an-xml-literal"></a>Para modificar un literal XML

1. Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento. Después, puede crear un nuevo <xref:System.Xml.Linq.XElement> objeto que tenga un nuevo nombre y pasar el nuevo <xref:System.Xml.Linq.XElement> objeto al <xref:System.Xml.Linq.XNode.ReplaceWith%2A> método del <xref:System.Xml.Linq.XElement> objeto existente.

    Si el elemento que va a reemplazar tiene subelementos que deben conservarse, establezca el valor del nuevo <xref:System.Xml.Linq.XElement> objeto en la <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del elemento existente. Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente. De lo contrario, puede establecer el valor del nuevo elemento en la `Value` propiedad del elemento existente.

    En el siguiente ejemplo de código se reemplazan todos los \<Description> elementos por un \<Abstract> elemento. El contenido del \<Description> elemento se conserva en el nuevo \<Abstract> elemento mediante la <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del \<Description> <xref:System.Xml.Linq.XElement> objeto.

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

## <a name="see-also"></a>Consulte también

- [Manipular XML en Visual Basic](manipulating-xml.md)
- [XML](index.md)
- [Procedimiento para cargar XML desde un archivo, cadena o secuencia](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Introducción a LINQ en Visual Basic](../linq/introduction-to-linq.md)
