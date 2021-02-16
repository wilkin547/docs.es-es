---
description: 'Más información acerca de cómo: transformar XML mediante LINQ (Visual Basic)'
title: Procedimiento para transformar XML mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 67e6f5f94cd71d960f742b660d3f223137bbd6d4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483643"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="294c5-103">Cómo: Transformar XML usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="294c5-103">How to: Transform XML by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="294c5-104">Los [literales XML](../../../language-reference/xml-literals/index.md) facilitan la lectura de XML de un origen y su transformación en un nuevo formato XML.</span><span class="sxs-lookup"><span data-stu-id="294c5-104">[XML Literals](../../../language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="294c5-105">Puede aprovechar las consultas LINQ para recuperar el contenido que se va a transformar o cambiar el contenido de un documento existente a un nuevo formato XML.</span><span class="sxs-lookup"><span data-stu-id="294c5-105">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>

<span data-ttu-id="294c5-106">En el ejemplo de este tema se transforma el contenido de un documento de origen XML a HTML para verlo en un explorador.</span><span class="sxs-lookup"><span data-stu-id="294c5-106">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a><span data-ttu-id="294c5-107">Para transformar un documento XML</span><span class="sxs-lookup"><span data-stu-id="294c5-107">To transform an XML document</span></span>

1. <span data-ttu-id="294c5-108">En Visual Studio, cree un nuevo proyecto de Visual Basic en la plantilla de proyecto de **aplicación de consola** .</span><span class="sxs-lookup"><span data-stu-id="294c5-108">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>

2. <span data-ttu-id="294c5-109">Haga doble clic en el archivo Module1. VB creado en el proyecto para modificar el código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="294c5-109">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="294c5-110">Agregue el código siguiente al `Sub Main` del `Module1` módulo.</span><span class="sxs-lookup"><span data-stu-id="294c5-110">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="294c5-111">Este código crea el documento XML de origen como un <xref:System.Xml.Linq.XDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="294c5-111">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>

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

     <span data-ttu-id="294c5-112">[Cómo: cargar XML desde un archivo, una cadena o una secuencia](how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="294c5-112">[How to: Load XML from a File, String, or Stream](how-to-load-xml-from-a-file-string-or-stream.md).</span></span>

3. <span data-ttu-id="294c5-113">Después del código para crear el documento XML de origen, agregue el código siguiente para recuperar todos los \<Book> elementos del objeto y transformarlos en un documento HTML.</span><span class="sxs-lookup"><span data-stu-id="294c5-113">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="294c5-114">La lista de \<Book> elementos se crea mediante una consulta LINQ que devuelve una colección de <xref:System.Xml.Linq.XElement> objetos que contienen el HTML transformado.</span><span class="sxs-lookup"><span data-stu-id="294c5-114">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="294c5-115">Puede utilizar expresiones incrustadas para colocar los valores del documento de origen en el nuevo formato XML.</span><span class="sxs-lookup"><span data-stu-id="294c5-115">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>

     <span data-ttu-id="294c5-116">El documento HTML resultante se escribe en un archivo mediante el <xref:System.Xml.Linq.XElement.Save%2A> método.</span><span class="sxs-lookup"><span data-stu-id="294c5-116">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>

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

4. <span data-ttu-id="294c5-117">Después `Sub Main` de `Module1` , agregue un nuevo método ( `Sub` ) para transformar un \<Description> nodo en el formato HTML especificado.</span><span class="sxs-lookup"><span data-stu-id="294c5-117">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="294c5-118">El código del paso anterior llama a este método y se usa para conservar el formato de los \<Description> elementos.</span><span class="sxs-lookup"><span data-stu-id="294c5-118">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>

     <span data-ttu-id="294c5-119">Este método reemplaza los subelementos del \<Description> elemento con HTML.</span><span class="sxs-lookup"><span data-stu-id="294c5-119">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="294c5-120">El `ReplaceWith` método se utiliza para conservar la ubicación de los subelementos.</span><span class="sxs-lookup"><span data-stu-id="294c5-120">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="294c5-121">El contenido transformado del \<Description> elemento se incluye en un elemento HTML Paragraph ( \<p> ).</span><span class="sxs-lookup"><span data-stu-id="294c5-121">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="294c5-122">La <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad se usa para recuperar el contenido transformado del \<Description> elemento.</span><span class="sxs-lookup"><span data-stu-id="294c5-122">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="294c5-123">Esto garantiza que los subelementos se incluyen en el contenido transformado.</span><span class="sxs-lookup"><span data-stu-id="294c5-123">This ensures that sub-elements are included in the transformed content.</span></span>

     <span data-ttu-id="294c5-124">Agregue el código siguiente después `Sub Main` de `Module1` .</span><span class="sxs-lookup"><span data-stu-id="294c5-124">Add the following code after `Sub Main` of `Module1`.</span></span>

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

5. <span data-ttu-id="294c5-125">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="294c5-125">Save your changes.</span></span>

6. <span data-ttu-id="294c5-126">Presione F5 para ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="294c5-126">Press F5 to run the code.</span></span> <span data-ttu-id="294c5-127">El documento guardado resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="294c5-127">The resulting saved document will resemble the following:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="294c5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="294c5-128">See also</span></span>

- [<span data-ttu-id="294c5-129">Literales XML</span><span class="sxs-lookup"><span data-stu-id="294c5-129">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="294c5-130">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="294c5-130">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="294c5-131">XML</span><span class="sxs-lookup"><span data-stu-id="294c5-131">XML</span></span>](index.md)
- [<span data-ttu-id="294c5-132">Procedimiento para cargar XML desde un archivo, cadena o secuencia</span><span class="sxs-lookup"><span data-stu-id="294c5-132">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="294c5-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="294c5-133">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="294c5-134">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="294c5-134">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
