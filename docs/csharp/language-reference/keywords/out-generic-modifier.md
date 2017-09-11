---
title: "out (Modificador genérico) (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: 15
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
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: a560a0307723d32750a7e26ad4ee1afec360a849
ms.contentlocale: es-es
ms.lasthandoff: 08/11/2017

---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="3d366-102">out (Modificador genérico) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3d366-102">out (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="3d366-103">Para los parámetros de tipo genérico, la palabra clave `out` especifica que el parámetro de tipo es covariante.</span><span class="sxs-lookup"><span data-stu-id="3d366-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="3d366-104">Puede usar la palabra clave `out` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="3d366-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="3d366-105">La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="3d366-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="3d366-106">Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="3d366-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="3d366-107">La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="3d366-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="3d366-108">Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="3d366-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="3d366-109">Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerabe(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.</span><span class="sxs-lookup"><span data-stu-id="3d366-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="3d366-110">A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.</span><span class="sxs-lookup"><span data-stu-id="3d366-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
 <span data-ttu-id="3d366-111">Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="3d366-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d366-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d366-112">Example</span></span>  
 <span data-ttu-id="3d366-113">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante.</span><span class="sxs-lookup"><span data-stu-id="3d366-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="3d366-114">También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.</span><span class="sxs-lookup"><span data-stu-id="3d366-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 <span data-ttu-id="3d366-115">[!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3d366-115">[!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="3d366-116">En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="3d366-116">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="3d366-117">El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="3d366-117">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d366-118">Hay una excepción para esta regla.</span><span class="sxs-lookup"><span data-stu-id="3d366-118">There is one exception to this rule.</span></span> <span data-ttu-id="3d366-119">Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado.</span><span class="sxs-lookup"><span data-stu-id="3d366-119">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="3d366-120">Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) y [Usar la varianza para los delegados genéricos Func y Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span><span class="sxs-lookup"><span data-stu-id="3d366-120">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) and [Using Variance for Func and Action Generic Delegates](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span></span>  
  
-   <span data-ttu-id="3d366-121">El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3d366-121">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d366-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d366-122">Example</span></span>  
 <span data-ttu-id="3d366-123">En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante.</span><span class="sxs-lookup"><span data-stu-id="3d366-123">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="3d366-124">También se muestra cómo convertir implícitamente los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="3d366-124">It also shows how to implicitly convert delegate types.</span></span>  
  
 <span data-ttu-id="3d366-125">[!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3d366-125">[!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]</span></span>  
  
 <span data-ttu-id="3d366-126">En un delegado genérico, un tipo se puede declarar como covariante si se usa solamente como tipo de valor devuelto por un método y no se usa para los argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="3d366-126">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3d366-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3d366-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d366-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d366-128">See Also</span></span>  
 <span data-ttu-id="3d366-129">[Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="3d366-129">[Variance in Generic Interfaces](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
 <span data-ttu-id="3d366-130">[in (Modificador genérico)](../../../csharp/language-reference/keywords/in-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="3d366-130">[in](../../../csharp/language-reference/keywords/in-generic-modifier.md) </span></span>  
 [<span data-ttu-id="3d366-131">Modificadores</span><span class="sxs-lookup"><span data-stu-id="3d366-131">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

