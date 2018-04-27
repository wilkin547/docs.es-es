---
title: Crear XML en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 029ff0a2120809fd4637de5910adaffa60e3b8a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="dda7d-102">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dda7d-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="dda7d-103">Visual Basic permite usar *literales XML* directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="dda7d-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="dda7d-104">La sintaxis de los literales XML representa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos y es similar a la sintaxis XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="dda7d-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="dda7d-105">Esto hace más fácil crear elementos XML, documentos y fragmentos mediante programación porque el código tiene la misma estructura que el XML final.</span><span class="sxs-lookup"><span data-stu-id="dda7d-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dda7d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dda7d-106">In This Section</span></span>  
  
|<span data-ttu-id="dda7d-107">Término</span><span class="sxs-lookup"><span data-stu-id="dda7d-107">Term</span></span>|<span data-ttu-id="dda7d-108">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="dda7d-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="dda7d-109">Introducción a literales XML</span><span class="sxs-lookup"><span data-stu-id="dda7d-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="dda7d-110">Introducción a los literales XML y cómo se relacionan con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dda7d-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="dda7d-111">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="dda7d-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="dda7d-112">Describe cómo utilizar expresiones incrustadas en los literales XML.</span><span class="sxs-lookup"><span data-stu-id="dda7d-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="dda7d-113">Crear literales XML</span><span class="sxs-lookup"><span data-stu-id="dda7d-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="dda7d-114">Describe cómo crear un elemento XML en el código mediante el uso de un literal XML.</span><span class="sxs-lookup"><span data-stu-id="dda7d-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="dda7d-115">Espacio en blanco en literales XML</span><span class="sxs-lookup"><span data-stu-id="dda7d-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="dda7d-116">Describe cómo Visual Basic trata el espacio en blanco en literales XML.</span><span class="sxs-lookup"><span data-stu-id="dda7d-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="dda7d-117">Literales XML y la especificación XML 1.0</span><span class="sxs-lookup"><span data-stu-id="dda7d-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="dda7d-118">Describe cómo la sintaxis de literales XML en Visual Basic se relaciona con la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="dda7d-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="dda7d-119">Incrustar expresiones en literales XML</span><span class="sxs-lookup"><span data-stu-id="dda7d-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="dda7d-120">Describe cómo utilizar expresiones incrustadas en los literales XML para crear contenido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dda7d-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="dda7d-121">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="dda7d-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="dda7d-122">Describe las instrucciones para asignar nombres a elementos y atributos XML.</span><span class="sxs-lookup"><span data-stu-id="dda7d-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dda7d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dda7d-123">See Also</span></span>  
 [<span data-ttu-id="dda7d-124">XML</span><span class="sxs-lookup"><span data-stu-id="dda7d-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
