---
title: Buscar el estilo de párrafo predeterminado (C#)
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: 702d3906f51b996f59dcd15067702b6de07c60a5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594364"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="03ed9-102">Buscar el estilo de párrafo predeterminado (C#)</span><span class="sxs-lookup"><span data-stu-id="03ed9-102">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="03ed9-103">La primera tarea del tutorial Manipular información en un documento WordprocessingML consiste en buscar el estilo predeterminado de los párrafos del documento.</span><span class="sxs-lookup"><span data-stu-id="03ed9-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03ed9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03ed9-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="03ed9-105">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="03ed9-105">Description</span></span>  
 <span data-ttu-id="03ed9-106">El siguiente ejemplo abre un documento XML WordprocessingML abierto de Office, busca las partes del documento y del estilo del paquete y ejecuta una consulta que busca el nombre de estilo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="03ed9-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="03ed9-107">Para obtener información sobre los paquetes Office Open XML y las partes de las que constan, vea [Details of Office Open XML WordprocessingML Documents (C#)](./wordprocessingml-document-with-styles.md) (Información de los documentos WordprocessingML de Office Open XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="03ed9-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](./wordprocessingml-document-with-styles.md).</span></span>  
  
 <span data-ttu-id="03ed9-108">La consulta busca un nodo con el nombre `w:style` que tiene un atributo con el nombre `w:type` con un valor de "paragraph" y también un atributo con el nombre `w:default` con un valor de "1".</span><span class="sxs-lookup"><span data-stu-id="03ed9-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="03ed9-109">Puesto que sólo habrá un nodo XML con estos atributos, la consulta utiliza el operador <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> para convertir una recopilación en un singleton.</span><span class="sxs-lookup"><span data-stu-id="03ed9-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="03ed9-110">A continuación obtiene el valor de un atributo con el nombre `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="03ed9-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="03ed9-111">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="03ed9-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="03ed9-112">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="03ed9-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="03ed9-113">Código</span><span class="sxs-lookup"><span data-stu-id="03ed9-113">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="03ed9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03ed9-114">Comments</span></span>  
 <span data-ttu-id="03ed9-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="03ed9-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="03ed9-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="03ed9-116">Next Steps</span></span>  
 <span data-ttu-id="03ed9-117">En el siguiente ejemplo, creará una consulta similar que busca todos los párrafos de un documento y sus estilos:</span><span class="sxs-lookup"><span data-stu-id="03ed9-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="03ed9-118">Recuperar los párrafos y sus estilos (C#)</span><span class="sxs-lookup"><span data-stu-id="03ed9-118">Retrieving the Paragraphs and Their Styles (C#)</span></span>](./retrieving-the-paragraphs-and-their-styles.md)  
  