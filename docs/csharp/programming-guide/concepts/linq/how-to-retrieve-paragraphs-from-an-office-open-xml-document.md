---
title: "Cómo: Recuperar párrafos de un documento de Office Open XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: cc2687cf-d648-451e-88ac-3847c6c967c8
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c48ab7189840b7d22c53c4f379ab6d8a30d8be88
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2018
---
# <a name="how-to-retrieve-paragraphs-from-an-office-open-xml-document-c"></a><span data-ttu-id="fec5c-102">Cómo: Recuperar párrafos de un documento de Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="fec5c-102">How to: Retrieve Paragraphs from an Office Open XML Document (C#)</span></span>
<span data-ttu-id="fec5c-103">Este tema presenta un ejemplo que abre un documento XML abierto de Office y recupera una colección de todos los párrafos del documento.</span><span class="sxs-lookup"><span data-stu-id="fec5c-103">This topic presents an example that opens an Office Open XML document, and retrieves a collection of all of the paragraphs in the document.</span></span>  
  
 <span data-ttu-id="fec5c-104">Para más información sobre Office Open XML, vea el [SDK de Open XML](https://github.com/OfficeDev/Open-XML-SDK) y [www.ericwhite.com](http://ericwhite.com/).</span><span class="sxs-lookup"><span data-stu-id="fec5c-104">For more information on Office Open XML, see [Open XML SDK](https://github.com/OfficeDev/Open-XML-SDK) and [www.ericwhite.com](http://ericwhite.com/).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fec5c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fec5c-105">Example</span></span>  
 <span data-ttu-id="fec5c-106">Este ejemplo abre un paquete XML abierto de Office y usa las relaciones de dicho paquete para buscar las partes del documento y del estilo.</span><span class="sxs-lookup"><span data-stu-id="fec5c-106">This example opens an Office Open XML package, uses the relationships within the Open XML package to find the document and the style parts.</span></span> <span data-ttu-id="fec5c-107">A continuación, consulta el documento y proyecta una colección de un tipo anónimo que contiene el nodo <xref:System.Xml.Linq.XElement> del párrafo, así como el nombre de estilo y el texto de cada párrafo.</span><span class="sxs-lookup"><span data-stu-id="fec5c-107">It then queries the document, projecting a collection of an anonymous type that contains the paragraph <xref:System.Xml.Linq.XElement> node, the style name of each paragraph, and the text of each paragraph.</span></span>  
  
 <span data-ttu-id="fec5c-108">El ejemplo usa un método de extensión denominado `StringConcatenate`, también proporcionado.</span><span class="sxs-lookup"><span data-stu-id="fec5c-108">The example uses an extension method named `StringConcatenate`, which is also supplied in the example.</span></span>  
  
 <span data-ttu-id="fec5c-109">Para ver un tutorial en el que se explica cómo funciona este ejemplo, consulte [Transformaciones funcionales puras de XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fec5c-109">For a detailed tutorial that explains how this example works, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
 <span data-ttu-id="fec5c-110">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="fec5c-110">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="fec5c-111">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fec5c-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    public static string ParagraphText(XElement e)  
    {  
        XNamespace w = e.Name.Namespace;  
        return e  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .StringConcatenate(element => (string)element);  
    }  
  
    static void Main(string[] args)  
    {  
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
              wdPackage  
              .GetRelationshipsByType(documentRelationshipType)  
              .FirstOrDefault();  
            if (docPackageRelationship != null)  
            {  
                Uri documentUri =  
                    PackUriHelper  
                    .ResolvePartUri(  
                       new Uri("/", UriKind.Relative),  
                             docPackageRelationship.TargetUri);  
                PackagePart documentPart =  
                    wdPackage.GetPart(documentUri);  
  
                //  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
                //  Find the styles part. There will only be one.  
                PackageRelationship styleRelation =  
                  documentPart.GetRelationshipsByType(stylesRelationshipType)  
                  .FirstOrDefault();  
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
                where (string)style.Attribute(w + "type") == "paragraph" &&  
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
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = ParagraphText(para.ParagraphNode)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="fec5c-112">En este ejemplo se genera el resultado siguiente cuando se ejecuta con el documento descrito en [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML [C#]):</span><span class="sxs-lookup"><span data-stu-id="fec5c-112">When run with the sample Open XML document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md), this example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="fec5c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fec5c-113">See Also</span></span>  
 [<span data-ttu-id="fec5c-114">Técnicas de consulta avanzadas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fec5c-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
