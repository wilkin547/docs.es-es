---
description: 'Modificador override: Referencia de C#'
title: 'Modificador override: Referencia de C#'
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434884"
---
# <a name="override-c-reference"></a><span data-ttu-id="93126-103">override (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="93126-103">override (C# reference)</span></span>

<span data-ttu-id="93126-104">El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.</span><span class="sxs-lookup"><span data-stu-id="93126-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

<span data-ttu-id="93126-105">En el siguiente ejemplo, la clase `Square` debe proporcionar una implementación invalidada de `GetArea`, ya que `GetArea` se hereda de la clase abstracta `Shape`:</span><span class="sxs-lookup"><span data-stu-id="93126-105">In the following example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="93126-106">Un método `override` proporciona una nueva implementación de un método heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="93126-106">An `override` method provides a new implementation of the method inherited from a base class.</span></span> <span data-ttu-id="93126-107">El método invalidado por una declaración `override` se conoce como método base invalidado.</span><span class="sxs-lookup"><span data-stu-id="93126-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="93126-108">Un método `override` debe tener la misma signatura que el método base invalidado.</span><span class="sxs-lookup"><span data-stu-id="93126-108">An `override` method must have the same signature as the overridden base method.</span></span> <span data-ttu-id="93126-109">A partir de C# 9.0, los métodos `override` admiten tipos de valor devuelto covariantes.</span><span class="sxs-lookup"><span data-stu-id="93126-109">Beginning with C# 9.0, `override` methods support covariant return types.</span></span> <span data-ttu-id="93126-110">En concreto, el tipo de valor devuelto de un método `override` puede derivar del tipo de valor devuelto del método base correspondiente.</span><span class="sxs-lookup"><span data-stu-id="93126-110">In particular, the return type of an `override` method can derive from the return type of the corresponding base method.</span></span> <span data-ttu-id="93126-111">En C# 8.0 y versiones anteriores, los tipos de valor devuelto de un método `override` y el método base invalidado deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="93126-111">In C# 8.0 and earlier, the return types of an `override` method and the overridden base method must be the same.</span></span>

<span data-ttu-id="93126-112">No se puede invalidar un método estático o no virtual.</span><span class="sxs-lookup"><span data-stu-id="93126-112">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="93126-113">El método base invalidado debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="93126-113">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="93126-114">Una declaración `override` no puede cambiar la accesibilidad del método `virtual`.</span><span class="sxs-lookup"><span data-stu-id="93126-114">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="93126-115">El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="93126-115">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="93126-116">No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.</span><span class="sxs-lookup"><span data-stu-id="93126-116">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="93126-117">Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada,.</span><span class="sxs-lookup"><span data-stu-id="93126-117">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property.</span></span> <span data-ttu-id="93126-118">A partir de C# 9.0, las propiedades de invalidación de solo lectura admiten tipos de valor devuelto covariantes.</span><span class="sxs-lookup"><span data-stu-id="93126-118">Beginning with C# 9.0, read-only overriding properties support covariant return types.</span></span> <span data-ttu-id="93126-119">La propiedad invalidada debe ser `virtual`, `abstract` u `override`.</span><span class="sxs-lookup"><span data-stu-id="93126-119">The overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="93126-120">Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="93126-120">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span> <span data-ttu-id="93126-121">Para obtener información sobre la herencia, vea [Herencia](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="93126-121">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

## <a name="example"></a><span data-ttu-id="93126-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93126-122">Example</span></span>

<span data-ttu-id="93126-123">En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="93126-123">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="93126-124">La clase `SalesEmployee` incluye un campo adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.</span><span class="sxs-lookup"><span data-stu-id="93126-124">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="93126-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="93126-125">C# language specification</span></span>

<span data-ttu-id="93126-126">Para obtener más información, vea la sección [Métodos de invalidación](~/_csharplang/spec/classes.md#override-methods) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="93126-126">For more information, see the [Override methods](~/_csharplang/spec/classes.md#override-methods) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="93126-127">Para obtener más información sobre tipos de valor devuelto covariantes, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span><span class="sxs-lookup"><span data-stu-id="93126-127">For more information about covariant return types, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93126-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="93126-128">See also</span></span>

- [<span data-ttu-id="93126-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="93126-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="93126-130">Herencia</span><span class="sxs-lookup"><span data-stu-id="93126-130">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="93126-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="93126-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="93126-132">Modificadores</span><span class="sxs-lookup"><span data-stu-id="93126-132">Modifiers</span></span>](index.md)
- [<span data-ttu-id="93126-133">abstract</span><span class="sxs-lookup"><span data-stu-id="93126-133">abstract</span></span>](abstract.md)
- [<span data-ttu-id="93126-134">virtual</span><span class="sxs-lookup"><span data-stu-id="93126-134">virtual</span></span>](virtual.md)
- [<span data-ttu-id="93126-135">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="93126-135">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="93126-136">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="93126-136">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
