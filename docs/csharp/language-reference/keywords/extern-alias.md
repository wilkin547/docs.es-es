---
title: 'alias externo: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 8a33b466bbe75b84d6cd28ebd6f4fc57695aa420
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452438"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="6d9ab-102">alias externo (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6d9ab-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="6d9ab-103">Es posible que deba hacer referencia a dos versiones de ensamblados que tienen los mismos nombres de tipo completos.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="6d9ab-104">Por ejemplo, es posible que tenga que usar dos o más versiones de un ensamblado en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="6d9ab-105">Mediante el uso de un alias de ensamblado externo, los espacios de nombres de cada ensamblado pueden ajustarse en espacios de nombres de nivel de raíz denominados por el alias, lo que permite que se usen en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d9ab-106">La palabra clave [extern](../../../csharp/language-reference/keywords/extern.md) también se usa como un modificador de método, y declara un método escrito en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-106">The [extern](../../../csharp/language-reference/keywords/extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="6d9ab-107">Para hacer referencia a dos ensamblados con los mismos nombres de tipo completos, debe especificarse un alias en un símbolo del sistema, como sigue:</span><span class="sxs-lookup"><span data-stu-id="6d9ab-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="6d9ab-108">Esto crea los alias externos `GridV1` y `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="6d9ab-109">Para usar estos alias desde dentro de un programa, se hace referencia a ellos mediante la palabra clave `extern`.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="6d9ab-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6d9ab-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="6d9ab-111">Cada declaración de alias externo introduce un espacio de nombres de nivel de raíz adicional que es semejante al espacio de nombres global (pero que no se encuentra en su interior).</span><span class="sxs-lookup"><span data-stu-id="6d9ab-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="6d9ab-112">Por tanto, se puede hacer referencia a los tipos de cada ensamblado sin ambigüedad mediante su nombre completo, con raíz en el alias de espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="6d9ab-113">En el ejemplo anterior, `GridV1::Grid` sería el control de cuadrícula de `grid.dll`, y `GridV2::Grid` sería el control de cuadrícula de `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="6d9ab-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6d9ab-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6d9ab-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d9ab-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d9ab-115">See also</span></span>

- [<span data-ttu-id="6d9ab-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6d9ab-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="6d9ab-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6d9ab-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6d9ab-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6d9ab-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="6d9ab-119">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6d9ab-119">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)
- [<span data-ttu-id="6d9ab-120">:: !</span><span class="sxs-lookup"><span data-stu-id="6d9ab-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [<span data-ttu-id="6d9ab-121">/reference (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="6d9ab-121">/reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
