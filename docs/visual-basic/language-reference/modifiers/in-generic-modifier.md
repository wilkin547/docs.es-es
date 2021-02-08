---
description: 'Más información sobre: in (modificador genérico) (Visual Basic)'
title: In (modificador genérico)-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: e6ac95a77253b28e45a4be8a29623bdd76a231f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774543"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="897a8-103">In (Modificador genérico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="897a8-103">In (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="897a8-104">Para los parámetros de tipo genérico, la palabra clave `In` especifica que el parámetro de tipo es contravariante.</span><span class="sxs-lookup"><span data-stu-id="897a8-104">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="897a8-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="897a8-105">Remarks</span></span>

<span data-ttu-id="897a8-106">La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="897a8-106">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="897a8-107">Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="897a8-107">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="897a8-108">Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="897a8-108">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="897a8-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="897a8-109">Rules</span></span>

<span data-ttu-id="897a8-110">Puede usar la palabra clave `In` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="897a8-110">You can use the `In` keyword in generic interfaces and delegates.</span></span>
  
<span data-ttu-id="897a8-111">Un parámetro de tipo puede declararse como contravariante en una interfaz o un delegado genérico si solo se usa como un tipo de argumentos de método y no se usa como tipo de valor devuelto de método.</span><span class="sxs-lookup"><span data-stu-id="897a8-111">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="897a8-112">`ByRef` los parámetros no pueden ser covariantes ni contravariante.</span><span class="sxs-lookup"><span data-stu-id="897a8-112">`ByRef` parameters cannot be covariant or contravariant.</span></span>

<span data-ttu-id="897a8-113">La covarianza y la contravarianza se admiten para los tipos de referencia y no se admiten para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="897a8-113">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>

<span data-ttu-id="897a8-114">En Visual Basic, no se pueden declarar eventos en interfaces contravariantes sin especificar el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="897a8-114">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="897a8-115">Además, las interfaces contravariantes no pueden tener clases anidadas, enumeraciones o estructuras, pero pueden tener interfaces anidadas.</span><span class="sxs-lookup"><span data-stu-id="897a8-115">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="897a8-116">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="897a8-116">Behavior</span></span>

<span data-ttu-id="897a8-117">Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="897a8-117">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="897a8-118">Por ejemplo, dado que en .NET Framework 4, en la <xref:System.Collections.Generic.IComparer%601> interfaz, el tipo T es contravariante, puede asignar un objeto del `IComparer(Of Person)` tipo a un objeto del `IComparer(Of Employee)` tipo sin usar ningún método de conversión especial si `Employee` hereda de `Person` .</span><span class="sxs-lookup"><span data-stu-id="897a8-118">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits from `Person`.</span></span>

<span data-ttu-id="897a8-119">A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.</span><span class="sxs-lookup"><span data-stu-id="897a8-119">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

## <a name="example---contravariant-generic-interface"></a><span data-ttu-id="897a8-120">Ejemplo: interfaz genérica contravariante</span><span class="sxs-lookup"><span data-stu-id="897a8-120">Example - contravariant generic interface</span></span>

<span data-ttu-id="897a8-121">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.</span><span class="sxs-lookup"><span data-stu-id="897a8-121">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="897a8-122">También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="897a8-122">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a><span data-ttu-id="897a8-123">Ejemplo: delegado genérico contravariante</span><span class="sxs-lookup"><span data-stu-id="897a8-123">Example - contravariant generic delegate</span></span>

<span data-ttu-id="897a8-124">En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este.</span><span class="sxs-lookup"><span data-stu-id="897a8-124">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="897a8-125">También se muestra cómo puede convertir implícitamente un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="897a8-125">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="897a8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="897a8-126">See also</span></span>

- [<span data-ttu-id="897a8-127">Varianza en interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="897a8-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="897a8-128">Fuera</span><span class="sxs-lookup"><span data-stu-id="897a8-128">Out</span></span>](out-generic-modifier.md)
