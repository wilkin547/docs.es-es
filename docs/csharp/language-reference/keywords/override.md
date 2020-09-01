---
description: 'Modificador override: Referencia de C#'
title: 'Modificador override: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 51ca806310214981b7ff24a796fe078d902dca4d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134465"
---
# <a name="override-c-reference"></a><span data-ttu-id="76f31-103">override (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="76f31-103">override (C# Reference)</span></span>

<span data-ttu-id="76f31-104">El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.</span><span class="sxs-lookup"><span data-stu-id="76f31-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="76f31-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76f31-105">Example</span></span>

<span data-ttu-id="76f31-106">En este ejemplo, la clase `Square` debe proporcionar una implementación de invalidación de `GetArea` porque `GetArea` se hereda de la clase abstracta `Shape`:</span><span class="sxs-lookup"><span data-stu-id="76f31-106">In this example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="76f31-107">Un método `override` proporciona una nueva implementación de un miembro que se hereda de una clase base.</span><span class="sxs-lookup"><span data-stu-id="76f31-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="76f31-108">El método invalidado por una declaración `override` se conoce como método base invalidado.</span><span class="sxs-lookup"><span data-stu-id="76f31-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="76f31-109">El método base invalidado debe tener la misma firma que el método `override`.</span><span class="sxs-lookup"><span data-stu-id="76f31-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="76f31-110">Para obtener información sobre la herencia, vea [Herencia](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="76f31-110">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="76f31-111">No se puede invalidar un método estático o no virtual.</span><span class="sxs-lookup"><span data-stu-id="76f31-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="76f31-112">El método base invalidado debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="76f31-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="76f31-113">Una declaración `override` no puede cambiar la accesibilidad del método `virtual`.</span><span class="sxs-lookup"><span data-stu-id="76f31-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="76f31-114">El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="76f31-114">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="76f31-115">No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.</span><span class="sxs-lookup"><span data-stu-id="76f31-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="76f31-116">Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada, y la propiedad invalidada debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="76f31-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="76f31-117">Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="76f31-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="76f31-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76f31-118">Example</span></span>

<span data-ttu-id="76f31-119">En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="76f31-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="76f31-120">La clase `SalesEmployee` incluye un campo adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.</span><span class="sxs-lookup"><span data-stu-id="76f31-120">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="76f31-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="76f31-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="76f31-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="76f31-122">See also</span></span>

- [<span data-ttu-id="76f31-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="76f31-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="76f31-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="76f31-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="76f31-125">Herencia</span><span class="sxs-lookup"><span data-stu-id="76f31-125">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="76f31-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="76f31-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="76f31-127">Modificadores</span><span class="sxs-lookup"><span data-stu-id="76f31-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="76f31-128">abstract</span><span class="sxs-lookup"><span data-stu-id="76f31-128">abstract</span></span>](abstract.md)
- [<span data-ttu-id="76f31-129">virtual</span><span class="sxs-lookup"><span data-stu-id="76f31-129">virtual</span></span>](virtual.md)
- [<span data-ttu-id="76f31-130">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="76f31-130">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="76f31-131">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="76f31-131">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
