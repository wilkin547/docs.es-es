---
title: override (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0f5a87eaa5894b61187c379c92ad785336aa79b2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="override-c-reference"></a><span data-ttu-id="bbb2b-102">override (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bbb2b-102">override (C# Reference)</span></span>
<span data-ttu-id="bbb2b-103">El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbb2b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbb2b-104">Example</span></span>  
 <span data-ttu-id="bbb2b-105">En este ejemplo, la clase `Square` debe proporcionar una implementación de invalidación de `Area` porque `Area` se hereda de la clase abstracta `ShapesClass`:</span><span class="sxs-lookup"><span data-stu-id="bbb2b-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 <span data-ttu-id="bbb2b-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbb2b-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span></span>  
  
 <span data-ttu-id="bbb2b-107">Un método `override` proporciona una nueva implementación de un miembro que se hereda de una clase base.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="bbb2b-108">El método invalidado por una declaración `override` se conoce como método base invalidado.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="bbb2b-109">El método base invalidado debe tener la misma firma que el método `override`.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="bbb2b-110">Para obtener información sobre la herencia, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="bbb2b-110">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="bbb2b-111">No se puede invalidar un método estático o no virtual.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="bbb2b-112">El método base invalidado debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="bbb2b-113">Una declaración `override` no puede cambiar la accesibilidad del método `virtual`.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="bbb2b-114">El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="bbb2b-114">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="bbb2b-115">No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="bbb2b-116">Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada, y la propiedad invalidada debe ser `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="bbb2b-117">Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="bbb2b-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbb2b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbb2b-118">Example</span></span>  
 <span data-ttu-id="bbb2b-119">En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="bbb2b-120">La clase `SalesEmployee` incluye una propiedad adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-120">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 <span data-ttu-id="bbb2b-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbb2b-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bbb2b-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bbb2b-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbb2b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbb2b-123">See Also</span></span>  
 <span data-ttu-id="bbb2b-124">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bbb2b-125">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bbb2b-126">[Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-126">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="bbb2b-127">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bbb2b-128">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-128">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="bbb2b-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="bbb2b-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 <span data-ttu-id="bbb2b-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="bbb2b-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="bbb2b-132">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="bbb2b-132">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)

