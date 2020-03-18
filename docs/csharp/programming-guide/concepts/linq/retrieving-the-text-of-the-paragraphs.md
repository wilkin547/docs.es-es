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
# <a name="retrieving-the-text-of-the-paragraphs-c"></a><span data-ttu-id="29c41-102">Recuperar el texto de los párrafos (C#)</span><span class="sxs-lookup"><span data-stu-id="29c41-102">Retrieving the Text of the Paragraphs (C#)</span></span>
<span data-ttu-id="29c41-103">Este ejemplo se basa en el ejemplo anterior, [Recuperar los párrafos y sus estilos (C#)](./retrieving-the-paragraphs-and-their-styles.md).</span><span class="sxs-lookup"><span data-stu-id="29c41-103">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (C#)](./retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="29c41-104">El nuevo ejemplo recupera el texto de cada párrafo como una cadena.</span><span class="sxs-lookup"><span data-stu-id="29c41-104">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="29c41-105">Para ello, incorpora una consulta nueva que lleva a cabo una iteración a lo largo de la colección de tipos anónimos y proyecta una nueva colección de un tipo anónimo incluyendo a un nuevo miembro, `Text`.</span><span class="sxs-lookup"><span data-stu-id="29c41-105">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="29c41-106">Utiliza el operador de consultas estándar <xref:System.Linq.Enumerable.Aggregate%2A> para concatenar varias cadenas en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="29c41-106">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="29c41-107">Esta técnica (es decir, primeramente proyectar una colección de un tipo anónimo para después utilizarla para proyectarla en una colección nueva de un tipo anónimo) es un común y resulta muy útil.</span><span class="sxs-lookup"><span data-stu-id="29c41-107">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="29c41-108">Se podría haber escrito esta consulta sin que se realice una proyección en el primer tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="29c41-108">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="29c41-109">Sin embargo, debido a la evaluación aplazada, no se utilizaría mucha potencia de procesamiento adicional en caso de utilizarse.</span><span class="sxs-lookup"><span data-stu-id="29c41-109">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="29c41-110">Esta técnica crea objetos de menor duración en la pila de memoria, pero esto no reduce de forma significativa el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="29c41-110">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="29c41-111">Por supuesto, sería posible escribir una única consulta que contuviese la funcionalidad necesaria para recuperar los párrafos, el estilo de cada uno de ellos y su texto.</span><span class="sxs-lookup"><span data-stu-id="29c41-111">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="29c41-112">Sin embargo, a menudo resulta útil dividir una consulta más compleja en múltiples consultas, ya que el código resultante será más modular y fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="29c41-112">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="29c41-113">Y lo que es más, si necesitara reutilizar una parte de esa consulta, resultaría más sencillo refactorizarla si las consultas están escritas de esta forma.</span><span class="sxs-lookup"><span data-stu-id="29c41-113">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="29c41-114">Estas consultas, que están encadenadas unas a otras, usan el modelo de procesamiento que se describe detalladamente en el tema [Tutorial: Chaining Queries Together (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) (Tutorial: Encadenar consultas juntas (C#)).</span><span class="sxs-lookup"><span data-stu-id="29c41-114">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Chaining Queries Together (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29c41-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29c41-115">Example</span></span>  
 <span data-ttu-id="29c41-116">Este ejemplo procesa un documento WordprocessingML, determinando el nodo elemento, el nombre del estilo y el texto de cada párrafo.</span><span class="sxs-lookup"><span data-stu-id="29c41-116">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="29c41-117">Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="29c41-117">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="29c41-118">En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="29c41-118">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="29c41-119">Para obtener instrucciones sobre cómo crear el documento de origen de este ejemplo, vea [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="29c41-119">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="29c41-120">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="29c41-120">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="29c41-121">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="29c41-121">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
 <span data-ttu-id="29c41-122">Este ejemplo genera el siguiente resultado cuando se aplica al documento descrito en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="29c41-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
## <a name="next-steps"></a><span data-ttu-id="29c41-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="29c41-123">Next Steps</span></span>  
 <span data-ttu-id="29c41-124">El siguiente ejemplo muestra cómo utilizar un método de extensión, en vez de <xref:System.Linq.Enumerable.Aggregate%2A>, para concatenar múltiples cadenas en una única cadena.</span><span class="sxs-lookup"><span data-stu-id="29c41-124">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
- [<span data-ttu-id="29c41-125">Refactorizar mediante un método de extensión (C#)</span><span class="sxs-lookup"><span data-stu-id="29c41-125">Refactoring Using an Extension Method (C#)</span></span>](./refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="29c41-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="29c41-126">See also</span></span>

- [<span data-ttu-id="29c41-127">Tutorial: Manipular contenido en un documento de WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="29c41-127">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="29c41-128">Ejecución aplazada y evaluación diferida en LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="29c41-128">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
