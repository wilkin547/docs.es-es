---
title: Novedades de C# 7.2
description: "Información general sobre las nuevas características en C# 7.2."
keywords: "Diseño del lenguaje C#, 7.2, Visual Studio 2017,"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: cc861f186bea681bb32a2f8041a7155026679987
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="0f869-104">Novedades de C# 7.2</span><span class="sxs-lookup"><span data-stu-id="0f869-104">What's new in C# 7.2</span></span>

<span data-ttu-id="0f869-105">C# 7.2 es otra versión de punto que agrega varias características útiles.</span><span class="sxs-lookup"><span data-stu-id="0f869-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="0f869-106">Una de las ventajas de esta versión es que funciona mejor con tipos de valor, ya que evita copias o asignaciones innecesarias.</span><span class="sxs-lookup"><span data-stu-id="0f869-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="0f869-107">El resto de características son menos importantes, pero igualmente útiles.</span><span class="sxs-lookup"><span data-stu-id="0f869-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="0f869-108">C# 7.2 usa el elemento de configuración de [selección de versión de lenguaje](csharp-7-1.md#language-version-selection) para seleccionar la versión del lenguaje del compilador.</span><span class="sxs-lookup"><span data-stu-id="0f869-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="0f869-109">Las nuevas características de lenguaje de esta versión son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f869-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="0f869-110">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="0f869-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="0f869-111">Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="0f869-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="0f869-112">Argumentos con nombre no finales</span><span class="sxs-lookup"><span data-stu-id="0f869-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="0f869-113">Los argumentos con nombre pueden ir seguidos de argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="0f869-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="0f869-114">Caracteres de subrayado iniciales en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="0f869-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="0f869-115">Los literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.</span><span class="sxs-lookup"><span data-stu-id="0f869-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="0f869-116">Modificador de acceso `private protected`</span><span class="sxs-lookup"><span data-stu-id="0f869-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="0f869-117">El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0f869-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="0f869-118">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="0f869-118">Reference semantics with value types</span></span>

<span data-ttu-id="0f869-119">Las características de lenguaje que presenta la versión 7.2 permiten trabajar con tipos de valor usando la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="0f869-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="0f869-120">Están diseñadas para aumentar el rendimiento minimizando la copia de tipos de valor sin usar las asignaciones de memoria asociadas al uso de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="0f869-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="0f869-121">Las características incluyen:</span><span class="sxs-lookup"><span data-stu-id="0f869-121">The features include:</span></span>

 - <span data-ttu-id="0f869-122">El modificador `in` en los parámetros para especificar que un argumento se pasa mediante una referencia sin que el método al que se realiza una llamada lo modifique.</span><span class="sxs-lookup"><span data-stu-id="0f869-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="0f869-123">El modificador `ref readonly` en las devoluciones de método para indicar que un método devuelve su valor mediante una referencia, pero que no permite operaciones de escritura en el objeto.</span><span class="sxs-lookup"><span data-stu-id="0f869-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="0f869-124">La declaración `readonly struct` para indicar que una estructura es fija y que debería pasarse como parámetro `in` a los métodos de su miembro.</span><span class="sxs-lookup"><span data-stu-id="0f869-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="0f869-125">La declaración `ref struct` para indicar que un tipo de estructura tiene acceso directo a la memoria administrada y que siempre debe estar asignada a la pila.</span><span class="sxs-lookup"><span data-stu-id="0f869-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="0f869-126">Puede obtener más información sobre todos los cambios en [Semántica de referencia con tipos de valor](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="0f869-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="0f869-127">Argumentos con nombre no finales</span><span class="sxs-lookup"><span data-stu-id="0f869-127">Non-trailing named arguments</span></span>

<span data-ttu-id="0f869-128">Las llamadas de método ya pueden usar argumentos con nombre que precedan a argumentos posicionales si están en la posición adecuada.</span><span class="sxs-lookup"><span data-stu-id="0f869-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="0f869-129">Para obtener más información, vea [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="0f869-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="0f869-130">Caracteres de subrayado iniciales en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="0f869-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="0f869-131">La implementación de la compatibilidad con separadores de dígitos en C# 7.0 no permitía que `_` fuera el primer carácter del valor literal.</span><span class="sxs-lookup"><span data-stu-id="0f869-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="0f869-132">Los literales numéricos hexadecimales y binarios ya pueden empezar con un `_`.</span><span class="sxs-lookup"><span data-stu-id="0f869-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="0f869-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0f869-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="0f869-134">Por último, presentamos un nuevo modificador de acceso compuesto: `private protected` indica que se puede tener acceso a un miembro mediante una clase o clases derivadas declaradas en un mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0f869-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="0f869-135">Mientras que `protected internal` permite el acceso a las clases derivadas o clases que se encuentran en un mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en un mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0f869-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="0f869-136">Para obtener más información, vea los [modificadores de acceso](../language-reference/keywords/access-modifiers.md) en el material de referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="0f869-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
