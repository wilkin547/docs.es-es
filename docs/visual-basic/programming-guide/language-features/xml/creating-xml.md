---
title: Crear XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 46f9174e78cc67c1e352d02ac6b5038f5da01086
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504674"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="164f6-102">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="164f6-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="164f6-103">Visual Basic le permite usar *literales XML* directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="164f6-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="164f6-104">La sintaxis de literales XML representa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos y es similar a la sintaxis XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="164f6-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="164f6-105">Esto facilita la creación de elementos, documentos y fragmentos XML mediante programación porque el código tiene la misma estructura que el XML.</span><span class="sxs-lookup"><span data-stu-id="164f6-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="164f6-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="164f6-106">In This Section</span></span>  
  
|<span data-ttu-id="164f6-107">Término</span><span class="sxs-lookup"><span data-stu-id="164f6-107">Term</span></span>|<span data-ttu-id="164f6-108">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="164f6-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="164f6-109">Introducción a literales XML</span><span class="sxs-lookup"><span data-stu-id="164f6-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="164f6-110">Introducción a los literales XML y cómo se relacionan con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="164f6-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="164f6-111">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="164f6-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="164f6-112">Describe cómo utilizar expresiones incrustadas en los literales XML.</span><span class="sxs-lookup"><span data-stu-id="164f6-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="164f6-113">Crear literales XML</span><span class="sxs-lookup"><span data-stu-id="164f6-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="164f6-114">Describe cómo crear un elemento XML en código mediante un literal XML.</span><span class="sxs-lookup"><span data-stu-id="164f6-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="164f6-115">Espacio en blanco en literales XML</span><span class="sxs-lookup"><span data-stu-id="164f6-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="164f6-116">Describe cómo Visual Basic trata los espacios en blanco en literales XML.</span><span class="sxs-lookup"><span data-stu-id="164f6-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="164f6-117">Literales XML y la especificación XML 1.0</span><span class="sxs-lookup"><span data-stu-id="164f6-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="164f6-118">Describe cómo se relaciona con la sintaxis de literales XML en Visual Basic a la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="164f6-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="164f6-119">Incrustar expresiones en literales XML</span><span class="sxs-lookup"><span data-stu-id="164f6-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="164f6-120">Describe cómo utilizar expresiones incrustadas en los literales XML para crear contenido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="164f6-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="164f6-121">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="164f6-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="164f6-122">Describe las instrucciones para asignar nombres a elementos y atributos XML.</span><span class="sxs-lookup"><span data-stu-id="164f6-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="164f6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="164f6-123">See Also</span></span>  
 [<span data-ttu-id="164f6-124">XML</span><span class="sxs-lookup"><span data-stu-id="164f6-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
