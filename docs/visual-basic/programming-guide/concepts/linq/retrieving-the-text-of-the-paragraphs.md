---
title: Recuperar el texto de los párrafos
ms.date: 07/20/2015
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
ms.openlocfilehash: 24167ade2d0326ef9382536f79f9e45eb22c89c5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413393"
---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a>Recuperar el texto de los párrafos (Visual Basic)
Este ejemplo se basa en el ejemplo anterior, [recuperando los párrafos y sus estilos (Visual Basic)](retrieving-the-paragraphs-and-their-styles.md). El nuevo ejemplo recupera el texto de cada párrafo como una cadena.  
  
 Para ello, incorpora una consulta nueva que lleva a cabo una iteración a lo largo de la colección de tipos anónimos y proyecta una nueva colección de un tipo anónimo incluyendo a un nuevo miembro, `Text`. Utiliza el operador de consultas estándar <xref:System.Linq.Enumerable.Aggregate%2A> para concatenar varias cadenas en una sola cadena.  
  
 Esta técnica (es decir, primeramente proyectar una colección de un tipo anónimo para después utilizarla para proyectarla en una colección nueva de un tipo anónimo) es un común y resulta muy útil. Se podría haber escrito esta consulta sin que se realice una proyección en el primer tipo anónimo. Sin embargo, debido a la evaluación aplazada, no se utilizaría mucha potencia de procesamiento adicional en caso de utilizarse. Esta técnica crea objetos de menor duración en la pila de memoria, pero esto no reduce de forma significativa el rendimiento.  
  
 Por supuesto, sería posible escribir una única consulta que contuviese la funcionalidad necesaria para recuperar los párrafos, el estilo de cada uno de ellos y su texto. Sin embargo, a menudo resulta útil dividir una consulta más compleja en múltiples consultas, ya que el código resultante será más modular y fácil de mantener. Y lo que es más, si necesitara reutilizar una parte de esa consulta, resultaría más sencillo refactorizarla si las consultas están escritas de esta forma.  
  
 Estas consultas, que están encadenadas juntas, usan el modelo de procesamiento que se examina en detalle en el tema [Tutorial: ejecución aplazada (Visual Basic)](tutorial-deferred-execution.md).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo procesa un documento WordprocessingML, determinando el nodo elemento, el nombre del estilo y el texto de cada párrafo. Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial. En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.  
  
 Para obtener instrucciones sobre cómo crear el documento de origen para este ejemplo, vea [crear el documento de origen de Office Open XML (Visual Basic)](creating-the-source-office-open-xml-document.md).  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    ' Following function is required because Visual Basic does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = _  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Following is the new query that retrieves the text of  
        ' each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t> _  
                    .Aggregate(New StringBuilder(), _  
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _  
                               Function(s As StringBuilder) s.ToString) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 En este ejemplo se genera el siguiente resultado cuando se aplica al documento descrito en [crear el documento de origen de Office Open XML (Visual Basic)](creating-the-source-office-open-xml-document.md).  
  
```console  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >Imports System<  
StyleName:Code ><  
StyleName:Code >Class Program<  
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >   End Sub<  
StyleName:Code >End Class<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a>Pasos siguientes  
 El siguiente ejemplo muestra cómo utilizar un método de extensión, en vez de <xref:System.Linq.Enumerable.Aggregate%2A>, para concatenar múltiples cadenas en una única cadena.  
  
- [Refactorizar mediante un método de extensión (Visual Basic)](refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a>Vea también

- [Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [Ejecución aplazada y evaluación diferida en LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
