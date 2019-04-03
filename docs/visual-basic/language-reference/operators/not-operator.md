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
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824218"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="f3ab6-102">Not (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3ab6-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="f3ab6-103">Realiza una negación lógica en un `Boolean` expresión o una negación bit a bit en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ab6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3ab6-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f3ab6-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f3ab6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f3ab6-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-106">Required.</span></span> <span data-ttu-id="f3ab6-107">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="f3ab6-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-108">Required.</span></span> <span data-ttu-id="f3ab6-109">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3ab6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3ab6-110">Remarks</span></span>  
 <span data-ttu-id="f3ab6-111">Para `Boolean` expresiones, la tabla siguiente muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f3ab6-112">Si `expression` es</span><span class="sxs-lookup"><span data-stu-id="f3ab6-112">If `expression` is</span></span>|<span data-ttu-id="f3ab6-113">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="f3ab6-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="f3ab6-114">Para expresiones numéricas, la `Not` operador invierte los valores de bits de cualquier expresión numérica y establece el bit en correspondiente `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="f3ab6-115">Si bit en `expression` es</span><span class="sxs-lookup"><span data-stu-id="f3ab6-115">If bit in `expression` is</span></span>|<span data-ttu-id="f3ab6-116">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="f3ab6-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="f3ab6-117">1</span><span class="sxs-lookup"><span data-stu-id="f3ab6-117">1</span></span>|<span data-ttu-id="f3ab6-118">0</span><span class="sxs-lookup"><span data-stu-id="f3ab6-118">0</span></span>|  
|<span data-ttu-id="f3ab6-119">0</span><span class="sxs-lookup"><span data-stu-id="f3ab6-119">0</span></span>|<span data-ttu-id="f3ab6-120">1</span><span class="sxs-lookup"><span data-stu-id="f3ab6-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f3ab6-121">Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar una correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f3ab6-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f3ab6-122">Data Types</span></span>  
 <span data-ttu-id="f3ab6-123">En una negación booleana, el tipo de datos del resultado es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="f3ab6-124">Para una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="f3ab6-125">Sin embargo, si la expresión es `Decimal`, el resultado es `Long`.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f3ab6-126">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f3ab6-126">Overloading</span></span>  
 <span data-ttu-id="f3ab6-127">El `Not` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="f3ab6-128">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f3ab6-129">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f3ab6-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3ab6-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3ab6-130">Example</span></span>  
 <span data-ttu-id="f3ab6-131">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica en un `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="f3ab6-132">El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="f3ab6-133">El ejemplo anterior genera los resultados de `False` y `True`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3ab6-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3ab6-134">Example</span></span>  
 <span data-ttu-id="f3ab6-135">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de los bits individuales de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="f3ab6-136">El bit en el modelo resultante se establece en el orden inverso del bit correspondiente en el modelo del operando, incluido el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="f3ab6-137">El ejemplo anterior genera los resultados de – 11, – 9 y – 7, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f3ab6-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ab6-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3ab6-138">See also</span></span>

- [<span data-ttu-id="f3ab6-139">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3ab6-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="f3ab6-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3ab6-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f3ab6-141">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f3ab6-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f3ab6-142">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3ab6-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
