---
title: 'Modificador override: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: acad3aa3b196c184132ad1acdf52b18a799b0896
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713253"
---
# <a name="override-c-reference"></a><span data-ttu-id="82b80-102">override (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="82b80-102">override (C# Reference)</span></span>

<span data-ttu-id="82b80-103">El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.</span><span class="sxs-lookup"><span data-stu-id="82b80-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="82b80-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82b80-104">Example</span></span>

<span data-ttu-id="82b80-105">En este ejemplo, la clase `Square` debe proporcionar una implementación de invalidación de `GetArea` porque `GetArea` se hereda de la clase abstracta `Shape`:</span><span class="sxs-lookup"><span data-stu-id="82b80-105">In this example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="82b80-106">Un método `override` proporciona una nueva implementación de un miembro que se hereda de una clase base.</span><span class="sxs-lookup"><span data-stu-id="82b80-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="82b80-107">El método invalidado por una declaración `override` se conoce como método base invalidado.</span><span class="sxs-lookup"><span data-stu-id="82b80-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="82b80-108">El método base invalidado debe tener la misma firma que el método `override`.</span><span class="sxs-lookup"><span data-stu-id="82b80-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="82b80-109">Para obtener información sobre la herencia, vea [Herencia](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="82b80-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="82b80-110">No se puede invalidar un método estático o no virtual.</span><span class="sxs-lookup"><span data-stu-id="82b80-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="82b80-111">El método base invalidado debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="82b80-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="82b80-112">Una declaración `override` no puede cambiar la accesibilidad del método `virtual`.</span><span class="sxs-lookup"><span data-stu-id="82b80-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="82b80-113">El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="82b80-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="82b80-114">No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.</span><span class="sxs-lookup"><span data-stu-id="82b80-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="82b80-115">Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada, y la propiedad invalidada debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="82b80-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="82b80-116">Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="82b80-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="82b80-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82b80-117">Example</span></span>

<span data-ttu-id="82b80-118">En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="82b80-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="82b80-119">La clase `SalesEmployee` incluye un campo adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.</span><span class="sxs-lookup"><span data-stu-id="82b80-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="82b80-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="82b80-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="82b80-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="82b80-121">See also</span></span>

- [<span data-ttu-id="82b80-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="82b80-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="82b80-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="82b80-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="82b80-124">Herencia</span><span class="sxs-lookup"><span data-stu-id="82b80-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="82b80-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="82b80-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="82b80-126">Modificadores</span><span class="sxs-lookup"><span data-stu-id="82b80-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="82b80-127">abstract</span><span class="sxs-lookup"><span data-stu-id="82b80-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="82b80-128">virtual</span><span class="sxs-lookup"><span data-stu-id="82b80-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="82b80-129">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="82b80-129">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="82b80-130">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="82b80-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
