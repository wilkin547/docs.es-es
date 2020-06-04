---
title: Operador Not
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
ms.openlocfilehash: 56cdeb80a217dbce15921eddd6a43d8d1b049376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401464"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="3155f-102">Not (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3155f-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="3155f-103">Realiza una negación lógica de una `Boolean` expresión o una negación bit a bit en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="3155f-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3155f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3155f-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3155f-105">Partes</span><span class="sxs-lookup"><span data-stu-id="3155f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="3155f-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="3155f-106">Required.</span></span> <span data-ttu-id="3155f-107">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3155f-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="3155f-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="3155f-108">Required.</span></span> <span data-ttu-id="3155f-109">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3155f-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3155f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3155f-110">Remarks</span></span>  
 <span data-ttu-id="3155f-111">En `Boolean` el caso de las expresiones, en la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="3155f-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="3155f-112">Si `expression` es </span><span class="sxs-lookup"><span data-stu-id="3155f-112">If `expression` is</span></span>|<span data-ttu-id="3155f-113">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="3155f-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="3155f-114">En el caso de las expresiones numéricas, el `Not` operador invierte los valores de bit de cualquier expresión numérica y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3155f-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="3155f-115">Si el bit de `expression` es</span><span class="sxs-lookup"><span data-stu-id="3155f-115">If bit in `expression` is</span></span>|<span data-ttu-id="3155f-116">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="3155f-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="3155f-117">1</span><span class="sxs-lookup"><span data-stu-id="3155f-117">1</span></span>|<span data-ttu-id="3155f-118">0</span><span class="sxs-lookup"><span data-stu-id="3155f-118">0</span></span>|  
|<span data-ttu-id="3155f-119">0</span><span class="sxs-lookup"><span data-stu-id="3155f-119">0</span></span>|<span data-ttu-id="3155f-120">1</span><span class="sxs-lookup"><span data-stu-id="3155f-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="3155f-121">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="3155f-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="3155f-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3155f-122">Data Types</span></span>  
 <span data-ttu-id="3155f-123">En el caso de una negación booleana, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="3155f-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="3155f-124">En el caso de una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression` .</span><span class="sxs-lookup"><span data-stu-id="3155f-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="3155f-125">Sin embargo, si Expression es `Decimal` , el resultado es `Long` .</span><span class="sxs-lookup"><span data-stu-id="3155f-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3155f-126">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="3155f-126">Overloading</span></span>  
 <span data-ttu-id="3155f-127">El `Not` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="3155f-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="3155f-128">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="3155f-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3155f-129">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3155f-129">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3155f-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3155f-130">Example</span></span>  
 <span data-ttu-id="3155f-131">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de una `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="3155f-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="3155f-132">El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="3155f-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="3155f-133">En el ejemplo anterior se generan los resultados de `False` y `True` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3155f-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3155f-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3155f-134">Example</span></span>  
 <span data-ttu-id="3155f-135">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de los bits individuales de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="3155f-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="3155f-136">El bit en el patrón del resultado se establece en la inversa del bit correspondiente en el patrón de operando, incluido el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="3155f-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="3155f-137">En el ejemplo anterior se generan los resultados de – 11, – 9 y – 7, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3155f-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3155f-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3155f-138">See also</span></span>

- [<span data-ttu-id="3155f-139">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3155f-139">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="3155f-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3155f-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="3155f-141">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="3155f-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="3155f-142">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3155f-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
