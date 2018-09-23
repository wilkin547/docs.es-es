---
title: Directivas de preprocesador de C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 1c0a97cabce347be0bc9367f3d090a1fc699db19
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46584664"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="9dc18-102">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="9dc18-102">C# preprocessor directives</span></span>
<span data-ttu-id="9dc18-103">Esta sección contiene información estas directivas de preprocesador de C#:</span><span class="sxs-lookup"><span data-stu-id="9dc18-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="9dc18-104">#if</span><span class="sxs-lookup"><span data-stu-id="9dc18-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="9dc18-105">#else</span><span class="sxs-lookup"><span data-stu-id="9dc18-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="9dc18-106">#elif</span><span class="sxs-lookup"><span data-stu-id="9dc18-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="9dc18-107">#endif</span><span class="sxs-lookup"><span data-stu-id="9dc18-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="9dc18-108">#define</span><span class="sxs-lookup"><span data-stu-id="9dc18-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="9dc18-109">#undef</span><span class="sxs-lookup"><span data-stu-id="9dc18-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="9dc18-110">#warning</span><span class="sxs-lookup"><span data-stu-id="9dc18-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="9dc18-111">#error</span><span class="sxs-lookup"><span data-stu-id="9dc18-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="9dc18-112">#line</span><span class="sxs-lookup"><span data-stu-id="9dc18-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="9dc18-113">#region</span><span class="sxs-lookup"><span data-stu-id="9dc18-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="9dc18-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="9dc18-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="9dc18-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="9dc18-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="9dc18-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="9dc18-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="9dc18-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="9dc18-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="9dc18-118">Vea cada uno de los temas para obtener más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9dc18-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="9dc18-119">Aunque el compilador no tiene un preprocesador independiente, las directivas descritas en esta sección se procesan como si hubiera uno.</span><span class="sxs-lookup"><span data-stu-id="9dc18-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="9dc18-120">Se usan para facilitar la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="9dc18-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="9dc18-121">A diferencia de las directivas de C y C++, no se pueden usar estas directivas para crear macros.</span><span class="sxs-lookup"><span data-stu-id="9dc18-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="9dc18-122">Una directiva de preprocesador debe ser la única instrucción en una línea.</span><span class="sxs-lookup"><span data-stu-id="9dc18-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dc18-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dc18-123">See also</span></span>

- [<span data-ttu-id="9dc18-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9dc18-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9dc18-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9dc18-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
