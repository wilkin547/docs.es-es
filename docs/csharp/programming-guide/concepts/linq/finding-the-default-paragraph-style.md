---
title: Buscar el estilo de párrafo predeterminado (C#)
description: Aprenda a procesar un documento WordprocessingML con LINQ en C#. En este ejemplo se busca el estilo predeterminado de los párrafos del documento.
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: e18bbbdbd5b2627c9ff4c3c3eedd84d7cb166a62
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103819"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="b3af8-104">Buscar el estilo de párrafo predeterminado (C#)</span><span class="sxs-lookup"><span data-stu-id="b3af8-104">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="b3af8-105">La primera tarea del tutorial Manipular información en un documento WordprocessingML consiste en buscar el estilo predeterminado de los párrafos del documento.</span><span class="sxs-lookup"><span data-stu-id="b3af8-105">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3af8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3af8-106">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b3af8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3af8-107">Description</span></span>  
 <span data-ttu-id="b3af8-108">El siguiente ejemplo abre un documento XML WordprocessingML abierto de Office, busca las partes del documento y del estilo del paquete y ejecuta una consulta que busca el nombre de estilo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b3af8-108">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="b3af8-109">Para obtener información sobre los paquetes Office Open XML y las partes de las que constan, vea [Información de los documentos de WordprocessingML de Office Open XML (C#)](./wordprocessingml-document-with-styles.md).</span><span class="sxs-lookup"><span data-stu-id="b3af8-109">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](./wordprocessingml-document-with-styles.md).</span></span>  
  
 <span data-ttu-id="b3af8-110">La consulta busca un nodo con el nombre `w:style` que tiene un atributo con el nombre `w:type` con un valor de "paragraph" y también un atributo con el nombre `w:default` con un valor de "1".</span><span class="sxs-lookup"><span data-stu-id="b3af8-110">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="b3af8-111">Puesto que sólo habrá un nodo XML con estos atributos, la consulta utiliza el operador <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> para convertir una recopilación en un singleton.</span><span class="sxs-lookup"><span data-stu-id="b3af8-111">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="b3af8-112">A continuación obtiene el valor de un atributo con el nombre `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="b3af8-112">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="b3af8-113">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="b3af8-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="b3af8-114">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3af8-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b3af8-115">Código</span><span class="sxs-lookup"><span data-stu-id="b3af8-115">Code</span></span>  
  
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
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="b3af8-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b3af8-116">Comments</span></span>  
 <span data-ttu-id="b3af8-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b3af8-117">This example produces the following output:</span></span>  
  
```output  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="b3af8-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b3af8-118">Next Steps</span></span>  
 <span data-ttu-id="b3af8-119">En el siguiente ejemplo, creará una consulta similar que busca todos los párrafos de un documento y sus estilos:</span><span class="sxs-lookup"><span data-stu-id="b3af8-119">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="b3af8-120">Recuperar los párrafos y sus estilos (C#)</span><span class="sxs-lookup"><span data-stu-id="b3af8-120">Retrieving the Paragraphs and Their Styles (C#)</span></span>](./retrieving-the-paragraphs-and-their-styles.md)  
