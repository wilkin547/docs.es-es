---
title: Forma de documentos WordprocessingML (C#)
description: Conozca el formato de un documento WordprocessingML. En varios ejemplos de C# se usa un documento WordprocessingML.
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 4a7716d775a634c5ad3719714be68fce67d5cbfe
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302352"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="114b1-104">Forma de documentos WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="114b1-104">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="114b1-105">En este tema se presenta la forma XML de un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="114b1-105">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="114b1-106">Formatos de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="114b1-106">Microsoft Office Formats</span></span>  
 <span data-ttu-id="114b1-107">El formato de archivo nativo para el sistema Microsoft Office 2007 es XML abierto de Office (comúnmente denominado XML abierto).</span><span class="sxs-lookup"><span data-stu-id="114b1-107">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="114b1-108">XML abierto es un formato basado en XML que sigue la norma Ecma y que actualmente está sometido al proceso de estándares ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="114b1-108">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="114b1-109">El lenguaje de marcado para los archivos de procesamiento de texto en XML abierto se denomina WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="114b1-109">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="114b1-110">Este tutorial usa los archivos de origen WordprocessingML como datos para los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="114b1-110">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="114b1-111">Si está utilizando Microsoft Office 2003, puede guardar documentos en el formato XML abierto de Office si ha instalado el Paquete de compatibilidad de Microsoft Office para los formatos de archivo Word, Excel y PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="114b1-111">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="114b1-112">Forma de los documentos WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="114b1-112">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="114b1-113">Lo primero que hay que comprender es la forma de los documentos WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="114b1-113">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="114b1-114">Un documento WordprocessingML contiene un elemento de Body (con el nombre `w:body`) que contiene los párrafos del documento.</span><span class="sxs-lookup"><span data-stu-id="114b1-114">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="114b1-115">Cada párrafo contiene una o más ejecuciones de texto (denominadas `w:r`).</span><span class="sxs-lookup"><span data-stu-id="114b1-115">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="114b1-116">Cada ejecución de texto contiene uno o más fragmentos de texto (con el nombre `w:t`).</span><span class="sxs-lookup"><span data-stu-id="114b1-116">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="114b1-117">A continuación se muestra un documento WordprocessingML muy sencillo:</span><span class="sxs-lookup"><span data-stu-id="114b1-117">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="114b1-118">Este documento contiene dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="114b1-118">This document contains two paragraphs.</span></span> <span data-ttu-id="114b1-119">Contienen una ejecución de texto única y cada ejecución de texto contiene un solo fragmento de texto.</span><span class="sxs-lookup"><span data-stu-id="114b1-119">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="114b1-120">La forma más sencilla de ver el contenido de un documento WordprocessingML en forma XML es crear un documento mediante Microsoft Word, guardarlo y después ejecutar el siguiente programa que muestra XML en la consola.</span><span class="sxs-lookup"><span data-stu-id="114b1-120">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="114b1-121">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="114b1-121">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="114b1-122">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="114b1-122">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
## <a name="external-resources"></a><span data-ttu-id="114b1-123">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="114b1-123">External resources</span></span>

- [<span data-ttu-id="114b1-124">Introducción a los formatos de archivo Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="114b1-124">Introducing the Office (2007) Open XML File Formats</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)
- [<span data-ttu-id="114b1-125">Información general de WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="114b1-125">Overview of WordprocessingML</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)
- [<span data-ttu-id="114b1-126">Anatomía de un archivo WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="114b1-126">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)
- [<span data-ttu-id="114b1-127">Introducción a WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="114b1-127">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)

## <a name="see-also"></a><span data-ttu-id="114b1-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="114b1-128">See also</span></span>

- [<span data-ttu-id="114b1-129">Tutorial: Manipulación de contenido en un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="114b1-129">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
