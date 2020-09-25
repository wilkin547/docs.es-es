---
description: Directivas de preprocesador de C#
title: Directivas de preprocesador de C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 210a024a8062f5070b2a500384f51b37c9d802c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157959"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="e223a-103">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="e223a-103">C# preprocessor directives</span></span>

<span data-ttu-id="e223a-104">Esta sección contiene información estas directivas de preprocesador de C#:</span><span class="sxs-lookup"><span data-stu-id="e223a-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="e223a-105">#if</span><span class="sxs-lookup"><span data-stu-id="e223a-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="e223a-106">#else</span><span class="sxs-lookup"><span data-stu-id="e223a-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="e223a-107">#elif</span><span class="sxs-lookup"><span data-stu-id="e223a-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="e223a-108">#endif</span><span class="sxs-lookup"><span data-stu-id="e223a-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="e223a-109">#define</span><span class="sxs-lookup"><span data-stu-id="e223a-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="e223a-110">#undef</span><span class="sxs-lookup"><span data-stu-id="e223a-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="e223a-111">#warning</span><span class="sxs-lookup"><span data-stu-id="e223a-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="e223a-112">#error</span><span class="sxs-lookup"><span data-stu-id="e223a-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="e223a-113">#line</span><span class="sxs-lookup"><span data-stu-id="e223a-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="e223a-114">#region</span><span class="sxs-lookup"><span data-stu-id="e223a-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="e223a-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="e223a-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="e223a-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="e223a-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="e223a-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e223a-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="e223a-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e223a-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="e223a-119">Vea cada uno de los temas para obtener más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e223a-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="e223a-120">Aunque el compilador no tiene un preprocesador independiente, las directivas descritas en esta sección se procesan como si hubiera uno.</span><span class="sxs-lookup"><span data-stu-id="e223a-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="e223a-121">Se usan para facilitar la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="e223a-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="e223a-122">A diferencia de las directivas de C y C++, no se pueden usar estas directivas para crear macros.</span><span class="sxs-lookup"><span data-stu-id="e223a-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="e223a-123">Una directiva de preprocesador debe ser la única instrucción en una línea.</span><span class="sxs-lookup"><span data-stu-id="e223a-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="e223a-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e223a-124">See also</span></span>

- [<span data-ttu-id="e223a-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e223a-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e223a-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e223a-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
