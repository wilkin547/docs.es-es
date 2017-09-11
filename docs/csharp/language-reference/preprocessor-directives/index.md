---
title: Directivas de preprocesador de C#
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.preprocessor
dev_langs:
- CSharp
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91bb2daefbc677fad8a3dd93b37aac996234d48c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="77968-102">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="77968-102">C# Preprocessor Directives</span></span>
<span data-ttu-id="77968-103">Esta sección contiene información sobre las siguientes directivas de preprocesador de C#.</span><span class="sxs-lookup"><span data-stu-id="77968-103">This section contains information about the following C# preprocessor directives.</span></span>  
  
 [<span data-ttu-id="77968-104">#if</span><span class="sxs-lookup"><span data-stu-id="77968-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)  
  
 [<span data-ttu-id="77968-105">#else</span><span class="sxs-lookup"><span data-stu-id="77968-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)  
  
 [<span data-ttu-id="77968-106">#elif</span><span class="sxs-lookup"><span data-stu-id="77968-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)  
  
 [<span data-ttu-id="77968-107">#endif</span><span class="sxs-lookup"><span data-stu-id="77968-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)  
  
 [<span data-ttu-id="77968-108">#define</span><span class="sxs-lookup"><span data-stu-id="77968-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)  
  
 [<span data-ttu-id="77968-109">#undef</span><span class="sxs-lookup"><span data-stu-id="77968-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
  
 [<span data-ttu-id="77968-110">#warning</span><span class="sxs-lookup"><span data-stu-id="77968-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)  
  
 [<span data-ttu-id="77968-111">#error</span><span class="sxs-lookup"><span data-stu-id="77968-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)  
  
 [<span data-ttu-id="77968-112">#line</span><span class="sxs-lookup"><span data-stu-id="77968-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)  
  
 [<span data-ttu-id="77968-113">#region</span><span class="sxs-lookup"><span data-stu-id="77968-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)  
  
 [<span data-ttu-id="77968-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="77968-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)  
  
 [<span data-ttu-id="77968-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="77968-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)  
  
 [<span data-ttu-id="77968-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="77968-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="77968-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="77968-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
 <span data-ttu-id="77968-118">Vea cada uno de los temas para obtener más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="77968-118">See the individual topics for more information and examples.</span></span>  
  
 <span data-ttu-id="77968-119">Aunque el compilador no tiene un preprocesador independiente, las directivas descritas en esta sección se procesan como si hubiera uno.</span><span class="sxs-lookup"><span data-stu-id="77968-119">Although the compiler does not have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="77968-120">Se usan para facilitar la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="77968-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="77968-121">A diferencia de las directivas de C y C++, no se pueden usar estas directivas para crear macros.</span><span class="sxs-lookup"><span data-stu-id="77968-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>  
  
 <span data-ttu-id="77968-122">Una directiva de preprocesador debe ser la única instrucción en una línea.</span><span class="sxs-lookup"><span data-stu-id="77968-122">A preprocessor directive must be the only instruction on a line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77968-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="77968-123">See Also</span></span>  
 <span data-ttu-id="77968-124">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="77968-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="77968-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="77968-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

