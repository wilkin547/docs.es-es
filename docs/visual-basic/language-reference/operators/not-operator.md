---
description: 'Más información acerca de: operador not (Visual Basic)'
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
ms.openlocfilehash: 91f3525b52d6f38081b8e5ba208c193f714a4045
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665359"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="45e6f-103">Not (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45e6f-103">Not Operator (Visual Basic)</span></span>

<span data-ttu-id="45e6f-104">Realiza una negación lógica de una `Boolean` expresión o una negación bit a bit en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="45e6f-104">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e6f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45e6f-105">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="45e6f-106">Partes</span><span class="sxs-lookup"><span data-stu-id="45e6f-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="45e6f-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="45e6f-107">Required.</span></span> <span data-ttu-id="45e6f-108">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="45e6f-108">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="45e6f-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="45e6f-109">Required.</span></span> <span data-ttu-id="45e6f-110">Cualquier expresión numérica o de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="45e6f-110">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45e6f-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45e6f-111">Remarks</span></span>  

 <span data-ttu-id="45e6f-112">En `Boolean` el caso de las expresiones, en la tabla siguiente se muestra cómo `result` se determina.</span><span class="sxs-lookup"><span data-stu-id="45e6f-112">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="45e6f-113">Si `expression` es </span><span class="sxs-lookup"><span data-stu-id="45e6f-113">If `expression` is</span></span>|<span data-ttu-id="45e6f-114">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="45e6f-114">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="45e6f-115">En el caso de las expresiones numéricas, el `Not` operador invierte los valores de bit de cualquier expresión numérica y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="45e6f-115">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="45e6f-116">Si el bit de `expression` es</span><span class="sxs-lookup"><span data-stu-id="45e6f-116">If bit in `expression` is</span></span>|<span data-ttu-id="45e6f-117">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="45e6f-117">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="45e6f-118">1</span><span class="sxs-lookup"><span data-stu-id="45e6f-118">1</span></span>|<span data-ttu-id="45e6f-119">0</span><span class="sxs-lookup"><span data-stu-id="45e6f-119">0</span></span>|  
|<span data-ttu-id="45e6f-120">0</span><span class="sxs-lookup"><span data-stu-id="45e6f-120">0</span></span>|<span data-ttu-id="45e6f-121">1</span><span class="sxs-lookup"><span data-stu-id="45e6f-121">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="45e6f-122">Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.</span><span class="sxs-lookup"><span data-stu-id="45e6f-122">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="45e6f-123">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="45e6f-123">Data Types</span></span>  

 <span data-ttu-id="45e6f-124">En el caso de una negación booleana, el tipo de datos del resultado es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="45e6f-124">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="45e6f-125">En el caso de una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression` .</span><span class="sxs-lookup"><span data-stu-id="45e6f-125">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="45e6f-126">Sin embargo, si Expression es `Decimal` , el resultado es `Long` .</span><span class="sxs-lookup"><span data-stu-id="45e6f-126">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="45e6f-127">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="45e6f-127">Overloading</span></span>  

 <span data-ttu-id="45e6f-128">El `Not` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="45e6f-128">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="45e6f-129">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="45e6f-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="45e6f-130">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="45e6f-130">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45e6f-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45e6f-131">Example</span></span>  

 <span data-ttu-id="45e6f-132">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de una `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="45e6f-132">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="45e6f-133">El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="45e6f-133">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="45e6f-134">En el ejemplo anterior se generan los resultados de `False` y `True` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="45e6f-134">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45e6f-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45e6f-135">Example</span></span>  

 <span data-ttu-id="45e6f-136">En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de los bits individuales de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="45e6f-136">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="45e6f-137">El bit en el patrón del resultado se establece en la inversa del bit correspondiente en el patrón de operando, incluido el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="45e6f-137">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="45e6f-138">En el ejemplo anterior se generan los resultados de – 11, – 9 y – 7, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="45e6f-138">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e6f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="45e6f-139">See also</span></span>

- [<span data-ttu-id="45e6f-140">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45e6f-140">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="45e6f-141">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45e6f-141">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="45e6f-142">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="45e6f-142">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="45e6f-143">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45e6f-143">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
