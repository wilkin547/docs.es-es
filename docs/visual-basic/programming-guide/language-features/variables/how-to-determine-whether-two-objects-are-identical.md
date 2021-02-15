---
description: 'Más información acerca de cómo: determinar si dos objetos son idénticos (Visual Basic)'
title: Procedimiento para determinar si dos objetos son idénticos
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 91f431b5a7e4cf51135c060ca0aebf1b3b968b25
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481901"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="c2e4b-103">Cómo: Determinar si dos objetos son idénticos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2e4b-103">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>

<span data-ttu-id="c2e4b-104">En Visual Basic, dos referencias a variables se consideran idénticas si sus punteros son iguales, es decir, si ambas variables apuntan a la misma instancia de clase en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-104">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="c2e4b-105">Por ejemplo, en una aplicación Windows Forms, es posible que desee realizar una comparación para determinar si la instancia actual ( `Me` ) es la misma que una instancia determinada, como `Form2` .</span><span class="sxs-lookup"><span data-stu-id="c2e4b-105">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="c2e4b-106">Visual Basic proporciona dos operadores para comparar los punteros.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-106">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="c2e4b-107">El [operador is](../../../language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos y el [Operador IsNot](../../../language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-107">The [Is Operator](../../../language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="c2e4b-108">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="c2e4b-108">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="c2e4b-109">Para determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="c2e4b-109">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="c2e4b-110">Configure una `Boolean` expresión para probar los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-110">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="c2e4b-111">En la expresión de prueba, utilice el `Is` operador con los dos objetos como operandos.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-111">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="c2e4b-112">`Is` Devuelve `True` si los objetos apuntan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-112">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="c2e4b-113">Determinar si dos objetos no son idénticos</span><span class="sxs-lookup"><span data-stu-id="c2e4b-113">Determining if Two Objects Are Not Identical</span></span>  

 <span data-ttu-id="c2e4b-114">A veces, desea realizar una acción si los dos objetos no son idénticos y puede resultar complicado combinar `Not` y `Is` , por ejemplo `If Not obj1 Is obj2` .</span><span class="sxs-lookup"><span data-stu-id="c2e4b-114">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="c2e4b-115">En tal caso, puede usar el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-115">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="c2e4b-116">Para determinar si dos objetos no son idénticos</span><span class="sxs-lookup"><span data-stu-id="c2e4b-116">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="c2e4b-117">Configure una `Boolean` expresión para probar los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-117">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="c2e4b-118">En la expresión de prueba, utilice el `IsNot` operador con los dos objetos como operandos.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-118">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="c2e4b-119">`IsNot` Devuelve `True` si los objetos no señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-119">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2e4b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2e4b-120">Example</span></span>  

 <span data-ttu-id="c2e4b-121">En el ejemplo siguiente se prueban pares de `Object` variables para ver si señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-121">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="c2e4b-122">En el ejemplo anterior se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="c2e4b-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="c2e4b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2e4b-123">See also</span></span>

- [<span data-ttu-id="c2e4b-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="c2e4b-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="c2e4b-125">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="c2e4b-125">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="c2e4b-126">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="c2e4b-126">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="c2e4b-127">Operador Is</span><span class="sxs-lookup"><span data-stu-id="c2e4b-127">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="c2e4b-128">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="c2e4b-128">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="c2e4b-129">Procedimiento para determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="c2e4b-129">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="c2e4b-130">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="c2e4b-130">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
