---
title: override (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 8f692dfdf8bd34ddb62623d86ec3dadd2b8dead3
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199269"
---
# <a name="override-c-reference"></a><span data-ttu-id="a8e80-102">override (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a8e80-102">override (C# Reference)</span></span>
<span data-ttu-id="a8e80-103">El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.</span><span class="sxs-lookup"><span data-stu-id="a8e80-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8e80-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8e80-104">Example</span></span>  
 <span data-ttu-id="a8e80-105">En este ejemplo, la clase `Square` debe proporcionar una implementación de invalidación de `Area` porque `Area` se hereda de la clase abstracta `ShapesClass`:</span><span class="sxs-lookup"><span data-stu-id="a8e80-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 <span data-ttu-id="a8e80-106">Un método `override` proporciona una nueva implementación de un miembro que se hereda de una clase base.</span><span class="sxs-lookup"><span data-stu-id="a8e80-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="a8e80-107">El método invalidado por una declaración `override` se conoce como método base invalidado.</span><span class="sxs-lookup"><span data-stu-id="a8e80-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="a8e80-108">El método base invalidado debe tener la misma firma que el método `override`.</span><span class="sxs-lookup"><span data-stu-id="a8e80-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="a8e80-109">Para obtener información sobre la herencia, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="a8e80-109">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="a8e80-110">No se puede invalidar un método estático o no virtual.</span><span class="sxs-lookup"><span data-stu-id="a8e80-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="a8e80-111">El método base invalidado debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="a8e80-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="a8e80-112">Una declaración `override` no puede cambiar la accesibilidad del método `virtual`.</span><span class="sxs-lookup"><span data-stu-id="a8e80-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="a8e80-113">El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a8e80-113">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="a8e80-114">No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.</span><span class="sxs-lookup"><span data-stu-id="a8e80-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="a8e80-115">Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada, y la propiedad invalidada debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="a8e80-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="a8e80-116">Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="a8e80-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8e80-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8e80-117">Example</span></span>  
 <span data-ttu-id="a8e80-118">En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="a8e80-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="a8e80-119">La clase `SalesEmployee` incluye una propiedad adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.</span><span class="sxs-lookup"><span data-stu-id="a8e80-119">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a8e80-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a8e80-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a8e80-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8e80-121">See Also</span></span>  
 [<span data-ttu-id="a8e80-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a8e80-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a8e80-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a8e80-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a8e80-124">Herencia</span><span class="sxs-lookup"><span data-stu-id="a8e80-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [<span data-ttu-id="a8e80-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a8e80-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a8e80-126">Modificadores</span><span class="sxs-lookup"><span data-stu-id="a8e80-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="a8e80-127">abstract</span><span class="sxs-lookup"><span data-stu-id="a8e80-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="a8e80-128">virtual</span><span class="sxs-lookup"><span data-stu-id="a8e80-128">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="a8e80-129">new</span><span class="sxs-lookup"><span data-stu-id="a8e80-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="a8e80-130">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="a8e80-130">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)
