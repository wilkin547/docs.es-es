---
title: Not (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: cd93316ada1fcf0997922f71a8efc5a3cf411d09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614621"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="0b958-102">Not (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b958-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="0b958-103">Realiza una negación lógica en un `Boolean` expresión o una negación bit a bit en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="0b958-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b958-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b958-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0b958-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="0b958-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="0b958-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b958-106">Required.</span></span> <span data-ttu-id="0b958-107">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="0b958-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="0b958-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b958-108">Required.</span></span> <span data-ttu-id="0b958-109">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="0b958-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b958-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b958-110">Remarks</span></span>  
 <span data-ttu-id="0b958-111">Para `Boolean` expresiones, la tabla siguiente muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="0b958-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="0b958-112">Si `expression` es</span><span class="sxs-lookup"><span data-stu-id="0b958-112">If `expression` is</span></span>|<span data-ttu-id="0b958-113">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="0b958-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="0b958-114">Para expresiones numéricas, la `Not` operador invierte los valores de bits de cualquier expresión numérica y establece el bit en correspondiente `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="0b958-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="0b958-115">Si bit en `expression` es</span><span class="sxs-lookup"><span data-stu-id="0b958-115">If bit in `expression` is</span></span>|<span data-ttu-id="0b958-116">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="0b958-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="0b958-117">1</span><span class="sxs-lookup"><span data-stu-id="0b958-117">1</span></span>|<span data-ttu-id="0b958-118">0</span><span class="sxs-lookup"><span data-stu-id="0b958-118">0</span></span>|  
|<span data-ttu-id="0b958-119">0</span><span class="sxs-lookup"><span data-stu-id="0b958-119">0</span></span>|<span data-ttu-id="0b958-120">1</span><span class="sxs-lookup"><span data-stu-id="0b958-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0b958-121">Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar una correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="0b958-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="0b958-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0b958-122">Data Types</span></span>  
 <span data-ttu-id="0b958-123">En una negación booleana, el tipo de datos del resultado es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0b958-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="0b958-124">Para una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`.</span><span class="sxs-lookup"><span data-stu-id="0b958-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="0b958-125">Sin embargo, si la expresión es `Decimal`, el resultado es `Long`.</span><span class="sxs-lookup"><span data-stu-id="0b958-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0b958-126">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="0b958-126">Overloading</span></span>  
 <span data-ttu-id="0b958-127">El `Not` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="0b958-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="0b958-128">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="0b958-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0b958-129">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0b958-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b958-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b958-130">Example</span></span>  
 <span data-ttu-id="0b958-131">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica en un `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="0b958-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="0b958-132">El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="0b958-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="0b958-133">El ejemplo anterior genera los resultados de `False` y `True`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0b958-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b958-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b958-134">Example</span></span>  
 <span data-ttu-id="0b958-135">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de los bits individuales de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="0b958-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="0b958-136">El bit en el modelo resultante se establece en el orden inverso del bit correspondiente en el modelo del operando, incluido el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="0b958-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="0b958-137">El ejemplo anterior genera los resultados de – 11, – 9 y – 7, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0b958-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b958-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b958-138">See also</span></span>
- [<span data-ttu-id="0b958-139">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b958-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="0b958-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b958-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0b958-141">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="0b958-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0b958-142">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b958-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
