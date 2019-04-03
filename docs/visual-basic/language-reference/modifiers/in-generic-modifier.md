---
title: In (Modificador genérico) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: d8d503f0814a89c977cdc208eced026b2d8cb1fd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838942"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="2ab7c-102">In (Modificador genérico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ab7c-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="2ab7c-103">Para los parámetros de tipo genérico, la palabra clave `In` especifica que el parámetro de tipo es contravariante.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ab7c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ab7c-104">Remarks</span></span>  
 <span data-ttu-id="2ab7c-105">La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="2ab7c-106">Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="2ab7c-107">Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ab7c-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2ab7c-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="2ab7c-108">Rules</span></span>  
 <span data-ttu-id="2ab7c-109">Puede usar la palabra clave `In` en las interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="2ab7c-110">Un parámetro de tipo se puede declarar contravariante en una interfaz o delegado genéricos si se usa solamente como un tipo de argumentos de método y no se usa como un tipo de valor devuelto del método.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="2ab7c-111">`ByRef` parámetros no pueden ser covariantes o contravariantes.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="2ab7c-112">Covarianza y contravarianza son compatibles con tipos de referencia y no se admite para tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="2ab7c-113">En Visual Basic, no puede declarar eventos en interfaces contravariantes sin especificar el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="2ab7c-114">Además, una interfaz contravariante no puede tener anidadas clases, enumeraciones o estructuras, pero puede haber interfaces anidadas.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2ab7c-115">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="2ab7c-115">Behavior</span></span>  
 <span data-ttu-id="2ab7c-116">Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="2ab7c-117">Por ejemplo, dado que en la interfaz <xref:System.Collections.Generic.IComparer%601> de .NET Framework 4 el tipo T es contravariante, puede asignar un objeto de tipo `IComparer(Of Person)` a un objeto de tipo `IComparer(Of Employee)` sin tener que usar ningún método de conversión especial si `Person` hereda `Employee`.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="2ab7c-118">A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ab7c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ab7c-119">Example</span></span>  
 <span data-ttu-id="2ab7c-120">En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="2ab7c-121">También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="2ab7c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ab7c-122">Example</span></span>  
 <span data-ttu-id="2ab7c-123">En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="2ab7c-124">También se muestra cómo puede convertir implícitamente un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="2ab7c-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2ab7c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ab7c-125">See also</span></span>

- [<span data-ttu-id="2ab7c-126">Varianza en interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="2ab7c-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="2ab7c-127">Out</span><span class="sxs-lookup"><span data-stu-id="2ab7c-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
