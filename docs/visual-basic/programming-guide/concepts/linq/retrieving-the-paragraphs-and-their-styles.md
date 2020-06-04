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
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a><span data-ttu-id="cb0c1-102">Recuperar los párrafos y sus estilos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb0c1-102">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>
<span data-ttu-id="cb0c1-103">En este ejemplo, se escribe una consulta que recupera los nodos de párrafo de un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="cb0c1-104">También identifica el estilo de cada uno de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="cb0c1-105">Esta consulta se basa en la consulta del ejemplo anterior, [buscando el estilo de párrafo predeterminado (Visual Basic)](finding-the-default-paragraph-style.md), que recupera el estilo predeterminado de la lista de estilos.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="cb0c1-106">Esta información es necesaria para que la consulta pueda identificar el estilo de los párrafos que no tienen un estilo establecido explícitamente.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="cb0c1-107">Los estilos de párrafo se establecen mediante el elemento `w:pPr`; si un párrafo no contiene este elemento, se formatea con el estilo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="cb0c1-108">Este tema explica la importancia de algunas partes de la consulta y luego muestra dicha consulta como parte de un ejemplo completo y funcional.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0c1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb0c1-109">Example</span></span>  
 <span data-ttu-id="cb0c1-110">El origen de la consulta para recuperar todos los párrafos de un documento y sus estilos es de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cb0c1-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 <span data-ttu-id="cb0c1-111">Esta expresión es similar al origen de la consulta en el ejemplo anterior, al [Buscar el estilo de párrafo predeterminado (Visual Basic)](finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c1-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="cb0c1-112">La diferencia principal radica en que usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> en lugar del eje <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="cb0c1-113">La consulta usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A> porque en los documentos que tienen secciones, lo párrafos no serán los secundarios directos del elemento de cuerpo; en su lugar, los párrafos estarán dos niveles por debajo en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="cb0c1-114">Mediante el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>, el código funcionará independientemente de que el documento use secciones o no.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0c1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb0c1-115">Example</span></span>  
 <span data-ttu-id="cb0c1-116">La consulta usa una cláusula `Let` para determinar el elemento que contiene el nodo de estilo.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-116">The query uses a `Let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="cb0c1-117">Si no hay ningún elemento, `styleNode` se establece en `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="cb0c1-117">If there is no element, then `styleNode` is set to `Nothing`:</span></span>  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 <span data-ttu-id="cb0c1-118">La cláusula `Let` usa primero el eje <xref:System.Xml.Linq.XContainer.Elements%2A> para encontrar todos los elementos llamados `pPr`, luego usa el método de extensión <xref:System.Xml.Linq.Extensions.Elements%2A> para encontrar todos los elementos secundarios llamados `pStyle` y por último usa el operador de consulta estándar <xref:System.Linq.Enumerable.FirstOrDefault%2A> para convertir la colección en un singleton.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-118">The `Let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="cb0c1-119">Si la colección está vacía, `styleNode` se establece en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-119">If the collection is empty, `styleNode` is set to `Nothing`.</span></span> <span data-ttu-id="cb0c1-120">Se trata de un método útil para buscar el nodo descendiente `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="cb0c1-121">Tenga en cuenta que si el nodo secundario `pPr` no existe, el código no produce errores generando una excepción; en su lugar, `styleNode` se establece en `Nothing`, que es el comportamiento deseado de esta cláusula `Let`.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `Nothing`, which is the desired behavior of this `Let` clause.</span></span>  
  
 <span data-ttu-id="cb0c1-122">La consulta proyecta una colección de un tipo anónimo con dos miembros, `StyleName` y `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0c1-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb0c1-123">Example</span></span>  
 <span data-ttu-id="cb0c1-124">Este ejemplo procesa un documento WordprocessingML, recuperando los nodos de párrafo a partir de dicho documento.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="cb0c1-125">También identifica el estilo de cada uno de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="cb0c1-126">Este ejemplo se basa en los ejemplos anteriormente vistos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="cb0c1-127">En los comentarios del siguiente código se menciona dónde se encuentra la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="cb0c1-128">Puede encontrar instrucciones para crear el documento de origen para este ejemplo en [crear el documento de origen de Office Open XML (Visual Basic)](creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c1-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="cb0c1-129">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="cb0c1-130">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
 <span data-ttu-id="cb0c1-131">En este ejemplo se genera el siguiente resultado cuando se aplica al documento descrito en [crear el documento de origen de Office Open XML (Visual Basic)](creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c1-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
## <a name="next-steps"></a><span data-ttu-id="cb0c1-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cb0c1-132">Next Steps</span></span>  
 <span data-ttu-id="cb0c1-133">En el siguiente tema, [recuperar el texto de los párrafos (Visual Basic)](retrieving-the-text-of-the-paragraphs.md), creará una consulta para recuperar el texto de los párrafos.</span><span class="sxs-lookup"><span data-stu-id="cb0c1-133">In the next topic, [Retrieving the Text of the Paragraphs (Visual Basic)](retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0c1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb0c1-134">See also</span></span>

- [<span data-ttu-id="cb0c1-135">Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb0c1-135">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
