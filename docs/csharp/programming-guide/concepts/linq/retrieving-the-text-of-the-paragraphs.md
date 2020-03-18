---
title: Recuperar el texto de los párrafos (C#)
ms.date: 07/20/2015
ms.assetid: 127d635e-e559-408f-90c8-2bb621ca50ac
ms.openlocfilehash: 7c47420045def3fe973169e01143646c0f60a8eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168250"
---
# <a name="retrieving-the-text-of-the-paragraphs-c"></a>Recuperar el texto de los párrafos (C#)
Este ejemplo se basa en el ejemplo anterior, [Recuperar los párrafos y sus estilos (C#)](./retrieving-the-paragraphs-and-their-styles.md). El nuevo ejemplo recupera el texto de cada párrafo como una cadena.  
  
 Para ello, incorpora una consulta nueva que lleva a cabo una iteración a lo largo de la colección de tipos anónimos y proyecta una nueva colección de un tipo anónimo incluyendo a un nuevo miembro, `Text`. Utiliza el operador de consultas estándar <xref:System.Linq.Enumerable.Aggregate%2A> para concatenar varias cadenas en una sola cadena.  
  
 Esta técnica (es decir, primeramente proyectar una colección de un tipo anónimo para después utilizarla para proyectarla en una colección nueva de un tipo anónimo) es un común y resulta muy útil. Se podría haber escrito esta consulta sin que se realice una proyección en el primer tipo anónimo. Sin embargo, debido a la evaluación aplazada, no se utilizaría mucha potencia de procesamiento adicional en caso de utilizarse. Esta técnica crea objetos de menor duración en la pila de memoria, pero esto no reduce de forma significativa el rendimiento.  
  
 Por supuesto, sería posible escribir una única consulta que contuviese la funcionalidad necesaria para recuperar los párrafos, el estilo de cada uno de ellos y su texto. Sin embargo, a menudo resulta útil dividir una consulta más compleja en múltiples consultas, ya que el código resultante será más modular y fácil de mantener. Y lo que es más, si necesitara reutilizar una parte de esa consulta, resultaría más sencillo refactorizarla si las consultas están escritas de esta forma.  
  
 Estas consultas, que están encadenadas unas a otras, usan el modelo de procesamiento que se describe detalladamente en el tema [Tutorial: Chaining Queries Together (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) (Tutorial: Encadenar consultas juntas (C#)).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo procesa un documento WordprocessingML, determinando el nodo elemento, el nombre del estilo y el texto de cada párrafo. Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial. En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.  
  
 Para obtener instrucciones sobre cómo crear el documento de origen de este ejemplo, vea [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
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
  
// Find all paragraphs in the document.  
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
  
// Following is the new query that retrieves the text of  
// each paragraph.  
var paraWithText =  
    from para in paragraphs  
    select new  
    {  
        ParagraphNode = para.ParagraphNode,  
        StyleName = para.StyleName,  
        Text = para  
               .ParagraphNode  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .Aggregate(  
                   new StringBuilder(),  
                   (s, i) => s.Append((string)i),  
                   s => s.ToString()  
               )  
    };  
  
foreach (var p in paraWithText)  
    Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
```  
  
 Este ejemplo genera el siguiente resultado cuando se aplica al documento descrito en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).  
  
```output  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a>Pasos siguientes  
 El siguiente ejemplo muestra cómo utilizar un método de extensión, en vez de <xref:System.Linq.Enumerable.Aggregate%2A>, para concatenar múltiples cadenas en una única cadena.  
  
- [Refactorizar mediante un método de extensión (C#)](./refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Manipular contenido en un documento de WordprocessingML (C#)](shape-of-wordprocessingml-documents.md)
- [Ejecución aplazada y evaluación diferida en LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
