---
title: Transformaciones funcionales puras de XML
ms.date: 07/20/2015
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
ms.openlocfilehash: 60ec6a5f9c643ea5cc0511f48356d6bfa3ad5748
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396329"
---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="8fd7f-102">Transformaciones funcionales puras de XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fd7f-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="8fd7f-103">En esta sección se proporciona un tutorial de transformación funcional para XML.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="8fd7f-104">Incluye explicaciones de los conceptos y las construcciones del lenguaje principales que debe comprender para usar las transformaciones funcionales, y ejemplos de uso de transformaciones funcionales para manipular un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="8fd7f-105">Aunque este tutorial proporciona ejemplos de código de LINQ to XML, todos los conceptos subyacentes también se aplican a otras tecnologías de LINQ.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="8fd7f-106">En el tutorial [Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) se proporciona una serie de ejemplos, cada uno de los cuales se basa en el anterior.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="8fd7f-107">Esos ejemplos demuestran el enfoque de transformación funcional pura para manipular XML.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="8fd7f-108">En este tutorial se da por supuesto que tiene conocimientos prácticos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="8fd7f-109">En este tutorial no se proporciona la semántica detallada de las construcciones del lenguaje, pero se proporcionan vínculos a documentación del lenguaje según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="8fd7f-110">También se asume un conocimiento práctico de los conceptos básicos de informática básica y XML, incluyendo espacios de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8fd7f-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8fd7f-111">In This Section</span></span>  
  
|<span data-ttu-id="8fd7f-112">Tema</span><span class="sxs-lookup"><span data-stu-id="8fd7f-112">Topic</span></span>|<span data-ttu-id="8fd7f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd7f-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8fd7f-114">Introducción a las transformaciones funcionales puras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fd7f-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](introduction-to-pure-functional-transformations.md)|<span data-ttu-id="8fd7f-115">Describe las transformaciones funcionales y define la terminología relevante.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="8fd7f-116">Tutorial: ejecución aplazada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fd7f-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](tutorial-deferred-execution.md)|<span data-ttu-id="8fd7f-117">Describe la evaluación diferida y la ejecución aplazada en detalle.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="8fd7f-118">Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fd7f-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="8fd7f-119">Un tutorial que demuestra una transformación funcional.</span><span class="sxs-lookup"><span data-stu-id="8fd7f-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fd7f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fd7f-120">See also</span></span>

- [<span data-ttu-id="8fd7f-121">Consultar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fd7f-121">Querying XML Trees (Visual Basic)</span></span>](querying-xml-trees.md)
