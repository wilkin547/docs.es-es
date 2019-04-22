---
title: Crear XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: d847f589bc47f8ab3d6691666bbd879e795db0c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813046"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="dbf77-102">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbf77-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="dbf77-103">Visual Basic le permite usar *literales XML* directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="dbf77-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="dbf77-104">La sintaxis de literales XML representa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos y es similar a la sintaxis XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="dbf77-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="dbf77-105">Esto facilita la creación de elementos, documentos y fragmentos XML mediante programación porque el código tiene la misma estructura que el XML.</span><span class="sxs-lookup"><span data-stu-id="dbf77-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbf77-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dbf77-106">In This Section</span></span>  
  
|<span data-ttu-id="dbf77-107">Término</span><span class="sxs-lookup"><span data-stu-id="dbf77-107">Term</span></span>|<span data-ttu-id="dbf77-108">Definición</span><span class="sxs-lookup"><span data-stu-id="dbf77-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="dbf77-109">Introducción a literales XML</span><span class="sxs-lookup"><span data-stu-id="dbf77-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="dbf77-110">Introducción a los literales XML y cómo se relacionan con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbf77-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="dbf77-111">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="dbf77-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="dbf77-112">Describe cómo utilizar expresiones incrustadas en los literales XML.</span><span class="sxs-lookup"><span data-stu-id="dbf77-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="dbf77-113">Cómo: Crear literales XML</span><span class="sxs-lookup"><span data-stu-id="dbf77-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="dbf77-114">Describe cómo crear un elemento XML en código mediante un literal XML.</span><span class="sxs-lookup"><span data-stu-id="dbf77-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="dbf77-115">Espacio en blanco en literales XML</span><span class="sxs-lookup"><span data-stu-id="dbf77-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="dbf77-116">Describe cómo Visual Basic trata los espacios en blanco en literales XML.</span><span class="sxs-lookup"><span data-stu-id="dbf77-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="dbf77-117">Literales XML y la especificación XML 1.0</span><span class="sxs-lookup"><span data-stu-id="dbf77-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="dbf77-118">Describe cómo se relaciona con la sintaxis de literales XML en Visual Basic a la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="dbf77-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="dbf77-119">Cómo: Incrustar expresiones en literales XML</span><span class="sxs-lookup"><span data-stu-id="dbf77-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="dbf77-120">Describe cómo utilizar expresiones incrustadas en los literales XML para crear contenido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dbf77-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="dbf77-121">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="dbf77-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="dbf77-122">Describe las instrucciones para asignar nombres a elementos y atributos XML.</span><span class="sxs-lookup"><span data-stu-id="dbf77-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbf77-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbf77-123">See also</span></span>

- [<span data-ttu-id="dbf77-124">XML</span><span class="sxs-lookup"><span data-stu-id="dbf77-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
