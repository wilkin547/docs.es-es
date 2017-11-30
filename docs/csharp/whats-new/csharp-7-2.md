---
title: Novedades de C# 7.2
description: "Información general sobre las nuevas características de C# 7.2."
keywords: "Diseño del lenguaje C#, 7.2, Visual Studio 2017"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="2a4aa-104">Novedades de C# 7.2</span><span class="sxs-lookup"><span data-stu-id="2a4aa-104">What's new in C# 7.2</span></span>

<span data-ttu-id="2a4aa-105">C# 7.2 es otra versión de punto que agrega un número de características útiles.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="2a4aa-106">Un tema para esta versión funciona más eficazmente con tipos de valor al evitar la copia innecesaria o asignaciones.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="2a4aa-107">Las características restantes son pequeños, nice tienen.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="2a4aa-108">7.2 C# usa el [selección de la versión de idioma](csharp-7-1.md#language-version-selection) elemento de configuración para seleccionar la versión de idioma de compilador.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="2a4aa-109">Las nuevas características de lenguaje en esta versión son:</span><span class="sxs-lookup"><span data-stu-id="2a4aa-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="2a4aa-110">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="2a4aa-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="2a4aa-111">Una combinación de mejoras de sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="2a4aa-112">No son finales argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="2a4aa-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="2a4aa-113">Argumentos con nombre pueden ir seguidos de argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="2a4aa-114">Carácter de subrayado inicial en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="2a4aa-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="2a4aa-115">Literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="2a4aa-116">`private protected`modificador de acceso</span><span class="sxs-lookup"><span data-stu-id="2a4aa-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="2a4aa-117">El `private protected` modificador de acceso permite el acceso para las clases derivadas en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="2a4aa-118">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="2a4aa-118">Reference semantics with value types</span></span>

<span data-ttu-id="2a4aa-119">Características de lenguaje incluidas en 7.2 permiten trabajar con tipos de valor al usar la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="2a4aa-120">Están diseñadas para aumentar el rendimiento, pues minimiza las copias de los tipos de valor sin incurrir en las asignaciones de memoria asociadas al uso de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="2a4aa-121">Las características incluyen:</span><span class="sxs-lookup"><span data-stu-id="2a4aa-121">The features include:</span></span>

 - <span data-ttu-id="2a4aa-122">El `in` modificador de parámetros, para especificar que un argumento se pasa por referencia pero no modifica el método llamado.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="2a4aa-123">El `ref readonly` modificador en el método devuelve, para indicar que un método devuelve su valor por referencia, pero no permite operaciones de escritura en ese objeto.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="2a4aa-124">El `readonly struct` declaración, para indicar que un struct es inmutable y se debe pasar como un `in` parámetro a sus métodos de miembro.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="2a4aa-125">El `ref struct` declaración, para indicar que un tipo de estructura tiene acceso directo a memoria administrada y siempre debe ser pila asignada.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="2a4aa-126">Puede obtener más información acerca de todos los cambios en [con semántica de referencias a tipos de valor](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="2a4aa-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="2a4aa-127">No son finales argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="2a4aa-127">Non-trailing named arguments</span></span>

<span data-ttu-id="2a4aa-128">Llamadas de método ahora pueden usar argumentos con nombre que preceden a los argumentos posicionales cuando los argumentos con nombre se encuentran en las posiciones correctas.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="2a4aa-129">Para obtener más información, consulte [argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="2a4aa-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="2a4aa-130">Carácter de subrayado inicial en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="2a4aa-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="2a4aa-131">La implementación de la compatibilidad con separadores de dígitos en C# 7.0 no permitió la `_` a ser el primer carácter del valor literal.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="2a4aa-132">Hex y literales numéricos binarios ahora pueden empezar con un `_`.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="2a4aa-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2a4aa-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="2a4aa-134">Por último, un nuevo modificador de acceso compuestos: `private protected` indica que las clases derivadas que se declaran en el mismo ensamblado puede tener acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="2a4aa-135">Mientras `protected internal` permite el acceso a las clases derivadas o las clases que se encuentran en el mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="2a4aa-136">Para obtener más información, consulte [los modificadores de acceso](../language-reference/keywords/access-modifiers.md) en la referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="2a4aa-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
