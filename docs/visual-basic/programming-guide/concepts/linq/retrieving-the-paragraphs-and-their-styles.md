---
title: "Recuperar los párrafos y sus estilos (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bb6d68296a720a796a319502c4cb2f0319727459
ms.lasthandoff: 03/13/2017


---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a>Recuperar los párrafos y sus estilos (Visual Basic)
En este ejemplo, se escribe una consulta que recupera los nodos de párrafo de un documento WordprocessingML. También identifica el estilo de cada uno de los párrafos.  
  
 Esta consulta se basa en la consulta en el ejemplo anterior, [buscar el estilo de párrafo predeterminado (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), que recupera el estilo predeterminado de la lista de estilos. Esta información es necesaria para que la consulta pueda identificar el estilo de los párrafos que no tienen un estilo establecido explícitamente. Los estilos de párrafo se establecen mediante el elemento `w:pPr`; si un párrafo no contiene este elemento, se formatea con el estilo predeterminado.  
  
 Este tema explica la importancia de algunas partes de la consulta y luego muestra dicha consulta como parte de un ejemplo completo y funcional.  
  
## <a name="example"></a>Ejemplo  
 El origen de la consulta para recuperar todos los párrafos de un documento y sus estilos es de la siguiente manera:  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 Esta expresión es similar al origen de la consulta en el ejemplo anterior, [buscar el estilo de párrafo predeterminado (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md). La principal diferencia es que usa el <xref:System.Xml.Linq.XContainer.Descendants%2A>eje en lugar de la <xref:System.Xml.Linq.XContainer.Elements%2A>eje.</xref:System.Xml.Linq.XContainer.Elements%2A> </xref:System.Xml.Linq.XContainer.Descendants%2A> La consulta usa el <xref:System.Xml.Linq.XContainer.Descendants%2A>eje porque en los documentos que tienen secciones, lo párrafos no serán los secundarios directos del elemento body; en su lugar, los párrafos estarán dos niveles por debajo en la jerarquía.</xref:System.Xml.Linq.XContainer.Descendants%2A> Mediante el uso de la <xref:System.Xml.Linq.XContainer.Descendants%2A>eje, el código funcionará si el documento use secciones o no.</xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
## <a name="example"></a>Ejemplo  
 La consulta usa una cláusula `Let` para determinar el elemento que contiene el nodo de estilo. Si no hay ningún elemento, `styleNode` se establece en `Nothing`:  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 El `Let` primero se utiliza la cláusula el <xref:System.Xml.Linq.XContainer.Elements%2A>eje para encontrar todos los elementos llamados `pPr`, a continuación, utiliza el <xref:System.Xml.Linq.Extensions.Elements%2A>método de extensión para encontrar todos los elementos secundarios llamados `pStyle`y por último usa el <xref:System.Linq.Enumerable.FirstOrDefault%2A>operador de consulta estándar para convertir la colección en un singleton.</xref:System.Linq.Enumerable.FirstOrDefault%2A> </xref:System.Xml.Linq.Extensions.Elements%2A> </xref:System.Xml.Linq.XContainer.Elements%2A> Si la colección está vacía, `styleNode` se establece en `Nothing`. Se trata de un método útil para buscar el nodo descendiente `pStyle`. Tenga en cuenta que si el nodo secundario `pPr` no existe, el código no produce errores generando una excepción; en su lugar, `styleNode` se establece en `Nothing`, que es el comportamiento deseado de esta cláusula `Let`.  
  
 La consulta proyecta una colección de un tipo anónimo con dos miembros, `StyleName` y `ParagraphNode`.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo procesa un documento WordprocessingML, recuperando los nodos de párrafo a partir de dicho documento. También identifica el estilo de cada uno de los párrafos. Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial. En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.  
  
 Puede encontrar instrucciones para crear el documento de origen para este ejemplo en [crear Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos en el <xref:System.IO.Packaging?displayProperty=fullName>espacio de nombres.</xref:System.IO.Packaging?displayProperty=fullName>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
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
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado cuando se aplica al documento descrito en [crear Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el tema siguiente, [recuperar el texto de los párrafos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), podrá crear una consulta para recuperar el texto de los párrafos.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Manipular contenido en un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
