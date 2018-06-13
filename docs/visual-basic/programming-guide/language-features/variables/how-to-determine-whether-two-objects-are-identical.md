---
title: 'Cómo: Determinar si dos objetos son idénticos (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650103"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="cec4b-102">Cómo: Determinar si dos objetos son idénticos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cec4b-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="cec4b-103">En Visual Basic, dos referencias de variable se consideran idénticas si sus punteros son los mismos, es decir, si ambas variables señalan a la misma instancia de clase en la memoria.</span><span class="sxs-lookup"><span data-stu-id="cec4b-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="cec4b-104">Por ejemplo, en una aplicación de formularios Windows Forms, puede realizar una comparación para determinar si la instancia actual (`Me`) es el mismo que una instancia concreta, como `Form2`.</span><span class="sxs-lookup"><span data-stu-id="cec4b-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="cec4b-105">Visual Basic proporciona dos operadores para comparar los punteros.</span><span class="sxs-lookup"><span data-stu-id="cec4b-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="cec4b-106">El [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos y el [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.</span><span class="sxs-lookup"><span data-stu-id="cec4b-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="cec4b-107">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="cec4b-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="cec4b-108">Para determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="cec4b-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="cec4b-109">Configurar un `Boolean` expresión que se va a probar los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="cec4b-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="cec4b-110">En la expresión de prueba, use la `Is` operador con los dos objetos como operandos.</span><span class="sxs-lookup"><span data-stu-id="cec4b-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="cec4b-111">`Is` Devuelve `True` si los objetos señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="cec4b-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="cec4b-112">Determinar si dos objetos no son idénticos</span><span class="sxs-lookup"><span data-stu-id="cec4b-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="cec4b-113">A veces, desea realizar una acción si los dos objetos no son idénticos, y puede ser difícil combinar `Not` y `Is`, por ejemplo `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="cec4b-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="cec4b-114">En tal caso puede usar el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="cec4b-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="cec4b-115">Para determinar si dos objetos no son idénticos</span><span class="sxs-lookup"><span data-stu-id="cec4b-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="cec4b-116">Configurar un `Boolean` expresión que se va a probar los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="cec4b-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="cec4b-117">En la expresión de prueba, use la `IsNot` operador con los dos objetos como operandos.</span><span class="sxs-lookup"><span data-stu-id="cec4b-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="cec4b-118">`IsNot` Devuelve `True` si los objetos no señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="cec4b-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cec4b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cec4b-119">Example</span></span>  
 <span data-ttu-id="cec4b-120">El ejemplo siguiente prueba pares de `Object` las variables para ver si señalan a la misma instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="cec4b-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 <span data-ttu-id="cec4b-121">En el ejemplo anterior se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="cec4b-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="cec4b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cec4b-122">See Also</span></span>  
 [<span data-ttu-id="cec4b-123">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="cec4b-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="cec4b-124">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="cec4b-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="cec4b-125">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="cec4b-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="cec4b-126">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="cec4b-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="cec4b-127">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="cec4b-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="cec4b-128">Determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="cec4b-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="cec4b-129">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="cec4b-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
