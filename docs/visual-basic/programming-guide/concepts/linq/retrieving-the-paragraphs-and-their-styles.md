---
title: Recuperar los párrafos y sus estilos
ms.date: 07/20/2015
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
ms.openlocfilehash: ad904abf9bd94e83b981859662c22787652e294f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413418"
---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a>Recuperar los párrafos y sus estilos (Visual Basic)
En este ejemplo, se escribe una consulta que recupera los nodos de párrafo de un documento WordprocessingML. También identifica el estilo de cada uno de los párrafos.  
  
 Esta consulta se basa en la consulta del ejemplo anterior, [buscando el estilo de párrafo predeterminado (Visual Basic)](finding-the-default-paragraph-style.md), que recupera el estilo predeterminado de la lista de estilos. Esta información es necesaria para que la consulta pueda identificar el estilo de los párrafos que no tienen un estilo establecido explícitamente. Los estilos de párrafo se establecen mediante el elemento `w:pPr`; si un párrafo no contiene este elemento, se formatea con el estilo predeterminado.  
  
 Este tema explica la importancia de algunas partes de la consulta y luego muestra dicha consulta como parte de un ejemplo completo y funcional.  
  
## <a name="example"></a>Ejemplo  
 El origen de la consulta para recuperar todos los párrafos de un documento y sus estilos es de la siguiente manera:  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 Esta expresión es similar al origen de la consulta en el ejemplo anterior, al [Buscar el estilo de párrafo predeterminado (Visual Basic)](finding-the-default-paragraph-style.md). La diferencia principal radica en que usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> en lugar del eje <xref:System.Xml.Linq.XContainer.Elements%2A>. La consulta usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> porque en los documentos que tienen secciones, lo párrafos no serán los secundarios directos del elemento de cuerpo; en su lugar, los párrafos estarán dos niveles por debajo en la jerarquía. Mediante el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>, el código funcionará independientemente de que el documento use secciones o no.  
  
## <a name="example"></a>Ejemplo  
 La consulta usa una cláusula `Let` para determinar el elemento que contiene el nodo de estilo. Si no hay ningún elemento, `styleNode` se establece en `Nothing`:  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 La cláusula `Let` usa primero el eje <xref:System.Xml.Linq.XContainer.Elements%2A> para encontrar todos los elementos llamados `pPr`, luego usa el método de extensión <xref:System.Xml.Linq.Extensions.Elements%2A> para encontrar todos los elementos secundarios llamados `pStyle` y por último usa el operador de consulta estándar <xref:System.Linq.Enumerable.FirstOrDefault%2A> para convertir la colección en un singleton. Si la colección está vacía, `styleNode` se establece en `Nothing`. Se trata de un método útil para buscar el nodo descendiente `pStyle`. Tenga en cuenta que si el nodo secundario `pPr` no existe, el código no produce errores generando una excepción; en su lugar, `styleNode` se establece en `Nothing`, que es el comportamiento deseado de esta cláusula `Let`.  
  
 La consulta proyecta una colección de un tipo anónimo con dos miembros, `StyleName` y `ParagraphNode`.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo procesa un documento WordprocessingML, recuperando los nodos de párrafo a partir de dicho documento. También identifica el estilo de cada uno de los párrafos. Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial. En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.  
  
 Puede encontrar instrucciones para crear el documento de origen para este ejemplo en [crear el documento de origen de Office Open XML (Visual Basic)](creating-the-source-office-open-xml-document.md).  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
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
  
 En este ejemplo se genera el siguiente resultado cuando se aplica al documento descrito en [crear el documento de origen de Office Open XML (Visual Basic)](creating-the-source-office-open-xml-document.md).  
  
```console  
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
 En el siguiente tema, [recuperar el texto de los párrafos (Visual Basic)](retrieving-the-text-of-the-paragraphs.md), creará una consulta para recuperar el texto de los párrafos.  
  
## <a name="see-also"></a>Vea también

- [Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
