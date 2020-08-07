---
title: Refactorizar mediante un método de extensión (C#)
description: Aprenda a refactorizar el código mediante un método de extensión. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
ms.assetid: c5fc123d-af10-4a2f-b8e4-db921efb2639
ms.openlocfilehash: e786f0e1514156535fd6a6033e37ed8879e99709
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381949"
---
# <a name="refactoring-using-an-extension-method-c"></a><span data-ttu-id="17e38-104">Refactorizar mediante un método de extensión (C#)</span><span class="sxs-lookup"><span data-stu-id="17e38-104">Refactoring Using an Extension Method (C#)</span></span>
<span data-ttu-id="17e38-105">Este ejemplo se basa en el ejemplo anterior, [Recuperar el texto de los párrafos (C#)](./retrieving-the-text-of-the-paragraphs.md), mediante la refactorización de la concatenación de cadenas con una función pura que se implementa como método de extensión.</span><span class="sxs-lookup"><span data-stu-id="17e38-105">This example builds on the previous example, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="17e38-106">El ejemplo anterior usaba el operador de consultas estándar <xref:System.Linq.Enumerable.Aggregate%2A> para concatenar varias cadenas en una sola.</span><span class="sxs-lookup"><span data-stu-id="17e38-106">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="17e38-107">Sin embargo, resulta más eficaz escribir un método de extensión a tal efecto, ya que la consulta resultante es más pequeña y más simple.</span><span class="sxs-lookup"><span data-stu-id="17e38-107">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17e38-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e38-108">Example</span></span>  
 <span data-ttu-id="17e38-109">Este ejemplo procesa un documento WordprocessingML, recuperando los párrafos, así como el estilo y el texto de cada párrafo.</span><span class="sxs-lookup"><span data-stu-id="17e38-109">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="17e38-110">Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="17e38-110">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="17e38-111">El ejemplo contiene varias sobrecargas del método `StringConcatenate`.</span><span class="sxs-lookup"><span data-stu-id="17e38-111">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="17e38-112">Encontrará instrucciones sobre cómo crear el documento de origen para este ejemplo en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="17e38-112">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="17e38-113">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="17e38-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="17e38-114">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17e38-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
```  
  
## <a name="example"></a><span data-ttu-id="17e38-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e38-115">Example</span></span>  
 <span data-ttu-id="17e38-116">Hay cuatro sobrecargas del método `StringConcatenate`.</span><span class="sxs-lookup"><span data-stu-id="17e38-116">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="17e38-117">Una sobrecarga simplemente toma una colección de cadenas y devuelve una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="17e38-117">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="17e38-118">Otra sobrecarga puede tomar una colección de cualquier tipo y un delegado que se proyecta de un singleton de la colección a una cadena.</span><span class="sxs-lookup"><span data-stu-id="17e38-118">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="17e38-119">Hay dos sobrecargas más que permiten especificar una cadena de separación.</span><span class="sxs-lookup"><span data-stu-id="17e38-119">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="17e38-120">El código siguiente usa las cuatro sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="17e38-120">The following code uses all four overloads.</span></span>  
  
```csharp  
string[] numbers = { "one", "two", "three" };  
  
Console.WriteLine("{0}", numbers.StringConcatenate());  
Console.WriteLine("{0}", numbers.StringConcatenate(":"));  
  
int[] intNumbers = { 1, 2, 3 };  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString()));  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString(), ":"));  
```  
  
 <span data-ttu-id="17e38-121">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="17e38-121">This example produces the following output:</span></span>  
  
```output  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="17e38-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e38-122">Example</span></span>  
 <span data-ttu-id="17e38-123">Ahora, el ejemplo puede modificarse para aprovechar el nuevo método de extensión:</span><span class="sxs-lookup"><span data-stu-id="17e38-123">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
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
                Text = para  
                       .ParagraphNode  
                       .Elements(w + "r")  
                       .Elements(w + "t")  
                       .StringConcatenate(e => (string)e)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="17e38-124">Este ejemplo genera el siguiente resultado cuando se aplica al documento descrito en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="17e38-124">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
 <span data-ttu-id="17e38-125">Tenga en cuenta que esta refactorización es una variante de refactorizar en una función pura.</span><span class="sxs-lookup"><span data-stu-id="17e38-125">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="17e38-126">El siguiente tema presentará la idea de factorizar en funciones puras con mayor detalle.</span><span class="sxs-lookup"><span data-stu-id="17e38-126">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="17e38-127">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="17e38-127">Next Steps</span></span>  
 <span data-ttu-id="17e38-128">El siguiente ejemplo muestra cómo refactorizar este código de otra forma, mediante las funciones puras:</span><span class="sxs-lookup"><span data-stu-id="17e38-128">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
- [<span data-ttu-id="17e38-129">Refactorizar mediante una función pura (C#)</span><span class="sxs-lookup"><span data-stu-id="17e38-129">Refactoring Using a Pure Function (C#)</span></span>](./refactoring-using-a-pure-function.md)
  
## <a name="see-also"></a><span data-ttu-id="17e38-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17e38-130">See also</span></span>

- [<span data-ttu-id="17e38-131">Tutorial: Manipulación de contenido en un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="17e38-131">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="17e38-132">Refactorizar en funciones puras (C#)</span><span class="sxs-lookup"><span data-stu-id="17e38-132">Refactoring Into Pure Functions (C#)</span></span>](./refactoring-into-pure-functions.md)
