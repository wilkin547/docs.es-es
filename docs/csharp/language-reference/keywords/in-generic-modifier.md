---
title: "in (Modificador genérico) (Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 84773fca826b5a25679f1385a11c51b590ea20f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="036a1-102">in (Modificador genérico) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="036a1-102">in (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="036a1-103">Para los parámetros de tipo genérico, la palabra clave `in` especifica que el parámetro de tipo es contravariante.</span><span class="sxs-lookup"><span data-stu-id="036a1-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="036a1-104">Puede usar la palabra clave `in` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="036a1-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="036a1-105">La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="036a1-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="036a1-106">Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="036a1-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="036a1-107">La covarianza y la contravarianza de los parámetros de tipo genérico son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="036a1-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="036a1-108">Un tipo se puede declarar contravariante en una interfaz o delegado genéricos si solo se usa como tipo de argumentos de método y no se usa como tipo de un valor devuelto de un método.</span><span class="sxs-lookup"><span data-stu-id="036a1-108">A type can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="036a1-109">Los parámetros `Ref` y `out` no pueden ser variantes.</span><span class="sxs-lookup"><span data-stu-id="036a1-109">`Ref` and `out` parameters cannot be variant.</span></span>  
  
 <span data-ttu-id="036a1-110">Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="036a1-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="036a1-111">Por ejemplo, dado que en la interfaz <xref:System.Collections.Generic.IComparer%601> de .NET Framework 4 el tipo T es contravariante, puede asignar un objeto de tipo `IComparer(Of Person)` a un objeto de tipo `IComparer(Of Employee)` sin tener que usar ningún método de conversión especial si `Employee` hereda `Person`.</span><span class="sxs-lookup"><span data-stu-id="036a1-111">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="036a1-112">A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.</span><span class="sxs-lookup"><span data-stu-id="036a1-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="036a1-113">Para obtener más información, vea [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) (Covarianza y contravarianza).</span><span class="sxs-lookup"><span data-stu-id="036a1-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="036a1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="036a1-114">Example</span></span>  
 <span data-ttu-id="036a1-115">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.</span><span class="sxs-lookup"><span data-stu-id="036a1-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="036a1-116">También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="036a1-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="036a1-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="036a1-117">Example</span></span>  
 <span data-ttu-id="036a1-118">En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este.</span><span class="sxs-lookup"><span data-stu-id="036a1-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="036a1-119">También se muestra cómo puede convertir implícitamente un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="036a1-119">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="036a1-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="036a1-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="036a1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="036a1-121">See Also</span></span>  
 [<span data-ttu-id="036a1-122">out</span><span class="sxs-lookup"><span data-stu-id="036a1-122">out</span></span>](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [<span data-ttu-id="036a1-123">Covarianza y contravarianza</span><span class="sxs-lookup"><span data-stu-id="036a1-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="036a1-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="036a1-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
