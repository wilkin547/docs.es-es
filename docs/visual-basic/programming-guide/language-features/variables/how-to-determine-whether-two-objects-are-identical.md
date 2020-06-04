---
title: Procedimiento para determinar si dos objetos son idénticos
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 67c3af8b7bdac3ad1c7e4908f1ac2684df7a87aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410482"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="184b1-102">Cómo: Determinar si dos objetos son idénticos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="184b1-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="184b1-103">En Visual Basic, dos referencias a variables se consideran idénticas si sus punteros son iguales, es decir, si ambas variables apuntan a la misma instancia de clase en la memoria.</span><span class="sxs-lookup"><span data-stu-id="184b1-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="184b1-104">Por ejemplo, en una aplicación Windows Forms, es posible que desee realizar una comparación para determinar si la instancia actual ( `Me` ) es la misma que una instancia determinada, como `Form2` .</span><span class="sxs-lookup"><span data-stu-id="184b1-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="184b1-105">Visual Basic proporciona dos operadores para comparar los punteros.</span><span class="sxs-lookup"><span data-stu-id="184b1-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="184b1-106">El [operador is](../../../language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos y el [Operador IsNot](../../../language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.</span><span class="sxs-lookup"><span data-stu-id="184b1-106">The [Is Operator](../../../language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="184b1-107">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="184b1-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="184b1-108">Para determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="184b1-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="184b1-109">Configure una `Boolean` expresión para probar los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="184b1-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="184b1-110">En la expresión de prueba, utilice el `Is` operador con los dos objetos como operandos.</span><span class="sxs-lookup"><span data-stu-id="184b1-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="184b1-111">`Is`Devuelve `True` si los objetos apuntan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="184b1-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="184b1-112">Determinar si dos objetos no son idénticos</span><span class="sxs-lookup"><span data-stu-id="184b1-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="184b1-113">A veces, desea realizar una acción si los dos objetos no son idénticos y puede resultar complicado combinar `Not` y `Is` , por ejemplo `If Not obj1 Is obj2` .</span><span class="sxs-lookup"><span data-stu-id="184b1-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="184b1-114">En tal caso, puede usar el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="184b1-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="184b1-115">Para determinar si dos objetos no son idénticos</span><span class="sxs-lookup"><span data-stu-id="184b1-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="184b1-116">Configure una `Boolean` expresión para probar los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="184b1-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="184b1-117">En la expresión de prueba, utilice el `IsNot` operador con los dos objetos como operandos.</span><span class="sxs-lookup"><span data-stu-id="184b1-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="184b1-118">`IsNot`Devuelve `True` si los objetos no señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="184b1-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="184b1-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="184b1-119">Example</span></span>  
 <span data-ttu-id="184b1-120">En el ejemplo siguiente se prueban pares de `Object` variables para ver si señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="184b1-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="184b1-121">En el ejemplo anterior se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="184b1-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="184b1-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="184b1-122">See also</span></span>

- [<span data-ttu-id="184b1-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="184b1-123">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="184b1-124">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="184b1-124">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="184b1-125">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="184b1-125">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="184b1-126">Operador is</span><span class="sxs-lookup"><span data-stu-id="184b1-126">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="184b1-127">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="184b1-127">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="184b1-128">Procedimiento para determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="184b1-128">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="184b1-129">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="184b1-129">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
