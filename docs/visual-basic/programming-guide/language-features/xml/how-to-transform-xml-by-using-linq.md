---
title: "Cómo: transformar XML usando LINQ (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9f97466727064ea275c051b5916b0fb297e9e23a
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Cómo: Transformar XML usando LINQ (Visual Basic)
[Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) facilitan la leen datos XML de un origen y transformación a un nuevo formato XML. Puede aprovechar las ventajas de las consultas LINQ para recuperar el contenido para transformar o cambiar el contenido de un documento existente a un nuevo formato XML.  
  
 El ejemplo de este tema transforma el contenido de un documento de origen XML en HTML para visualizarse en un explorador.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>Para transformar un documento XML  
  
1.  En Visual Studio, cree un nuevo proyecto de Visual Basic en el **aplicación de consola** plantilla de proyecto.  
  
2.  Haga doble clic en el archivo Module1.vb creado en el proyecto para modificar el código de Visual Basic. Agregue el código siguiente a la `Sub Main` de la `Module1` módulo. Este código crea el documento de origen XML como un <xref:System.Xml.Linq.XDocument>objeto.</xref:System.Xml.Linq.XDocument>  
  
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
  
     [Cómo: cargar XML desde un archivo, cadena o secuencia](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3.  Después del código para crear el documento XML de origen, agregue el código siguiente para recuperar todos los \<libro > elementos del objeto y transformarlos en un documento HTML. La lista de \<libro > elementos se crea mediante una consulta LINQ que devuelve una colección de <xref:System.Xml.Linq.XElement>objetos que contienen el HTML transformado.</xref:System.Xml.Linq.XElement> Puede utilizar expresiones incrustadas para colocar los valores del documento de origen en el nuevo formato XML.  
  
     El documento HTML resultante se escribe en un archivo utilizando el <xref:System.Xml.Linq.XElement.Save%2A>método.</xref:System.Xml.Linq.XElement.Save%2A>  
  
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
  
4.  Después de `Sub Main` de `Module1`, agregue un nuevo método (`Sub`) para transformar un \<descripción > nodo en el formato HTML especificado. Este método se llama por el código en el paso anterior y se utiliza para conservar el formato de la \<descripción > elementos.  
  
     Este método reemplaza los subelementos de la \<Descripción > elemento HTML. El `ReplaceWith` método se utiliza para conservar la ubicación de los subelementos. El contenido transformado de la \<Descripción > elemento se incluye en un párrafo HTML (\<p >) elemento. El <xref:System.Xml.Linq.XContainer.Nodes%2A>propiedad se utiliza para recuperar el contenido transformado de la \<Descripción > elemento.</xref:System.Xml.Linq.XContainer.Nodes%2A> Esto garantiza que los elementos secundarios se incluyen en el contenido transformado.  
  
     Agregue el código siguiente después de `Sub Main` de `Module1`.  
  
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
  
5.  Guarde los cambios.  
  
6.  Presione F5 para ejecutar el código. El documento guardado resultante será similar al siguiente:  
  
    ```  
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
  
## <a name="see-also"></a>Vea también  
 [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Cómo: cargar XML desde un archivo, cadena o secuencia](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)

