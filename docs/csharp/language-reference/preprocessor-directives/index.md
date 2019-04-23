---
title: Directivas de preprocesador de C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 54067777ed2e92eea263b17cce0d4cdf13ed731d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689325"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="fa5a6-102">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="fa5a6-102">C# preprocessor directives</span></span>
<span data-ttu-id="fa5a6-103">Esta sección contiene información estas directivas de preprocesador de C#:</span><span class="sxs-lookup"><span data-stu-id="fa5a6-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="fa5a6-104">#if</span><span class="sxs-lookup"><span data-stu-id="fa5a6-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="fa5a6-105">#else</span><span class="sxs-lookup"><span data-stu-id="fa5a6-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="fa5a6-106">#elif</span><span class="sxs-lookup"><span data-stu-id="fa5a6-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="fa5a6-107">#endif</span><span class="sxs-lookup"><span data-stu-id="fa5a6-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="fa5a6-108">#define</span><span class="sxs-lookup"><span data-stu-id="fa5a6-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="fa5a6-109">#undef</span><span class="sxs-lookup"><span data-stu-id="fa5a6-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="fa5a6-110">#warning</span><span class="sxs-lookup"><span data-stu-id="fa5a6-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="fa5a6-111">#error</span><span class="sxs-lookup"><span data-stu-id="fa5a6-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="fa5a6-112">#line</span><span class="sxs-lookup"><span data-stu-id="fa5a6-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="fa5a6-113">#region</span><span class="sxs-lookup"><span data-stu-id="fa5a6-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="fa5a6-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="fa5a6-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="fa5a6-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="fa5a6-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="fa5a6-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="fa5a6-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="fa5a6-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="fa5a6-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="fa5a6-118">Vea cada uno de los temas para obtener más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="fa5a6-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="fa5a6-119">Aunque el compilador no tiene un preprocesador independiente, las directivas descritas en esta sección se procesan como si hubiera uno.</span><span class="sxs-lookup"><span data-stu-id="fa5a6-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="fa5a6-120">Se usan para facilitar la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="fa5a6-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="fa5a6-121">A diferencia de las directivas de C y C++, no se pueden usar estas directivas para crear macros.</span><span class="sxs-lookup"><span data-stu-id="fa5a6-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="fa5a6-122">Una directiva de preprocesador debe ser la única instrucción en una línea.</span><span class="sxs-lookup"><span data-stu-id="fa5a6-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa5a6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa5a6-123">See also</span></span>

- [<span data-ttu-id="fa5a6-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fa5a6-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="fa5a6-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fa5a6-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
