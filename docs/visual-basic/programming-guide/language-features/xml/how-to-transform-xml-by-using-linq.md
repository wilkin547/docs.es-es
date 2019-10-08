---
title: Procedimiento Transformar XML mediante LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 08378775f2c30d8ebfcc4f7ceea6fc3ecb2066e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003265"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="2ea84-102">Procedimiento Transformar XML mediante LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ea84-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="2ea84-103">Los [literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) facilitan la lectura de XML de un origen y su transformación en un nuevo formato XML.</span><span class="sxs-lookup"><span data-stu-id="2ea84-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="2ea84-104">Puede aprovechar las consultas LINQ para recuperar el contenido que se va a transformar o cambiar el contenido de un documento existente a un nuevo formato XML.</span><span class="sxs-lookup"><span data-stu-id="2ea84-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="2ea84-105">En el ejemplo de este tema se transforma el contenido de un documento de origen XML a HTML para verlo en un explorador.</span><span class="sxs-lookup"><span data-stu-id="2ea84-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="2ea84-106">Para transformar un documento XML</span><span class="sxs-lookup"><span data-stu-id="2ea84-106">To transform an XML document</span></span>  
  
1. <span data-ttu-id="2ea84-107">En Visual Studio, cree un nuevo proyecto de Visual Basic en la plantilla de proyecto de **aplicación de consola** .</span><span class="sxs-lookup"><span data-stu-id="2ea84-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2. <span data-ttu-id="2ea84-108">Haga doble clic en el archivo Module1. VB creado en el proyecto para modificar el código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2ea84-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="2ea84-109">Agregue el código siguiente al `Sub Main` del módulo `Module1`.</span><span class="sxs-lookup"><span data-stu-id="2ea84-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="2ea84-110">Este código crea el documento XML de origen como un objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="2ea84-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
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
  
     <span data-ttu-id="2ea84-111">[Cómo: Cargar XML desde un archivo, cadena o secuencia @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="2ea84-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3. <span data-ttu-id="2ea84-112">Después del código para crear el documento XML de origen, agregue el código siguiente para recuperar todos los elementos de > \<Book del objeto y transformarlos en un documento HTML.</span><span class="sxs-lookup"><span data-stu-id="2ea84-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="2ea84-113">La lista de elementos de > \<Book se crea mediante una consulta LINQ que devuelve una colección de objetos <xref:System.Xml.Linq.XElement> que contienen el HTML transformado.</span><span class="sxs-lookup"><span data-stu-id="2ea84-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="2ea84-114">Puede utilizar expresiones incrustadas para colocar los valores del documento de origen en el nuevo formato XML.</span><span class="sxs-lookup"><span data-stu-id="2ea84-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="2ea84-115">El documento HTML resultante se escribe en un archivo mediante el método <xref:System.Xml.Linq.XElement.Save%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ea84-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
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
  
4. <span data-ttu-id="2ea84-116">Después de `Sub Main` de `Module1`, agregue un nuevo método (`Sub`) para transformar un nodo de > \<Description en el formato HTML especificado.</span><span class="sxs-lookup"><span data-stu-id="2ea84-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="2ea84-117">El código del paso anterior llama a este método y se usa para conservar el formato de los elementos de > \<Description.</span><span class="sxs-lookup"><span data-stu-id="2ea84-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="2ea84-118">Este método reemplaza los subelementos del elemento de > \<Description por HTML.</span><span class="sxs-lookup"><span data-stu-id="2ea84-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="2ea84-119">El método `ReplaceWith` se utiliza para conservar la ubicación de los subelementos.</span><span class="sxs-lookup"><span data-stu-id="2ea84-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="2ea84-120">El contenido transformado del elemento de > \<Description se incluye en un elemento de párrafo HTML (> de \<P).</span><span class="sxs-lookup"><span data-stu-id="2ea84-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="2ea84-121">La propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> se usa para recuperar el contenido transformado del elemento > \<Description.</span><span class="sxs-lookup"><span data-stu-id="2ea84-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="2ea84-122">Esto garantiza que los subelementos se incluyen en el contenido transformado.</span><span class="sxs-lookup"><span data-stu-id="2ea84-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="2ea84-123">Agregue el código siguiente después de `Sub Main` de `Module1`.</span><span class="sxs-lookup"><span data-stu-id="2ea84-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
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
  
5. <span data-ttu-id="2ea84-124">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="2ea84-124">Save your changes.</span></span>  
  
6. <span data-ttu-id="2ea84-125">Presione F5 para ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="2ea84-125">Press F5 to run the code.</span></span> <span data-ttu-id="2ea84-126">El documento guardado resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ea84-126">The resulting saved document will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ea84-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ea84-127">See also</span></span>

- [<span data-ttu-id="2ea84-128">Literales XML</span><span class="sxs-lookup"><span data-stu-id="2ea84-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2ea84-129">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ea84-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="2ea84-130">XML</span><span class="sxs-lookup"><span data-stu-id="2ea84-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- <span data-ttu-id="2ea84-131">[Cómo: Cargar XML desde un archivo, cadena o secuencia @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="2ea84-131">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)</span></span>
- [<span data-ttu-id="2ea84-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="2ea84-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="2ea84-133">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ea84-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
