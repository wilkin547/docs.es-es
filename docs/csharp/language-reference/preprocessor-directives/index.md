---
title: Directivas de preprocesador de C#
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6378c8df794a4ee75e7b5ca283b18b228ba46383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="9d692-102">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="9d692-102">C# preprocessor directives</span></span>
<span data-ttu-id="9d692-103">Esta sección contiene información estas directivas de preprocesador de C#:</span><span class="sxs-lookup"><span data-stu-id="9d692-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="9d692-104">#if</span><span class="sxs-lookup"><span data-stu-id="9d692-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="9d692-105">#else</span><span class="sxs-lookup"><span data-stu-id="9d692-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="9d692-106">#elif</span><span class="sxs-lookup"><span data-stu-id="9d692-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="9d692-107">#endif</span><span class="sxs-lookup"><span data-stu-id="9d692-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="9d692-108">#define</span><span class="sxs-lookup"><span data-stu-id="9d692-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="9d692-109">#undef</span><span class="sxs-lookup"><span data-stu-id="9d692-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="9d692-110">#warning</span><span class="sxs-lookup"><span data-stu-id="9d692-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="9d692-111">#error</span><span class="sxs-lookup"><span data-stu-id="9d692-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="9d692-112">#line</span><span class="sxs-lookup"><span data-stu-id="9d692-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="9d692-113">#region</span><span class="sxs-lookup"><span data-stu-id="9d692-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="9d692-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="9d692-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="9d692-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="9d692-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="9d692-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="9d692-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="9d692-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="9d692-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="9d692-118">Vea cada uno de los temas para obtener más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9d692-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="9d692-119">Aunque el compilador no tiene un preprocesador independiente, las directivas descritas en esta sección se procesan como si hubiera uno.</span><span class="sxs-lookup"><span data-stu-id="9d692-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="9d692-120">Se usan para facilitar la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="9d692-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="9d692-121">A diferencia de las directivas de C y C++, no se pueden usar estas directivas para crear macros.</span><span class="sxs-lookup"><span data-stu-id="9d692-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="9d692-122">Una directiva de preprocesador debe ser la única instrucción en una línea.</span><span class="sxs-lookup"><span data-stu-id="9d692-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d692-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d692-123">See also</span></span>
 [<span data-ttu-id="9d692-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9d692-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9d692-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9d692-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
