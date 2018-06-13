---
title: Out (Modificador genérico) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 7ba774bfcd629a7518602d4b971e86a690b2dd83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598158"
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="fd9ef-102">Out (Modificador genérico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd9ef-102">Out (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="fd9ef-103">Para los parámetros de tipo genérico, la `Out` palabra clave especifica que el tipo es covariante.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd9ef-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd9ef-104">Remarks</span></span>  
 <span data-ttu-id="fd9ef-105">La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="fd9ef-106">Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="fd9ef-107">Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="fd9ef-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="fd9ef-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="fd9ef-108">Rules</span></span>  
 <span data-ttu-id="fd9ef-109">Puede usar la palabra clave `Out` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="fd9ef-110">En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="fd9ef-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="fd9ef-111">El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd9ef-112">Hay una excepción para esta regla.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-112">There is one exception to this rule.</span></span> <span data-ttu-id="fd9ef-113">Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="fd9ef-114">Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fd9ef-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
-   <span data-ttu-id="fd9ef-115">El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
 <span data-ttu-id="fd9ef-116">En un delegado genérico, un parámetro de tipo se puede declarar covariante si se usa solo como un tipo de valor devuelto del método y no se usan para los argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
 <span data-ttu-id="fd9ef-117">La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="fd9ef-118">En Visual Basic, no puede declarar eventos en las interfaces covariantes sin especificar el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="fd9ef-119">Además, no pueden tener anidadas interfaces covariantes clases, enumeraciones o estructuras, pero puede haber interfaces anidadas.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="fd9ef-120">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="fd9ef-120">Behavior</span></span>  
 <span data-ttu-id="fd9ef-121">Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="fd9ef-122">Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerabe(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="fd9ef-123">A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd9ef-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd9ef-124">Example</span></span>  
 <span data-ttu-id="fd9ef-125">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="fd9ef-126">También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="fd9ef-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd9ef-127">Example</span></span>  
 <span data-ttu-id="fd9ef-128">En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="fd9ef-129">También muestra cómo puede usar la conversión implícita de tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="fd9ef-129">It also shows how you can use implicit conversion for delegate types.</span></span>  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fd9ef-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd9ef-130">See Also</span></span>  
 [<span data-ttu-id="fd9ef-131">Varianza en interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="fd9ef-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="fd9ef-132">In</span><span class="sxs-lookup"><span data-stu-id="fd9ef-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
