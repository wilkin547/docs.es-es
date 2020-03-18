---
title: Recuperar los párrafos y sus estilos (C#)
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 47127b6f1d6bfaa0d8d93333882a0d0b59f1bae6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168302"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a>Recuperar los párrafos y sus estilos (C#)
En este ejemplo, se escribe una consulta que recupera los nodos de párrafo de un documento WordprocessingML. También identifica el estilo de cada uno de los párrafos.  
  
 Esta consulta se basa en la consulta del ejemplo anterior, [Buscar el estilo de párrafo predeterminado (C#)](./finding-the-default-paragraph-style.md), que recupera el estilo predeterminado de la lista de estilos. Esta información es necesaria para que la consulta pueda identificar el estilo de los párrafos que no tienen un estilo establecido explícitamente. Los estilos de párrafo se establecen mediante el elemento `w:pPr`; si un párrafo no contiene este elemento, se formatea con el estilo predeterminado.  
  
 Este tema explica la importancia de algunas partes de la consulta y luego muestra dicha consulta como parte de un ejemplo completo y funcional.  
  
## <a name="example"></a>Ejemplo  
 El origen de la consulta para recuperar todos los párrafos de un documento y sus estilos es de la siguiente manera:  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 Esta expresión es similar al origen de la consulta del ejemplo anterior, [Buscar el estilo de párrafo predeterminado (C#)](./finding-the-default-paragraph-style.md). La diferencia principal radica en que usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> en lugar del eje <xref:System.Xml.Linq.XContainer.Elements%2A>. La consulta usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> porque en los documentos que tienen secciones, lo párrafos no serán los secundarios directos del elemento de cuerpo; en su lugar, los párrafos estarán dos niveles por debajo en la jerarquía. Mediante el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>, el código funcionará independientemente de que el documento use secciones o no.  
  
## <a name="example"></a>Ejemplo  
 La consulta usa una cláusula `let` para determinar el elemento que contiene el nodo de estilo. Si no hay ningún elemento, `styleNode` se establece en `null`:  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 La cláusula `let` usa primero el eje <xref:System.Xml.Linq.XContainer.Elements%2A> para encontrar todos los elementos llamados `pPr`, luego usa el método de extensión <xref:System.Xml.Linq.Extensions.Elements%2A> para encontrar todos los elementos secundarios llamados `pStyle` y por último usa el operador de consulta estándar <xref:System.Linq.Enumerable.FirstOrDefault%2A> para convertir la colección en un singleton. Si la colección está vacía, `styleNode` se establece en `null`. Se trata de un método útil para buscar el nodo descendiente `pStyle`. Tenga en cuenta que si el nodo secundario `pPr` no existe, el código no produce errores generando una excepción; en su lugar, `styleNode` se establece en `null`, que es el comportamiento deseado de esta cláusula `let`.  
  
 La consulta proyecta una colección de un tipo anónimo con dos miembros, `StyleName` y `ParagraphNode`.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo procesa un documento WordprocessingML, recuperando los nodos de párrafo a partir de dicho documento. También identifica el estilo de cada uno de los párrafos. Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial. En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.  
  
 Encontrará instrucciones sobre cómo crear el documento de origen para este ejemplo en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 Este ejemplo genera el siguiente resultado cuando se aplica al documento descrito en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).  
  
```output  
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
 En el tema siguiente, [Recuperar el texto de los párrafos (C#)](./retrieving-the-text-of-the-paragraphs.md), podrá crear una consulta para recuperar el texto de los párrafos.  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Manipular contenido en un documento de WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md)
