---
title: Novedades de C# 7.2
description: Información general sobre las nuevas características en C# 7.2.
ms.date: 08/16/2017
ms.openlocfilehash: a74afd7f073daa46328d60149e2dd90207420a80
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566194"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="78798-103">Novedades de C# 7.2</span><span class="sxs-lookup"><span data-stu-id="78798-103">What's new in C# 7.2</span></span>

<span data-ttu-id="78798-104">C# 7.2 es otra versión de punto que agrega varias características útiles.</span><span class="sxs-lookup"><span data-stu-id="78798-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="78798-105">Una de las ventajas de esta versión es que funciona mejor con tipos de valor, ya que evita copias o asignaciones innecesarias.</span><span class="sxs-lookup"><span data-stu-id="78798-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="78798-106">El resto de características son menos importantes, pero igualmente útiles.</span><span class="sxs-lookup"><span data-stu-id="78798-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="78798-107">C# 7.2 usa el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md) para seleccionar la versión del lenguaje del compilador.</span><span class="sxs-lookup"><span data-stu-id="78798-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="78798-108">Las nuevas características de lenguaje de esta versión son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="78798-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="78798-109">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="78798-109">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="78798-110">Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="78798-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="78798-111">Argumentos con nombre no finales</span><span class="sxs-lookup"><span data-stu-id="78798-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="78798-112">Los argumentos con nombre pueden ir seguidos de argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="78798-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="78798-113">Caracteres de subrayado iniciales en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="78798-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="78798-114">Los literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.</span><span class="sxs-lookup"><span data-stu-id="78798-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="78798-115">Modificador de acceso `private protected`</span><span class="sxs-lookup"><span data-stu-id="78798-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="78798-116">El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="78798-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="78798-117">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="78798-117">Reference semantics with value types</span></span>

<span data-ttu-id="78798-118">Las características de lenguaje que presenta la versión 7.2 permiten trabajar con tipos de valor usando la semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="78798-118">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="78798-119">Están diseñadas para aumentar el rendimiento minimizando la copia de tipos de valor sin usar las asignaciones de memoria asociadas al uso de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="78798-119">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="78798-120">Las características incluyen:</span><span class="sxs-lookup"><span data-stu-id="78798-120">The features include:</span></span>

 - <span data-ttu-id="78798-121">El modificador `in` en los parámetros para especificar que un argumento se pasa mediante una referencia sin que el método al que se realiza una llamada lo modifique.</span><span class="sxs-lookup"><span data-stu-id="78798-121">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="78798-122">El modificador `ref readonly` en las devoluciones de método para indicar que un método devuelve su valor mediante una referencia, pero que no permite operaciones de escritura en el objeto.</span><span class="sxs-lookup"><span data-stu-id="78798-122">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="78798-123">La declaración `readonly struct` para indicar que una estructura es fija y que debería pasarse como parámetro `in` a los métodos de su miembro.</span><span class="sxs-lookup"><span data-stu-id="78798-123">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="78798-124">La declaración `ref struct` para indicar que un tipo de estructura tiene acceso directo a la memoria administrada y que siempre debe estar asignada a la pila.</span><span class="sxs-lookup"><span data-stu-id="78798-124">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="78798-125">Puede obtener más información sobre todos los cambios en [Semántica de referencia con tipos de valor](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="78798-125">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="78798-126">Argumentos con nombre no finales</span><span class="sxs-lookup"><span data-stu-id="78798-126">Non-trailing named arguments</span></span>

<span data-ttu-id="78798-127">Las llamadas de método ya pueden usar argumentos con nombre que precedan a argumentos posicionales si están en la posición adecuada.</span><span class="sxs-lookup"><span data-stu-id="78798-127">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="78798-128">Para obtener más información, vea [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="78798-128">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="78798-129">Caracteres de subrayado iniciales en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="78798-129">Leading underscores in numeric literals</span></span>

<span data-ttu-id="78798-130">La implementación de la compatibilidad con separadores de dígitos en C# 7.0 no permitía que `_` fuera el primer carácter del valor literal.</span><span class="sxs-lookup"><span data-stu-id="78798-130">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="78798-131">Los literales numéricos hexadecimales y binarios ya pueden empezar con un `_`.</span><span class="sxs-lookup"><span data-stu-id="78798-131">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="78798-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78798-132">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="78798-133">Modificador de acceso _private protected_</span><span class="sxs-lookup"><span data-stu-id="78798-133">_private protected_ access modifier</span></span>

<span data-ttu-id="78798-134">Por último, presentamos un nuevo modificador de acceso compuesto: `private protected` indica que se puede tener acceso a un miembro mediante una clase o clases derivadas declaradas en un mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="78798-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="78798-135">Mientras que `protected internal` permite el acceso a las clases derivadas o clases que se encuentran en un mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en un mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="78798-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="78798-136">Para obtener más información, vea los [modificadores de acceso](../language-reference/keywords/access-modifiers.md) en el material de referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="78798-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
