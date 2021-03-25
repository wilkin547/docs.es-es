---
description: 'alias externo: Referencia de C#'
title: 'alias externo: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 230e9d7169e8924749f234af2fa411950f68ce78
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477472"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="7bad0-103">alias externo (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7bad0-103">extern alias (C# Reference)</span></span>

<span data-ttu-id="7bad0-104">Es posible que deba hacer referencia a dos versiones de ensamblados que tienen los mismos nombres de tipo completos.</span><span class="sxs-lookup"><span data-stu-id="7bad0-104">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="7bad0-105">Por ejemplo, es posible que tenga que usar dos o más versiones de un ensamblado en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bad0-105">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="7bad0-106">Mediante el uso de un alias de ensamblado externo, los espacios de nombres de cada ensamblado pueden ajustarse en espacios de nombres de nivel de raíz denominados por el alias, lo que permite que se usen en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="7bad0-106">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bad0-107">La palabra clave [extern](./extern.md) también se usa como un modificador de método, y declara un método escrito en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="7bad0-107">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="7bad0-108">Para hacer referencia a dos ensamblados con los mismos nombres de tipo completos, debe especificarse un alias en un símbolo del sistema, como sigue:</span><span class="sxs-lookup"><span data-stu-id="7bad0-108">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="7bad0-109">Esto crea los alias externos `GridV1` y `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="7bad0-109">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="7bad0-110">Para usar estos alias desde dentro de un programa, se hace referencia a ellos mediante la palabra clave `extern`.</span><span class="sxs-lookup"><span data-stu-id="7bad0-110">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="7bad0-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7bad0-111">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="7bad0-112">Cada declaración de alias externo introduce un espacio de nombres de nivel de raíz adicional que es semejante al espacio de nombres global (pero que no se encuentra en su interior).</span><span class="sxs-lookup"><span data-stu-id="7bad0-112">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="7bad0-113">Por tanto, se puede hacer referencia a los tipos de cada ensamblado sin ambigüedad mediante su nombre completo, con raíz en el alias de espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="7bad0-113">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="7bad0-114">En el ejemplo anterior, `GridV1::Grid` sería el control de cuadrícula de `grid.dll`, y `GridV2::Grid` sería el control de cuadrícula de `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="7bad0-114">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="7bad0-115">Uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7bad0-115">Using Visual Studio</span></span>

<span data-ttu-id="7bad0-116">Si usa Visual Studio, los alias se pueden proporcionar de manera similar.</span><span class="sxs-lookup"><span data-stu-id="7bad0-116">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="7bad0-117">Agregue una referencia de *grid.dll* y *grid20.dll* al proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7bad0-117">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="7bad0-118">Abra una pestaña de propiedades y cambie los alias de global a GridV1 y GridV2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7bad0-118">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="7bad0-119">Use estos alias igual que antes.</span><span class="sxs-lookup"><span data-stu-id="7bad0-119">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="7bad0-120">Ahora puede crear un alias para un espacio de nombres o un tipo *mediante la directiva de alias*.</span><span class="sxs-lookup"><span data-stu-id="7bad0-120">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="7bad0-121">Para más información, consulte la [directiva using](using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="7bad0-121">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="7bad0-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7bad0-122">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7bad0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bad0-123">See also</span></span>

- [<span data-ttu-id="7bad0-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7bad0-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7bad0-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7bad0-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7bad0-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7bad0-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="7bad0-127">:: !</span><span class="sxs-lookup"><span data-stu-id="7bad0-127">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="7bad0-128">**References** (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="7bad0-128">**References** (C# Compiler Options)</span></span>](../compiler-options/inputs.md#references)
