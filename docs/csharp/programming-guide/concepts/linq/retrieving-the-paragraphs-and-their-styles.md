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
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="18c78-102">Recuperar los párrafos y sus estilos (C#)</span><span class="sxs-lookup"><span data-stu-id="18c78-102">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="18c78-103">En este ejemplo, se escribe una consulta que recupera los nodos de párrafo de un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="18c78-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="18c78-104">También identifica el estilo de cada uno de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="18c78-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="18c78-105">Esta consulta se basa en la consulta del ejemplo anterior, [Buscar el estilo de párrafo predeterminado (C#)](./finding-the-default-paragraph-style.md), que recupera el estilo predeterminado de la lista de estilos.</span><span class="sxs-lookup"><span data-stu-id="18c78-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="18c78-106">Esta información es necesaria para que la consulta pueda identificar el estilo de los párrafos que no tienen un estilo establecido explícitamente.</span><span class="sxs-lookup"><span data-stu-id="18c78-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="18c78-107">Los estilos de párrafo se establecen mediante el elemento `w:pPr`; si un párrafo no contiene este elemento, se formatea con el estilo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="18c78-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="18c78-108">Este tema explica la importancia de algunas partes de la consulta y luego muestra dicha consulta como parte de un ejemplo completo y funcional.</span><span class="sxs-lookup"><span data-stu-id="18c78-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18c78-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18c78-109">Example</span></span>  
 <span data-ttu-id="18c78-110">El origen de la consulta para recuperar todos los párrafos de un documento y sus estilos es de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="18c78-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="18c78-111">Esta expresión es similar al origen de la consulta del ejemplo anterior, [Buscar el estilo de párrafo predeterminado (C#)](./finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="18c78-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="18c78-112">La diferencia principal radica en que usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> en lugar del eje <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="18c78-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="18c78-113">La consulta usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> porque en los documentos que tienen secciones, lo párrafos no serán los secundarios directos del elemento de cuerpo; en su lugar, los párrafos estarán dos niveles por debajo en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="18c78-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="18c78-114">Mediante el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>, el código funcionará independientemente de que el documento use secciones o no.</span><span class="sxs-lookup"><span data-stu-id="18c78-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18c78-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18c78-115">Example</span></span>  
 <span data-ttu-id="18c78-116">La consulta usa una cláusula `let` para determinar el elemento que contiene el nodo de estilo.</span><span class="sxs-lookup"><span data-stu-id="18c78-116">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="18c78-117">Si no hay ningún elemento, `styleNode` se establece en `null`:</span><span class="sxs-lookup"><span data-stu-id="18c78-117">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="18c78-118">La cláusula `let` usa primero el eje <xref:System.Xml.Linq.XContainer.Elements%2A> para encontrar todos los elementos llamados `pPr`, luego usa el método de extensión <xref:System.Xml.Linq.Extensions.Elements%2A> para encontrar todos los elementos secundarios llamados `pStyle` y por último usa el operador de consulta estándar <xref:System.Linq.Enumerable.FirstOrDefault%2A> para convertir la colección en un singleton.</span><span class="sxs-lookup"><span data-stu-id="18c78-118">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="18c78-119">Si la colección está vacía, `styleNode` se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="18c78-119">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="18c78-120">Se trata de un método útil para buscar el nodo descendiente `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="18c78-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="18c78-121">Tenga en cuenta que si el nodo secundario `pPr` no existe, el código no produce errores generando una excepción; en su lugar, `styleNode` se establece en `null`, que es el comportamiento deseado de esta cláusula `let`.</span><span class="sxs-lookup"><span data-stu-id="18c78-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="18c78-122">La consulta proyecta una colección de un tipo anónimo con dos miembros, `StyleName` y `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="18c78-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18c78-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18c78-123">Example</span></span>  
 <span data-ttu-id="18c78-124">Este ejemplo procesa un documento WordprocessingML, recuperando los nodos de párrafo a partir de dicho documento.</span><span class="sxs-lookup"><span data-stu-id="18c78-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="18c78-125">También identifica el estilo de cada uno de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="18c78-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="18c78-126">Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="18c78-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="18c78-127">En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="18c78-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="18c78-128">Encontrará instrucciones sobre cómo crear el documento de origen para este ejemplo en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="18c78-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="18c78-129">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="18c78-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="18c78-130">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18c78-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
 <span data-ttu-id="18c78-131">Este ejemplo genera el siguiente resultado cuando se aplica al documento descrito en [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md) (Creación del documento de origen de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="18c78-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
## <a name="next-steps"></a><span data-ttu-id="18c78-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="18c78-132">Next Steps</span></span>  
 <span data-ttu-id="18c78-133">En el tema siguiente, [Recuperar el texto de los párrafos (C#)](./retrieving-the-text-of-the-paragraphs.md), podrá crear una consulta para recuperar el texto de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="18c78-133">In the next topic, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c78-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="18c78-134">See also</span></span>

- [<span data-ttu-id="18c78-135">Tutorial: Manipular contenido en un documento de WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="18c78-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
