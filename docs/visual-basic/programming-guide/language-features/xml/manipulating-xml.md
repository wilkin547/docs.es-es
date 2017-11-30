---
title: Manipular XML en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 061617524659ac2f8793e2030f26a2d6b2724a64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="cf745-102">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf745-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="cf745-103">Puede usar *literales XML* cargar XML desde un origen externo, como una cadena, un archivo o una secuencia.</span><span class="sxs-lookup"><span data-stu-id="cf745-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="cf745-104">A continuación, puede usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para manipular el XML y usar [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] para consultar el XML.</span><span class="sxs-lookup"><span data-stu-id="cf745-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf745-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf745-105">In This Section</span></span>  
 [<span data-ttu-id="cf745-106">Cargar XML desde un archivo, cadena o secuencia</span><span class="sxs-lookup"><span data-stu-id="cf745-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="cf745-107">Muestra cómo cargar XML en un <xref:System.Xml.Linq.XDocument> o <xref:System.Xml.Linq.XElement> objeto desde un archivo de texto, cadena o secuencia.</span><span class="sxs-lookup"><span data-stu-id="cf745-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="cf745-108">Transformar XML usando LINQ</span><span class="sxs-lookup"><span data-stu-id="cf745-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="cf745-109">Muestra cómo transformar el contenido de un <xref:System.Xml.Linq.XDocument> objeto en un nuevo documento XML.</span><span class="sxs-lookup"><span data-stu-id="cf745-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="cf745-110">Modificar literales XML</span><span class="sxs-lookup"><span data-stu-id="cf745-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="cf745-111">Muestra cómo modificar los elementos, atributos y valores en un literal XML.</span><span class="sxs-lookup"><span data-stu-id="cf745-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cf745-112">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cf745-112">Related Sections</span></span>  
 [<span data-ttu-id="cf745-113">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="cf745-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="cf745-114">Proporciona vínculos a secciones que describen las diversas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="cf745-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="cf745-115">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf745-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="cf745-116">Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cf745-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="cf745-117">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf745-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="cf745-118">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cf745-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="cf745-119">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf745-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="cf745-120">Muestra cómo obtener acceso a partes de un elemento o documento XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cf745-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="cf745-121">XML</span><span class="sxs-lookup"><span data-stu-id="cf745-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="cf745-122">Proporciona vínculos a secciones que describen cómo utilizar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cf745-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf745-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf745-123">See Also</span></span>  
 [<span data-ttu-id="cf745-124">XML</span><span class="sxs-lookup"><span data-stu-id="cf745-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="cf745-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="cf745-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="cf745-126">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf745-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
