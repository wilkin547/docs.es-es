---
title: 'Constantes: Guía de programación de C#'
description: En C#, las constantes son valores literales en tiempo de compilación, que no cambian después de compilar el programa. Solo los tipos integrados de C# pueden ser constantes.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 4783aff8e9424c90e46cb52692a3e645e995d914
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899079"
---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="8cca5-104">Constantes (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8cca5-104">Constants (C# Programming Guide)</span></span>

<span data-ttu-id="8cca5-105">Las constantes son valores inmutables que se conocen en tiempo de compilación y que no cambian durante la vida del programa.</span><span class="sxs-lookup"><span data-stu-id="8cca5-105">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="8cca5-106">Las constantes se declaran con el modificador [const](../../language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="8cca5-106">Constants are declared with the [const](../../language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="8cca5-107">Solo los [tipos integrados](../../language-reference/builtin-types/built-in-types.md) de C# (excluido <xref:System.Object?displayProperty=nameWithType>) pueden declararse como `const`.</span><span class="sxs-lookup"><span data-stu-id="8cca5-107">Only the C# [built-in types](../../language-reference/builtin-types/built-in-types.md) (excluding <xref:System.Object?displayProperty=nameWithType>) may be declared as `const`.</span></span> <span data-ttu-id="8cca5-108">Los tipos definidos por el usuario, incluidas las clases, las estructuras y las matrices, no pueden ser `const`.</span><span class="sxs-lookup"><span data-stu-id="8cca5-108">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="8cca5-109">Use el modificador [readonly](../../language-reference/keywords/readonly.md) para crear una clase, una estructura o una matriz que se inicialice una vez en tiempo de ejecución (por ejemplo, en un constructor) y que posteriormente no se pueda cambiar.</span><span class="sxs-lookup"><span data-stu-id="8cca5-109">Use the [readonly](../../language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="8cca5-110">C# no admite métodos, propiedades ni eventos `const`.</span><span class="sxs-lookup"><span data-stu-id="8cca5-110">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="8cca5-111">El tipo enum permite definir constantes con nombre para los tipos integrados enteros (por ejemplo, `int`, `uint`, `long`, etc.).</span><span class="sxs-lookup"><span data-stu-id="8cca5-111">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="8cca5-112">Para más información, vea [enum](../../language-reference/builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="8cca5-112">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="8cca5-113">Las constantes se deben inicializar al declararse.</span><span class="sxs-lookup"><span data-stu-id="8cca5-113">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="8cca5-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8cca5-114">For example:</span></span>  
  
 [!code-csharp[Calendar#1](snippets/constants/Calendar.cs#1)]
  
 <span data-ttu-id="8cca5-115">En este ejemplo la constante `Months` siempre es 12 y ni siquiera la propia clase la puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="8cca5-115">In this example, the constant `Months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="8cca5-116">De hecho, cuando el compilador detecta un identificador de constante en el código fuente de C# (por ejemplo, `Months`), sustituye directamente el valor literal en el código de lenguaje intermedio (IL) que genera.</span><span class="sxs-lookup"><span data-stu-id="8cca5-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `Months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="8cca5-117">Dado que no hay ninguna dirección de variable asociada a una constante en tiempo de ejecución, no se pueden pasar los campos `const` por referencia ni pueden aparecer como un valor L en una expresión.</span><span class="sxs-lookup"><span data-stu-id="8cca5-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cca5-118">Tenga cuidado al hacer referencia a valores de constante definidos en otro código como archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="8cca5-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="8cca5-119">Si una nueva versión del archivo DLL define un nuevo valor para la constante, el programa conservará el valor literal anterior hasta que se vuelva a compilar con la versión nueva.</span><span class="sxs-lookup"><span data-stu-id="8cca5-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="8cca5-120">Se pueden declarar varias constantes del mismo tipo a la vez, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8cca5-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 [!code-csharp[Calendar#2](snippets/constants/Calendar.cs#2)]
  
 <span data-ttu-id="8cca5-121">La expresión que se usa para inicializar una constante puede hacer referencia a otra constante si no crea una referencia circular.</span><span class="sxs-lookup"><span data-stu-id="8cca5-121">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="8cca5-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8cca5-122">For example:</span></span>  
  
 [!code-csharp[Calendar#3](snippets/constants/Calendar.cs#3)]
  
 <span data-ttu-id="8cca5-123">Las constantes pueden marcarse como [públicas](../../language-reference/keywords/public.md), [privadas](../../language-reference/keywords/private.md), [protegidas](../../language-reference/keywords/protected.md), [internas](../../language-reference/keywords/internal.md), [protegidas internas](../../language-reference/keywords/protected-internal.md)o [privadas protegidas](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="8cca5-123">Constants can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="8cca5-124">Estos modificadores de acceso definen cómo los usuarios de la clase pueden acceder a la constante.</span><span class="sxs-lookup"><span data-stu-id="8cca5-124">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="8cca5-125">Para más información, vea [Modificadores de acceso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="8cca5-125">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="8cca5-126">A las constantes se accede como si fueran campos [estáticos](../../language-reference/keywords/static.md) porque el valor de la constante es el mismo para todas las instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="8cca5-126">Constants are accessed as if they were [static](../../language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="8cca5-127">No use la palabra clave `static` para declararlas.</span><span class="sxs-lookup"><span data-stu-id="8cca5-127">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="8cca5-128">Las expresiones que no están en la clase que define la constante deben usar el nombre de la clase, un punto y el nombre de la constante para acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="8cca5-128">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="8cca5-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8cca5-129">For example:</span></span>  
  
 [!code-csharp[Calendar#4](snippets/constants/Calendar.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="8cca5-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8cca5-130">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8cca5-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cca5-131">See also</span></span>

- [<span data-ttu-id="8cca5-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8cca5-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8cca5-133">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="8cca5-133">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="8cca5-134">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8cca5-134">Properties</span></span>](./properties.md)
- [<span data-ttu-id="8cca5-135">Tipos</span><span class="sxs-lookup"><span data-stu-id="8cca5-135">Types</span></span>](../types/index.md)
- [<span data-ttu-id="8cca5-136">readonly</span><span class="sxs-lookup"><span data-stu-id="8cca5-136">readonly</span></span>](../../language-reference/keywords/readonly.md)
- [<span data-ttu-id="8cca5-137">Inmutabilidad en la primera parte de C#: tipos de inmutabilidad</span><span class="sxs-lookup"><span data-stu-id="8cca5-137">Immutability in C# Part One: Kinds of Immutability</span></span>](/archive/blogs/ericlippert/immutability-in-c-part-one-kinds-of-immutability)
