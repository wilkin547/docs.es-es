---
title: Forma de los documentos WordprocessingML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dfb446b-5a07-4c00-9ab3-a74ba734ff3a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f29ed78062337c7036ada2405fa610ff1f883feb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="shape-of-wordprocessingml-documents-visual-basic"></a><span data-ttu-id="75901-102">Forma de los documentos WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75901-102">Shape of WordprocessingML Documents (Visual Basic)</span></span>
<span data-ttu-id="75901-103">En este tema se presenta la forma XML de un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="75901-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="75901-104">Formatos de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="75901-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="75901-105">El formato de archivo nativo para el sistema Microsoft Office 2007 es XML abierto de Office (comúnmente denominado XML abierto).</span><span class="sxs-lookup"><span data-stu-id="75901-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="75901-106">XML abierto es un formato basado en XML que sigue la norma Ecma y que actualmente está sometido al proceso de estándares ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="75901-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="75901-107">El lenguaje de marcado para los archivos de procesamiento de texto en XML abierto se denomina WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="75901-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="75901-108">Este tutorial usa los archivos de origen WordprocessingML como datos para los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="75901-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="75901-109">Si está utilizando Microsoft Office 2003, puede guardar documentos en el formato XML abierto de Office si ha instalado el Paquete de compatibilidad de Microsoft Office para los formatos de archivo Word, Excel y PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="75901-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="75901-110">Forma de los documentos WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="75901-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="75901-111">Lo primero que hay que comprender es la forma de los documentos WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="75901-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="75901-112">Un documento WordprocessingML contiene un elemento de Body (con el nombre `w:body`) que contiene los párrafos del documento.</span><span class="sxs-lookup"><span data-stu-id="75901-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="75901-113">Cada párrafo contiene una o más ejecuciones de texto (denominadas `w:r`).</span><span class="sxs-lookup"><span data-stu-id="75901-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="75901-114">Cada ejecución de texto contiene uno o más fragmentos de texto (con el nombre `w:t`).</span><span class="sxs-lookup"><span data-stu-id="75901-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="75901-115">A continuación se muestra un documento WordprocessingML muy sencillo:</span><span class="sxs-lookup"><span data-stu-id="75901-115">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="75901-116">Este documento contiene dos párrafos.</span><span class="sxs-lookup"><span data-stu-id="75901-116">This document contains two paragraphs.</span></span> <span data-ttu-id="75901-117">Contienen una ejecución de texto única y cada ejecución de texto contiene un solo fragmento de texto.</span><span class="sxs-lookup"><span data-stu-id="75901-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="75901-118">La forma más sencilla de ver el contenido de un documento WordprocessingML en forma XML es crear un documento mediante Microsoft Word, guardarlo y después ejecutar el siguiente programa que muestra XML en la consola.</span><span class="sxs-lookup"><span data-stu-id="75901-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="75901-119">Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="75901-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="75901-120">Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="75901-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Sub Main()  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
  
        Using wdPackage As Package = _  
          Package.Open("SampleDoc.docx", _  
                       FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage _  
                .GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri( _  
                            New Uri("/", UriKind.Relative), _  
                            docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Get the officeDocument part from the package.  
                ' Load the XML in the part into an XDocument instance.  
                Dim xDoc As XDocument = _  
                    XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
                Console.WriteLine(xDoc.Root)  
            End If  
        End Using  
    End Sub  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="75901-121">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="75901-121">External Resources</span></span>  
 [<span data-ttu-id="75901-122">Introducción a los formatos de archivo Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="75901-122">Introducing the Office (2007) Open XML File Formats</span></span>](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 [<span data-ttu-id="75901-123">Información general de WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="75901-123">Overview of WordprocessingML</span></span>](http://go.microsoft.com/fwlink/?LinkId=98094)  
  
 [<span data-ttu-id="75901-124">Office 2003: página de descargas de esquemas de referencia XML</span><span class="sxs-lookup"><span data-stu-id="75901-124">Office 2003: XML Reference Schemas Download page</span></span>](http://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a><span data-ttu-id="75901-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="75901-125">See Also</span></span>  
 [<span data-ttu-id="75901-126">Tutorial: Manipular contenido en un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75901-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
