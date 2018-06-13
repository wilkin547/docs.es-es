---
title: Manipular XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: 4be24afe17e60c6c849530f1b892651a1f78399c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650418"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="71a68-102">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71a68-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="71a68-103">Puede usar *literales XML* cargar XML desde un origen externo, como una cadena, un archivo o una secuencia.</span><span class="sxs-lookup"><span data-stu-id="71a68-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="71a68-104">A continuación, puede usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para manipular el XML y usar [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] para consultar el XML.</span><span class="sxs-lookup"><span data-stu-id="71a68-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="71a68-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="71a68-105">In This Section</span></span>  
 [<span data-ttu-id="71a68-106">Cargar XML desde un archivo, cadena o secuencia</span><span class="sxs-lookup"><span data-stu-id="71a68-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="71a68-107">Muestra cómo cargar XML en un <xref:System.Xml.Linq.XDocument> o <xref:System.Xml.Linq.XElement> objeto desde un archivo de texto, cadena o secuencia.</span><span class="sxs-lookup"><span data-stu-id="71a68-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="71a68-108">Transformar XML usando LINQ</span><span class="sxs-lookup"><span data-stu-id="71a68-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="71a68-109">Muestra cómo transformar el contenido de un <xref:System.Xml.Linq.XDocument> objeto en un nuevo documento XML.</span><span class="sxs-lookup"><span data-stu-id="71a68-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="71a68-110">Modificar literales XML</span><span class="sxs-lookup"><span data-stu-id="71a68-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="71a68-111">Muestra cómo modificar los elementos, atributos y valores en un literal XML.</span><span class="sxs-lookup"><span data-stu-id="71a68-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="71a68-112">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="71a68-112">Related Sections</span></span>  
 [<span data-ttu-id="71a68-113">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="71a68-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="71a68-114">Proporciona vínculos a secciones que describen las diversas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="71a68-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="71a68-115">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71a68-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="71a68-116">Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="71a68-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="71a68-117">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71a68-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="71a68-118">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="71a68-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="71a68-119">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71a68-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="71a68-120">Muestra cómo obtener acceso a partes de un elemento o documento XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="71a68-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="71a68-121">XML</span><span class="sxs-lookup"><span data-stu-id="71a68-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="71a68-122">Proporciona vínculos a secciones que describen cómo utilizar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="71a68-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a68-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="71a68-123">See Also</span></span>  
 [<span data-ttu-id="71a68-124">XML</span><span class="sxs-lookup"><span data-stu-id="71a68-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="71a68-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="71a68-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="71a68-126">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71a68-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
