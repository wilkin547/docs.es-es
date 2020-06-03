---
title: 'Modificador new: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 529d77b0a66a8a3cedfe7a400af0fb34dd653322
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795175"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="88a06-102">new (Modificador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="88a06-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="88a06-103">Cuando se utiliza como modificador de una declaración, la palabra clave `new` oculta explícitamente un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="88a06-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="88a06-104">Cuando se oculta un miembro heredado, la versión derivada del miembro reemplaza a la versión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="88a06-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="88a06-105">Aunque los miembros se pueden ocultar sin utilizar el modificador `new`, obtendrá una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="88a06-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="88a06-106">Si utiliza `new` explícitamente para ocultar un miembro, se suprime esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="88a06-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="88a06-107">También puede usar la palabra clave `new` para [crear una instancia de un tipo](../operators/new-operator.md) o como una [restricción de tipo genérico](./new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="88a06-107">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [generic type constraint](./new-constraint.md).</span></span>

<span data-ttu-id="88a06-108">Para ocultar un miembro heredado, declárelo en la clase derivada con el mismo nombre de miembro y modifíquelo con la palabra clave `new`.</span><span class="sxs-lookup"><span data-stu-id="88a06-108">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="88a06-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="88a06-109">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="88a06-110">En este ejemplo, `BaseC.Invoke` oculta `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="88a06-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="88a06-111">El campo `x` no se ve afectado porque no lo oculta un nombre similar.</span><span class="sxs-lookup"><span data-stu-id="88a06-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="88a06-112">La ocultación de nombres por medio de la herencia toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="88a06-112">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="88a06-113">Normalmente, una constante, un campo, una propiedad o un tipo que se muestran en una clase o struct ocultan a todos los miembros de la clase base que comparten su nombre.</span><span class="sxs-lookup"><span data-stu-id="88a06-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span> <span data-ttu-id="88a06-114">Hay casos especiales.</span><span class="sxs-lookup"><span data-stu-id="88a06-114">There are special cases.</span></span> <span data-ttu-id="88a06-115">Por ejemplo, si declara un nuevo campo con el nombre `N` para tener un tipo que no es invocable y un tipo base declara `N` como método, el nuevo campo no oculta la declaración base en la sintaxis de invocación.</span><span class="sxs-lookup"><span data-stu-id="88a06-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span> <span data-ttu-id="88a06-116">Para obtener más información, vea la sección [Búsqueda de miembros](~/_csharplang/spec/expressions.md#member-lookup) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="88a06-116">For more information, see the [Member lookup](~/_csharplang/spec/expressions.md#member-lookup) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="88a06-117">Un método introducido en una clase o struct oculta las propiedades, los campos y los tipos que comparten el nombre en la clase base.</span><span class="sxs-lookup"><span data-stu-id="88a06-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="88a06-118">También oculta todos los métodos de la clase base que tienen la misma signatura.</span><span class="sxs-lookup"><span data-stu-id="88a06-118">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="88a06-119">Un indizador introducido en una clase o struct oculta todos los indizadores de la clase base que tienen la misma signatura.</span><span class="sxs-lookup"><span data-stu-id="88a06-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="88a06-120">Es un error usar `new` y [override](override.md) en el mismo miembro, porque los dos modificadores tienen significados mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="88a06-120">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="88a06-121">El modificador `new` crea un nuevo miembro con el mismo nombre y oculta el miembro original.</span><span class="sxs-lookup"><span data-stu-id="88a06-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="88a06-122">El modificador `override` amplía la implementación de un miembro heredado.</span><span class="sxs-lookup"><span data-stu-id="88a06-122">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="88a06-123">Si se utiliza el modificador `new` en una declaración que no oculta un miembro heredado, se genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="88a06-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="88a06-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88a06-124">Example</span></span>

<span data-ttu-id="88a06-125">En este ejemplo, una clase base, `BaseC`, y una clase derivada, `DerivedC`, utilizan el mismo nombre de campo `x`, lo que oculta el valor del campo heredado.</span><span class="sxs-lookup"><span data-stu-id="88a06-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="88a06-126">El ejemplo muestra el uso del modificador `new`.</span><span class="sxs-lookup"><span data-stu-id="88a06-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="88a06-127">También muestra cómo obtener acceso a los miembros ocultos de la clase base mediante sus nombres completos.</span><span class="sxs-lookup"><span data-stu-id="88a06-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="88a06-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88a06-128">Example</span></span>

<span data-ttu-id="88a06-129">En este ejemplo, una clase anidada oculta una clase que tiene el mismo nombre en la clase base.</span><span class="sxs-lookup"><span data-stu-id="88a06-129">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="88a06-130">El ejemplo muestra cómo utilizar el modificador `new` para eliminar el mensaje de advertencia y cómo obtener acceso a los miembros de la clase oculta mediante sus nombres completos.</span><span class="sxs-lookup"><span data-stu-id="88a06-130">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="88a06-131">Si quita el modificador `new`, el programa seguirá compilándose y ejecutándose, pero aparecerá la siguiente advertencia:</span><span class="sxs-lookup"><span data-stu-id="88a06-131">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="88a06-132">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="88a06-132">C# language specification</span></span>

<span data-ttu-id="88a06-133">Para obtener más información, vea la sección [El modificador new](~/_csharplang/spec/classes.md#the-new-modifier) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="88a06-133">For more information, see [The new modifier](~/_csharplang/spec/classes.md#the-new-modifier) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="88a06-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="88a06-134">See also</span></span>

- [<span data-ttu-id="88a06-135">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="88a06-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="88a06-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="88a06-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="88a06-137">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="88a06-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="88a06-138">Modificadores</span><span class="sxs-lookup"><span data-stu-id="88a06-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="88a06-139">Control de versiones con las palabras clave Override y New</span><span class="sxs-lookup"><span data-stu-id="88a06-139">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="88a06-140">Saber cuándo utilizar las palabras clave Override y New</span><span class="sxs-lookup"><span data-stu-id="88a06-140">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
