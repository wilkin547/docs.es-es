---
title: 'Tutorial: Manipular contenido en un documento WordprocessingML (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bc9815f8-13d2-4f50-a4d1-b1c0d50d37b3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 293e8de848f83517211e3f3ed640102a2c534764
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-c"></a><span data-ttu-id="a28e6-102">Tutorial: Manipular contenido en un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-102">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>
<span data-ttu-id="a28e6-103">En este tutorial se muestra cómo aplicar el enfoque de transformación funcional y LINQ to XML para manipular documentos XML.</span><span class="sxs-lookup"><span data-stu-id="a28e6-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="a28e6-104">Los ejemplos de C# consultan y manipulan información en documentos WordprocessingML de Office Open XML que guarda Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="a28e6-104">The C# examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="a28e6-105">Para obtener más información, visite el sitio web [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573).</span><span class="sxs-lookup"><span data-stu-id="a28e6-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a28e6-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a28e6-106">In This Section</span></span>  
  
|<span data-ttu-id="a28e6-107">Tema</span><span class="sxs-lookup"><span data-stu-id="a28e6-107">Topic</span></span>|<span data-ttu-id="a28e6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a28e6-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a28e6-109">Forma de documentos WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-109">Shape of WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="a28e6-110">Proporciona una explicación rápida de los detalles de un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="a28e6-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="a28e6-111">Crear el documento de origen de Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-111">Creating the Source Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="a28e6-112">Proporciona instrucciones paso a paso para crear el documento de origen para consultas de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a28e6-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="a28e6-113">Buscar el estilo de párrafo predeterminado (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-113">Finding the Default Paragraph Style (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="a28e6-114">Muestra una consulta para buscar el nombre del estilo predeterminado para un documento.</span><span class="sxs-lookup"><span data-stu-id="a28e6-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="a28e6-115">Recuperar los párrafos y sus estilos (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-115">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="a28e6-116">Muestra una consulta que recupera una recopilación de los párrafos de un documento.</span><span class="sxs-lookup"><span data-stu-id="a28e6-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="a28e6-117">Recuperar el texto de los párrafos (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-117">Retrieving the Text of the Paragraphs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="a28e6-118">Amplía la consulta anterior para recuperar el texto de cada párrafo.</span><span class="sxs-lookup"><span data-stu-id="a28e6-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="a28e6-119">Refactorizar mediante un método de extensión (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-119">Refactoring Using an Extension Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="a28e6-120">Simplifica el código refactorizando mediante un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="a28e6-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="a28e6-121">Refactorizar mediante una función pura (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-121">Refactoring Using a Pure Function (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="a28e6-122">Simplifica más el código refactorizando mediante una función pura.</span><span class="sxs-lookup"><span data-stu-id="a28e6-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="a28e6-123">Proyectar XML en una forma distinta (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-123">Projecting XML in a Different Shape (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="a28e6-124">Completa una transformación XML proyectando XML de una forma diferente que el documento original.</span><span class="sxs-lookup"><span data-stu-id="a28e6-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="a28e6-125">Buscar texto en documentos de Word (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-125">Finding Text in Word Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="a28e6-126">Utiliza las consultas anteriores para buscar en un documento una cadena de texto especificada.</span><span class="sxs-lookup"><span data-stu-id="a28e6-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="a28e6-127">Detalles de los documentos de WordprocessingML de Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-127">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="a28e6-128">Proporciona algunos detalles de los documentos WordprocessingML XML abierto de Office.</span><span class="sxs-lookup"><span data-stu-id="a28e6-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a28e6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a28e6-129">See Also</span></span>  
 <span data-ttu-id="a28e6-130">[Transformaciones funcionales puras de XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a28e6-130">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
 [<span data-ttu-id="a28e6-131">Introducción a las transformaciones funcionales puras (C#)</span><span class="sxs-lookup"><span data-stu-id="a28e6-131">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)

