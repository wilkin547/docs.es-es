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
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701075"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="119be-102">Not (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="119be-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="119be-103">Realiza una negación lógica de una expresión de `Boolean` o una negación bit a bit en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="119be-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="119be-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="119be-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="119be-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="119be-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="119be-106">Required.</span></span> <span data-ttu-id="119be-107">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="119be-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="119be-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="119be-108">Required.</span></span> <span data-ttu-id="119be-109">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="119be-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="119be-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="119be-110">Remarks</span></span>  
 <span data-ttu-id="119be-111">En el caso de las expresiones `Boolean`, en la tabla siguiente se muestra cómo se determina `result`.</span><span class="sxs-lookup"><span data-stu-id="119be-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="119be-112">Si `expression` es</span><span class="sxs-lookup"><span data-stu-id="119be-112">If `expression` is</span></span>|<span data-ttu-id="119be-113">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="119be-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="119be-114">En el caso de las expresiones numéricas, el operador `Not` invierte los valores de bit de cualquier expresión numérica y establece el bit correspondiente en `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="119be-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="119be-115">Si el bit de `expression` es</span><span class="sxs-lookup"><span data-stu-id="119be-115">If bit in `expression` is</span></span>|<span data-ttu-id="119be-116">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="119be-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="119be-117">1</span><span class="sxs-lookup"><span data-stu-id="119be-117">1</span></span>|<span data-ttu-id="119be-118">0</span><span class="sxs-lookup"><span data-stu-id="119be-118">0</span></span>|  
|<span data-ttu-id="119be-119">0</span><span class="sxs-lookup"><span data-stu-id="119be-119">0</span></span>|<span data-ttu-id="119be-120">1</span><span class="sxs-lookup"><span data-stu-id="119be-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="119be-121">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="119be-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="119be-122">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="119be-122">Data Types</span></span>  
 <span data-ttu-id="119be-123">En el caso de una negación booleana, el tipo de datos del resultado es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="119be-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="119be-124">En el caso de una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`.</span><span class="sxs-lookup"><span data-stu-id="119be-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="119be-125">Sin embargo, si la expresión es `Decimal`, el resultado es `Long`.</span><span class="sxs-lookup"><span data-stu-id="119be-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="119be-126">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="119be-126">Overloading</span></span>  
 <span data-ttu-id="119be-127">El operador de `Not` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="119be-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="119be-128">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="119be-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="119be-129">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="119be-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="119be-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="119be-130">Example</span></span>  
 <span data-ttu-id="119be-131">En el ejemplo siguiente se usa el operador `Not` para realizar una negación lógica en una expresión `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="119be-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="119be-132">El resultado es un valor `Boolean` que representa el inverso del valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="119be-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="119be-133">En el ejemplo anterior se generan los resultados de `False` y `True`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="119be-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="119be-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="119be-134">Example</span></span>  
 <span data-ttu-id="119be-135">En el ejemplo siguiente se usa el operador `Not` para realizar la negación lógica de los bits individuales de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="119be-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="119be-136">El bit en el patrón del resultado se establece en la inversa del bit correspondiente en el patrón de operando, incluido el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="119be-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="119be-137">En el ejemplo anterior se generan los resultados de – 11, – 9 y – 7, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="119be-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119be-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="119be-138">See also</span></span>

- [<span data-ttu-id="119be-139">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="119be-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="119be-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="119be-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="119be-141">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="119be-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="119be-142">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="119be-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
