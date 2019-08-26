---
title: Forma de documentos WordprocessingML (C#)
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 84d893267c37ecf99a457ebb683d0451e2b4b68f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591054"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="feb93-102">Forma de documentos WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="feb93-102">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="feb93-103">En este tema se presenta la forma XML de un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="feb93-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="feb93-104">Formatos de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="feb93-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="feb93-105">El formato de archivo nativo para el sistema Microsoft Office 2007 es XML abierto de Office (comúnmente denominado XML abierto).</span><span class="sxs-lookup"><span data-stu-id="feb93-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="feb93-106">XML abierto es un formato basado en XML que sigue la norma Ecma y que actualmente está sometido al proceso de estándares ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="feb93-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="feb93-107">El lenguaje de marcado para los archivos de procesamiento de texto en XML abierto se denomina WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="feb93-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="feb93-108">Este tutorial usa los archivos de origen WordprocessingML como datos para los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="feb93-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="feb93-109">Si está utilizando Microsoft Office 2003, puede guardar documentos en el formato XML abierto de Office si ha instalado el Paquete de compatibilidad de Microsoft Office para los formatos de archivo Word, Excel y PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="feb93-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="feb93-110">Forma de los documentos WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="feb93-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="feb93-111">Lo primero que hay que comprender es la forma de los documentos WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="feb93-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="feb93-112">Un documento WordprocessingML contiene un elemento de Body (con el nombre `w:body`) que contiene los párrafos del documento.</span><span class="sxs-lookup"><span data-stu-id="feb93-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="feb93-113">Cada párrafo contiene una o más ejecuciones de texto (denominadas `w:r`).</span><span class="sxs-lookup"><span data-stu-id="feb93-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="feb93-114">Cada ejecución de texto contiene uno o más fragmentos de texto (con el nombre `w:t`).</span><span class="sxs-lookup"><span data-stu-id="feb93-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="feb93-115">A continuación se muestra un documento WordprocessingML muy sencillo:</span><span class="sxs-lookup"><span data-stu-id="feb93-115">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="feb93-116">Este documento contiene dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="feb93-116">This document contains two paragraphs.</span></span> <span data-ttu-id="feb93-117">Contienen una ejecución de texto única y cada ejecución de texto contiene un solo fragmento de texto.</span><span class="sxs-lookup"><span data-stu-id="feb93-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="feb93-118">La forma más sencilla de ver el contenido de un documento WordprocessingML en forma XML es crear un documento mediante Microsoft Word, guardarlo y después ejecutar el siguiente programa que muestra XML en la consola.</span><span class="sxs-lookup"><span data-stu-id="feb93-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="feb93-119">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="feb93-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="feb93-120">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="feb93-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="feb93-121">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="feb93-121">External Resources</span></span>  
 [<span data-ttu-id="feb93-122">Introducción a los formatos de archivo Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="feb93-122">Introducing the Office (2007) Open XML File Formats</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)  
 [<span data-ttu-id="feb93-123">Información general de WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="feb93-123">Overview of WordprocessingML</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)  
 [<span data-ttu-id="feb93-124">Anatomía de un archivo WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="feb93-124">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)  
 [<span data-ttu-id="feb93-125">Introducción a WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="feb93-125">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)  
 [<span data-ttu-id="feb93-126">Office 2003: página de descarga de esquemas de referencia XML</span><span class="sxs-lookup"><span data-stu-id="feb93-126">Office 2003: XML Reference Schemas Download page</span></span>](https://www.microsoft.com/download/details.aspx?id=101)  
  
## <a name="see-also"></a><span data-ttu-id="feb93-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="feb93-127">See also</span></span>

- [<span data-ttu-id="feb93-128">Tutorial: Manipulación de contenido en un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="feb93-128">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
