---
title: 'alias externo: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 891e56b064f8a327abe28293223a85b9d95e8fd3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301819"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="698f1-102">alias externo (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="698f1-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="698f1-103">Es posible que deba hacer referencia a dos versiones de ensamblados que tienen los mismos nombres de tipo completos.</span><span class="sxs-lookup"><span data-stu-id="698f1-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="698f1-104">Por ejemplo, es posible que tenga que usar dos o más versiones de un ensamblado en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="698f1-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="698f1-105">Mediante el uso de un alias de ensamblado externo, los espacios de nombres de cada ensamblado pueden ajustarse en espacios de nombres de nivel de raíz denominados por el alias, lo que permite que se usen en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="698f1-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="698f1-106">La palabra clave [extern](./extern.md) también se usa como un modificador de método, y declara un método escrito en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="698f1-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="698f1-107">Para hacer referencia a dos ensamblados con los mismos nombres de tipo completos, debe especificarse un alias en un símbolo del sistema, como sigue:</span><span class="sxs-lookup"><span data-stu-id="698f1-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="698f1-108">Esto crea los alias externos `GridV1` y `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="698f1-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="698f1-109">Para usar estos alias desde dentro de un programa, se hace referencia a ellos mediante la palabra clave `extern`.</span><span class="sxs-lookup"><span data-stu-id="698f1-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="698f1-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="698f1-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="698f1-111">Cada declaración de alias externo introduce un espacio de nombres de nivel de raíz adicional que es semejante al espacio de nombres global (pero que no se encuentra en su interior).</span><span class="sxs-lookup"><span data-stu-id="698f1-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="698f1-112">Por tanto, se puede hacer referencia a los tipos de cada ensamblado sin ambigüedad mediante su nombre completo, con raíz en el alias de espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="698f1-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="698f1-113">En el ejemplo anterior, `GridV1::Grid` sería el control de cuadrícula de `grid.dll`, y `GridV2::Grid` sería el control de cuadrícula de `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="698f1-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="698f1-114">Uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="698f1-114">Using Visual Studio</span></span>

<span data-ttu-id="698f1-115">Si usa Visual Studio, los alias se pueden proporcionar de manera similar.</span><span class="sxs-lookup"><span data-stu-id="698f1-115">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="698f1-116">Agregue una referencia de *grid.dll* y *grid20.dll* al proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="698f1-116">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="698f1-117">Abra una pestaña de propiedades y cambie los alias de global a GridV1 y GridV2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="698f1-117">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="698f1-118">Use estos alias igual que antes.</span><span class="sxs-lookup"><span data-stu-id="698f1-118">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="698f1-119">Ahora puede crear un alias para un espacio de nombres o un tipo *mediante la directiva de alias*.</span><span class="sxs-lookup"><span data-stu-id="698f1-119">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="698f1-120">Para más información, consulte la [directiva using](using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="698f1-120">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="698f1-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="698f1-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="698f1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="698f1-122">See also</span></span>

- [<span data-ttu-id="698f1-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="698f1-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="698f1-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="698f1-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="698f1-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="698f1-125">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="698f1-126">:: !</span><span class="sxs-lookup"><span data-stu-id="698f1-126">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="698f1-127">-reference (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="698f1-127">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
