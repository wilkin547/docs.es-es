---
title: new (Modificador, Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 496339a7c3b95f16fd13479b096d90058b0799d4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43400721"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="16676-102">new (Modificador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="16676-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="16676-103">Cuando se utiliza como modificador de una declaración, la palabra clave `new` oculta explícitamente un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="16676-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="16676-104">Cuando se oculta un miembro heredado, la versión derivada del miembro reemplaza a la versión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="16676-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="16676-105">Aunque los miembros se pueden ocultar sin utilizar el modificador `new`, obtendrá una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="16676-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="16676-106">Si utiliza `new` explícitamente para ocultar un miembro, se suprime esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="16676-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="16676-107">Para ocultar un miembro heredado, declárelo en la clase derivada con el mismo nombre de miembro y modifíquelo con la palabra clave `new`.</span><span class="sxs-lookup"><span data-stu-id="16676-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="16676-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16676-108">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="16676-109">En este ejemplo, `BaseC.Invoke` oculta `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="16676-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="16676-110">El campo `x` no se ve afectado porque no lo oculta un nombre similar.</span><span class="sxs-lookup"><span data-stu-id="16676-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="16676-111">La ocultación de nombres por medio de la herencia toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="16676-111">Name hiding through inheritance takes one of the following forms:</span></span>

<span data-ttu-id="16676-112">Normalmente, una constante, un campo, una propiedad o un tipo que se muestran en una clase o struct ocultan a todos los miembros de la clase base que comparten su nombre.</span><span class="sxs-lookup"><span data-stu-id="16676-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="16676-113">Hay casos especiales.</span><span class="sxs-lookup"><span data-stu-id="16676-113">There are special cases.</span></span>  <span data-ttu-id="16676-114">Por ejemplo, si declara un nuevo campo con el nombre `N` para tener un tipo que no es invocable y un tipo base declara `N` como método, el nuevo campo no oculta la declaración base en la sintaxis de invocación.</span><span class="sxs-lookup"><span data-stu-id="16676-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="16676-115">Vea [Especificación del lenguaje C# 5.0](https://www.microsoft.com/download/details.aspx?id=7029) para obtener información detallada (vea "Búsqueda de miembros" en la sección "Expresiones").</span><span class="sxs-lookup"><span data-stu-id="16676-115">See the [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) for details (see section "Member Lookup" in section "Expressions").</span></span>

<span data-ttu-id="16676-116">Un método introducido en una clase o struct oculta las propiedades, los campos y los tipos que comparten el nombre en la clase base.</span><span class="sxs-lookup"><span data-stu-id="16676-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="16676-117">También oculta todos los métodos de la clase base que tienen la misma signatura.</span><span class="sxs-lookup"><span data-stu-id="16676-117">It also hides all base class methods that have the same signature.</span></span>

<span data-ttu-id="16676-118">Un indizador introducido en una clase o struct oculta todos los indizadores de la clase base que tienen la misma signatura.</span><span class="sxs-lookup"><span data-stu-id="16676-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="16676-119">Es un error usar `new` y [override](override.md) en el mismo miembro, porque los dos modificadores tienen significados mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="16676-119">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="16676-120">El modificador `new` crea un nuevo miembro con el mismo nombre y oculta el miembro original.</span><span class="sxs-lookup"><span data-stu-id="16676-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="16676-121">El modificador `override` amplía la implementación de un miembro heredado.</span><span class="sxs-lookup"><span data-stu-id="16676-121">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="16676-122">Si se utiliza el modificador `new` en una declaración que no oculta un miembro heredado, se genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="16676-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="16676-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16676-123">Example</span></span>

<span data-ttu-id="16676-124">En este ejemplo, una clase base, `BaseC`, y una clase derivada, `DerivedC`, utilizan el mismo nombre de campo `x`, lo que oculta el valor del campo heredado.</span><span class="sxs-lookup"><span data-stu-id="16676-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="16676-125">El ejemplo muestra el uso del modificador `new`.</span><span class="sxs-lookup"><span data-stu-id="16676-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="16676-126">También muestra cómo obtener acceso a los miembros ocultos de la clase base mediante sus nombres completos.</span><span class="sxs-lookup"><span data-stu-id="16676-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="16676-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16676-127">Example</span></span>

<span data-ttu-id="16676-128">En este ejemplo, una clase anidada oculta una clase que tiene el mismo nombre en la clase base.</span><span class="sxs-lookup"><span data-stu-id="16676-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="16676-129">El ejemplo muestra cómo utilizar el modificador `new` para eliminar el mensaje de advertencia y cómo obtener acceso a los miembros de la clase oculta mediante sus nombres completos.</span><span class="sxs-lookup"><span data-stu-id="16676-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="16676-130">Si quita el modificador `new`, el programa seguirá compilándose y ejecutándose, pero aparecerá la siguiente advertencia:</span><span class="sxs-lookup"><span data-stu-id="16676-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="16676-131">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="16676-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="16676-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="16676-132">See also</span></span>

- [<span data-ttu-id="16676-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="16676-133">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="16676-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="16676-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="16676-135">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="16676-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="16676-136">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="16676-136">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="16676-137">Modificadores</span><span class="sxs-lookup"><span data-stu-id="16676-137">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="16676-138">Control de versiones con las palabras clave Override y New</span><span class="sxs-lookup"><span data-stu-id="16676-138">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="16676-139">Saber cuándo utilizar las palabras clave Override y New</span><span class="sxs-lookup"><span data-stu-id="16676-139">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
