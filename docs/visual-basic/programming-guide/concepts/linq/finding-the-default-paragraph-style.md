---
title: Buscar el estilo de párrafo predeterminado
ms.date: 07/20/2015
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
ms.openlocfilehash: b70ae72c293d00c4f7b7a2601bfd20b85702b6d5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398082"
---
# <a name="finding-the-default-paragraph-style-visual-basic"></a>Buscar el estilo de párrafo predeterminado (Visual Basic)
La primera tarea del tutorial Manipular información en un documento WordprocessingML consiste en buscar el estilo predeterminado de los párrafos del documento.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Description  
 El siguiente ejemplo abre un documento XML WordprocessingML abierto de Office, busca las partes del documento y del estilo del paquete y ejecuta una consulta que busca el nombre de estilo predeterminado. Para obtener información acerca de los paquetes de documentos XML abierto de Office y las partes de las que constan, vea los [detalles de los documentos WordprocessingML de Office Open XML (Visual Basic)](details-of-office-open-xml-wordprocessingml-documents.md).  
  
 La consulta busca un nodo con el nombre `w:style` que tiene un atributo con el nombre `w:type` con un valor de "paragraph" y también un atributo con el nombre `w:default` con un valor de "1". Puesto que sólo habrá un nodo XML con estos atributos, la consulta utiliza el operador <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> para convertir una recopilación en un singleton. A continuación obtiene el valor de un atributo con el nombre `w:styleId`.  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
### <a name="code"></a>Código  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Comentarios  
 Este ejemplo produce el siguiente resultado:  
  
```console  
The default style is: Normal  
```  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el siguiente ejemplo, creará una consulta similar que busca todos los párrafos de un documento y sus estilos:  
  
- [Recuperar los párrafos y sus estilos (Visual Basic)](retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a>Consulte también

- [Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
