---
title: In (modificador genérico)-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004872"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="eab6e-102">In (Modificador genérico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eab6e-102">In (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="eab6e-103">Para los parámetros de tipo genérico, la palabra clave `In` especifica que el parámetro de tipo es contravariante.</span><span class="sxs-lookup"><span data-stu-id="eab6e-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="eab6e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eab6e-104">Remarks</span></span>

<span data-ttu-id="eab6e-105">La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="eab6e-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="eab6e-106">Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="eab6e-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="eab6e-107">Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="eab6e-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="eab6e-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="eab6e-108">Rules</span></span>

<span data-ttu-id="eab6e-109">Puede usar la palabra clave `In` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="eab6e-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>
  
<span data-ttu-id="eab6e-110">Un parámetro de tipo puede declararse como contravariante en una interfaz o un delegado genérico si solo se usa como un tipo de argumentos de método y no se usa como tipo de valor devuelto de método.</span><span class="sxs-lookup"><span data-stu-id="eab6e-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="eab6e-111">los parámetros `ByRef` no pueden ser covariantes o contravariante.</span><span class="sxs-lookup"><span data-stu-id="eab6e-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>

<span data-ttu-id="eab6e-112">La covarianza y la contravarianza se admiten para los tipos de referencia y no se admiten para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="eab6e-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>

<span data-ttu-id="eab6e-113">En Visual Basic, no se pueden declarar eventos en interfaces contravariantes sin especificar el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="eab6e-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="eab6e-114">Además, las interfaces contravariantes no pueden tener clases anidadas, enumeraciones o estructuras, pero pueden tener interfaces anidadas.</span><span class="sxs-lookup"><span data-stu-id="eab6e-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="eab6e-115">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="eab6e-115">Behavior</span></span>

<span data-ttu-id="eab6e-116">Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="eab6e-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="eab6e-117">Por ejemplo, dado que en .NET Framework 4, en la interfaz <xref:System.Collections.Generic.IComparer%601>, el tipo T es contravariante, puede asignar un objeto del tipo `IComparer(Of Person)` a un objeto del tipo `IComparer(Of Employee)` sin usar ningún método de conversión especial si `Employee` hereda de `Person`.</span><span class="sxs-lookup"><span data-stu-id="eab6e-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits from `Person`.</span></span>

<span data-ttu-id="eab6e-118">A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.</span><span class="sxs-lookup"><span data-stu-id="eab6e-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

## <a name="example---contravariant-generic-interface"></a><span data-ttu-id="eab6e-119">Ejemplo: interfaz genérica contravariante</span><span class="sxs-lookup"><span data-stu-id="eab6e-119">Example - contravariant generic interface</span></span>

<span data-ttu-id="eab6e-120">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.</span><span class="sxs-lookup"><span data-stu-id="eab6e-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="eab6e-121">También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="eab6e-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a><span data-ttu-id="eab6e-122">Ejemplo: delegado genérico contravariante</span><span class="sxs-lookup"><span data-stu-id="eab6e-122">Example - contravariant generic delegate</span></span>

<span data-ttu-id="eab6e-123">En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este.</span><span class="sxs-lookup"><span data-stu-id="eab6e-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="eab6e-124">También se muestra cómo puede convertir implícitamente un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="eab6e-124">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="eab6e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="eab6e-125">See also</span></span>

- [<span data-ttu-id="eab6e-126">Varianza en interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="eab6e-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="eab6e-127">Out</span><span class="sxs-lookup"><span data-stu-id="eab6e-127">Out</span></span>](out-generic-modifier.md)
