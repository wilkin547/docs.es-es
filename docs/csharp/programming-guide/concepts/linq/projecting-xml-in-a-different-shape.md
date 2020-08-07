---
title: Proyección de XML en una forma distinta (C#)
description: Aprenda a proyectar XML en una forma distinta a la del XML de origen. Revise un ejemplo de código donde se usan las clases del ensamblado WindowsBase.
ms.date: 07/20/2015
ms.assetid: 4cb6b14a-32dc-4a2a-813e-bf9368fa8d86
ms.openlocfilehash: 492c0671b6a81f7e6b8d5f93698f84b88b14bd23
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299102"
---
# <a name="projecting-xml-in-a-different-shape-c"></a><span data-ttu-id="9152a-104">Proyección de XML en una forma distinta (C#)</span><span class="sxs-lookup"><span data-stu-id="9152a-104">Projecting XML in a Different Shape (C#)</span></span>
<span data-ttu-id="9152a-105">Este tema muestra un ejemplo de cómo proyectar un XML cuya apariencia es diferente a la del XML de origen.</span><span class="sxs-lookup"><span data-stu-id="9152a-105">This topic shows an example of projecting XML that is in a different shape than the source XML.</span></span>  
  
 <span data-ttu-id="9152a-106">Muchas de las transformación típicas de un XML consisten en consultas encadenadas, como ocurre en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9152a-106">Many typical XML transformations consist of chained queries, as in this example.</span></span> <span data-ttu-id="9152a-107">Es habitual comenzar con una cierta forma de XML, proyectar los resultados intermedios como colecciones de tipos anónimos o con nombre y, finalmente, proyectar de nuevo los resultados en XML, cuya forma es completamente diferente a la del XML de origen.</span><span class="sxs-lookup"><span data-stu-id="9152a-107">It is common to start with some form of XML, project intermediate results as collections of anonymous types or named types, and then finally to project the results back into XML that is in an entirely different shape than the source XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9152a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9152a-108">Example</span></span>  
 <span data-ttu-id="9152a-109">Este ejemplo procesa un documento WordprocessingML, recuperando los nodos de párrafo a partir de dicho documento.</span><span class="sxs-lookup"><span data-stu-id="9152a-109">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="9152a-110">También identifica el estilo y el texto de cada uno de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="9152a-110">It also identifies the style and text of each paragraph.</span></span> <span data-ttu-id="9152a-111">Por último, el ejemplo proyecta el XML con una forma diferente.</span><span class="sxs-lookup"><span data-stu-id="9152a-111">Finally, the example projects XML with a different shape.</span></span> <span data-ttu-id="9152a-112">Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9152a-112">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="9152a-113">La nueva instrucción encargada de la proyección está señalada en los comentarios del código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9152a-113">The new statement that does the projection is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="9152a-114">Para obtener instrucciones sobre cómo crear el documento de origen de este ejemplo, vea [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="9152a-114">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="9152a-115">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="9152a-115">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="9152a-116">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9152a-116">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
                    Uri styleUri =  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
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
  
        // The following is the new code that projects XML in a new shape.  
        XElement root = new XElement("Root",  
            from p in paraWithText  
            select new XElement("Paragraph",  
                new XElement("StyleName", p.StyleName),  
                new XElement("Text", p.Text)  
            )  
        );  
  
        Console.WriteLine(root);  
    }  
}  
```  
  
 <span data-ttu-id="9152a-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9152a-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Paragraph>  
    <StyleName>Heading1</StyleName>  
    <Text>Parsing WordprocessingML with LINQ to XML</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>The following example prints to the console.</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>using System;</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>class Program {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    public static void (string[] args) {</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>        Console.WriteLine("Hello World");</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>    }</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>}</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text>This example produces the following output:</Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Normal</StyleName>  
    <Text></Text>  
  </Paragraph>  
  <Paragraph>  
    <StyleName>Code</StyleName>  
    <Text>Hello World</Text>  
  </Paragraph>  
</Root>  
```  
  
## <a name="next-steps"></a><span data-ttu-id="9152a-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9152a-118">Next Steps</span></span>  
 <span data-ttu-id="9152a-119">En el siguiente ejemplo, realizará una consulta para buscar todo el texto de un documento de Word:</span><span class="sxs-lookup"><span data-stu-id="9152a-119">In the next example, you'll query to find all the text in a Word document:</span></span>  
  
- [<span data-ttu-id="9152a-120">Buscar texto en documentos de Word (C#)</span><span class="sxs-lookup"><span data-stu-id="9152a-120">Finding Text in Word Documents (C#)</span></span>](./finding-text-in-word-documents.md)  
  