---
title: 'in (Modificador genérico): Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: 57da13f6dc6719166b9051afeb2532ba5fbeff3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713487"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="5bf20-102">in (Modificador genérico) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5bf20-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="5bf20-103">Para los parámetros de tipo genérico, la palabra clave `in` especifica que el parámetro de tipo es contravariante.</span><span class="sxs-lookup"><span data-stu-id="5bf20-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="5bf20-104">Puede usar la palabra clave `in` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="5bf20-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="5bf20-105">La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="5bf20-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="5bf20-106">Esto permite la conversión implícita de las clases que implementan interfaces contravariantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="5bf20-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="5bf20-107">La covarianza y la contravarianza de los parámetros de tipo genérico son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="5bf20-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="5bf20-108">Un tipo se puede declarar contravariante en una interfaz o un delgado genéricos solo si define el tipo de parámetros de un método y no el tipo de valor devuelto de un método.</span><span class="sxs-lookup"><span data-stu-id="5bf20-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="5bf20-109">Los parámetros `In`, `ref` y `out` deben ser invariables, es decir, ni covariantes ni contravariantes.</span><span class="sxs-lookup"><span data-stu-id="5bf20-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="5bf20-110">Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5bf20-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="5bf20-111">Por ejemplo, en la interfaz <xref:System.Collections.Generic.IComparer%601>, el tipo T es contravariante, puede asignar un objeto de tipo `IComparer<Person>` a un objeto de tipo `IComparer<Employee>` sin tener que usar ningún método de conversión especial si `Employee` hereda `Person`.</span><span class="sxs-lookup"><span data-stu-id="5bf20-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="5bf20-112">A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.</span><span class="sxs-lookup"><span data-stu-id="5bf20-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="5bf20-113">Para obtener más información, vea [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) (Covarianza y contravarianza).</span><span class="sxs-lookup"><span data-stu-id="5bf20-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="5bf20-114">Interfaz genérica contravariante</span><span class="sxs-lookup"><span data-stu-id="5bf20-114">Contravariant generic interface</span></span>

<span data-ttu-id="5bf20-115">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.</span><span class="sxs-lookup"><span data-stu-id="5bf20-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="5bf20-116">También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="5bf20-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="5bf20-117">Delegado genérico contravariante</span><span class="sxs-lookup"><span data-stu-id="5bf20-117">Contravariant generic delegate</span></span>

<span data-ttu-id="5bf20-118">En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este.</span><span class="sxs-lookup"><span data-stu-id="5bf20-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="5bf20-119">También se muestra cómo puede convertir implícitamente un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="5bf20-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="5bf20-120">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5bf20-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5bf20-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bf20-121">See also</span></span>

- [<span data-ttu-id="5bf20-122">out</span><span class="sxs-lookup"><span data-stu-id="5bf20-122">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="5bf20-123">Covarianza y contravarianza</span><span class="sxs-lookup"><span data-stu-id="5bf20-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="5bf20-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="5bf20-124">Modifiers</span></span>](index.md)
