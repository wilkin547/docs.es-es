---
title: Procedimiento para transformar XML mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: dab394ec45567589e002b5d2ac76ec19fb0f76c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374901"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Cómo: Transformar XML usando LINQ (Visual Basic)

Los [literales XML](../../../language-reference/xml-literals/index.md) facilitan la lectura de XML de un origen y su transformación en un nuevo formato XML. Puede aprovechar las consultas LINQ para recuperar el contenido que se va a transformar o cambiar el contenido de un documento existente a un nuevo formato XML.

En el ejemplo de este tema se transforma el contenido de un documento de origen XML a HTML para verlo en un explorador.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a>Para transformar un documento XML

1. En Visual Studio, cree un nuevo proyecto de Visual Basic en la plantilla de proyecto de **aplicación de consola** .

2. Haga doble clic en el archivo Module1. VB creado en el proyecto para modificar el código de Visual Basic. Agregue el código siguiente al `Sub Main` del `Module1` módulo. Este código crea el documento XML de origen como un <xref:System.Xml.Linq.XDocument> objeto.

    ```vb
    Dim catalog =
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
              Get the expert insights, practical code samples,
              and best practices you need
              to advance your expertise with <technology>Visual
              Basic .NET</technology>.
              Learn how to create faster, more reliable applications
              based on professional,
              pragmatic guidance by today's top <audience>developers</audience>.
            </Description>
          </Book>
        </Catalog>
    ```

     [Cómo: cargar XML desde un archivo, una cadena o una secuencia](how-to-load-xml-from-a-file-string-or-stream.md).

3. Después del código para crear el documento XML de origen, agregue el código siguiente para recuperar todos los \<Book> elementos del objeto y transformarlos en un documento HTML. La lista de \<Book> elementos se crea mediante una consulta LINQ que devuelve una colección de <xref:System.Xml.Linq.XElement> objetos que contienen el HTML transformado. Puede utilizar expresiones incrustadas para colocar los valores del documento de origen en el nuevo formato XML.

     El documento HTML resultante se escribe en un archivo mediante el <xref:System.Xml.Linq.XElement.Save%2A> método.

    ```vb
    Dim htmlOutput =
      <html>
        <body>
          <%= From book In catalog.<Catalog>.<Book>
              Select <div>
                       <h1><%= book.<Title>.Value %></h1>
                       <h3><%= "By " & book.<Author>.Value %></h3>
                        <h3><%= "Price = " & book.<Price>.Value %></h3>
                        <h2>Description</h2>
                        <%= TransformDescription(book.<Description>(0)) %>
                        <hr/>
                      </div> %>
        </body>
      </html>

    htmlOutput.Save("BookDescription.html")
    ```

4. Después `Sub Main` de `Module1` , agregue un nuevo método ( `Sub` ) para transformar un \<Description> nodo en el formato HTML especificado. El código del paso anterior llama a este método y se usa para conservar el formato de los \<Description> elementos.

     Este método reemplaza los subelementos del \<Description> elemento con HTML. El `ReplaceWith` método se utiliza para conservar la ubicación de los subelementos. El contenido transformado del \<Description> elemento se incluye en un elemento HTML Paragraph ( \<p> ). La <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad se usa para recuperar el contenido transformado del \<Description> elemento. Esto garantiza que los subelementos se incluyen en el contenido transformado.

     Agregue el código siguiente después `Sub Main` de `Module1` .

    ```vb
    Public Function TransformDescription(ByVal desc As XElement) As XElement

      ' Replace <technology> elements with <b>.
      Dim content = (From element In desc...<technology>).ToList()

      If content.Count > 0 Then
        For i = 0 To content.Count - 1
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)
        Next
      End If

      ' Replace <audience> elements with <i>.
      content = (From element In desc...<audience>).ToList()

      If content.Count > 0 Then
        For i = 0 To content.Count - 1
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)
        Next
      End If

      ' Return the updated contents of the <Description> element.
      Return <p><%= desc.Nodes %></p>
    End Function
    ```

5. Guarde los cambios.

6. Presione F5 para ejecutar el código. El documento guardado resultante tendrá un aspecto similar al siguiente:

    ```html
    <?xml version="1.0"?>
    <html>
      <body>
        <div>
          <h1>XML Developer's Guide</h1>
          <h3>By Garghentini, Davide</h3>
          <h3>Price = 44.95</h3>
          <h2>Description</h2>
          <p>
            An in-depth look at creating applications
            with <b>XML</b>. For
            <i>beginners</i> or
            <i>advanced</i> developers.
          </p>
          <hr />
        </div>
        <div>
          <h1>Developing Applications with Visual Basic .NET</h1>
          <h3>By Spencer, Phil</h3>
          <h3>Price = 45.95</h3>
          <h2>Description</h2>
          <p>
            Get the expert insights, practical code
            samples, and best practices you need
            to advance your expertise with <b>Visual
            Basic .NET</b>. Learn how to create faster,
            more reliable applications based on
            professional, pragmatic guidance by today's
            top <i>developers</i>.
          </p>
          <hr />
        </div>
      </body>
    </html>
    ```

## <a name="see-also"></a>Consulte también

- [Literales XML](../../../language-reference/xml-literals/index.md)
- [Manipular XML en Visual Basic](manipulating-xml.md)
- [XML](index.md)
- [Procedimiento para cargar XML desde un archivo, cadena o secuencia](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Introducción a LINQ en Visual Basic](../linq/introduction-to-linq.md)
