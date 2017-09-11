---
title: Transformaciones funcionales puras de XML (C#)
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
ms.assetid: 97e8e582-eb3d-4756-bbfb-0899eb688ae4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ee60c400bb9bff719f818ab5a5a0a3c667a1b412
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="pure-functional-transformations-of-xml-c"></a><span data-ttu-id="f4e18-102">Transformaciones funcionales puras de XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f4e18-102">Pure Functional Transformations of XML (C#)</span></span>
<span data-ttu-id="f4e18-103">En esta sección se proporciona un tutorial de transformación funcional para XML.</span><span class="sxs-lookup"><span data-stu-id="f4e18-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="f4e18-104">Incluye explicaciones de los conceptos y las construcciones del lenguaje principales que debe comprender para usar las transformaciones funcionales, y ejemplos de uso de transformaciones funcionales para manipular un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f4e18-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="f4e18-105">Aunque este tutorial proporciona ejemplos de código de LINQ to XML, todos los conceptos subyacentes también se aplican a otras tecnologías de LINQ.</span><span class="sxs-lookup"><span data-stu-id="f4e18-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="f4e18-106">El tutorial [Tutorial: manipular contenido en un documento WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) proporciona una serie de ejemplos, cada uno de los cuales se basa en el anterior.</span><span class="sxs-lookup"><span data-stu-id="f4e18-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="f4e18-107">Esos ejemplos demuestran el enfoque de transformación funcional pura para manipular XML.</span><span class="sxs-lookup"><span data-stu-id="f4e18-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="f4e18-108">Este tutorial presupone un conocimiento práctico de C#.</span><span class="sxs-lookup"><span data-stu-id="f4e18-108">This tutorial assumes a working knowledge of C#.</span></span> <span data-ttu-id="f4e18-109">En este tutorial no se proporciona la semántica detallada de las construcciones del lenguaje, pero se proporcionan vínculos a documentación del lenguaje según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f4e18-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="f4e18-110">También se asume un conocimiento práctico de los conceptos básicos de informática básica y XML, incluyendo espacios de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="f4e18-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4e18-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f4e18-111">In This Section</span></span>  
  
|<span data-ttu-id="f4e18-112">Tema</span><span class="sxs-lookup"><span data-stu-id="f4e18-112">Topic</span></span>|<span data-ttu-id="f4e18-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4e18-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f4e18-114">Introducción a las transformaciones funcionales puras (C#)</span><span class="sxs-lookup"><span data-stu-id="f4e18-114">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="f4e18-115">Describe las transformaciones funcionales y define la terminología relevante.</span><span class="sxs-lookup"><span data-stu-id="f4e18-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="f4e18-116">Tutorial: encadenar cadenas juntas (C#)</span><span class="sxs-lookup"><span data-stu-id="f4e18-116">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)|<span data-ttu-id="f4e18-117">Describe la evaluación diferida y la ejecución aplazada en detalle.</span><span class="sxs-lookup"><span data-stu-id="f4e18-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="f4e18-118">Tutorial: Manipular contenido en un documento de WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="f4e18-118">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="f4e18-119">Un tutorial que demuestra una transformación funcional.</span><span class="sxs-lookup"><span data-stu-id="f4e18-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4e18-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4e18-120">See Also</span></span>  
 [<span data-ttu-id="f4e18-121">Consultar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f4e18-121">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

