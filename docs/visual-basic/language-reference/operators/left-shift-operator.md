---
title: '&lt;&lt;(Operador) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56cfb227f7e5c68de802c1f2cfb842a770f65ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="fb253-102">&lt;&lt;(Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb253-102">&lt;&lt; Operator (Visual Basic)</span></span>
<span data-ttu-id="fb253-103">Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="fb253-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb253-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb253-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="fb253-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="fb253-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="fb253-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fb253-106">Required.</span></span> <span data-ttu-id="fb253-107">Valor numérico integral.</span><span class="sxs-lookup"><span data-stu-id="fb253-107">Integral numeric value.</span></span> <span data-ttu-id="fb253-108">El resultado de desplazar el patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="fb253-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="fb253-109">El tipo de datos es el mismo que el de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="fb253-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="fb253-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fb253-110">Required.</span></span> <span data-ttu-id="fb253-111">Expresión numérica integral.</span><span class="sxs-lookup"><span data-stu-id="fb253-111">Integral numeric expression.</span></span> <span data-ttu-id="fb253-112">El patrón de bits que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="fb253-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="fb253-113">El tipo de datos debe ser un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="fb253-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="fb253-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fb253-114">Required.</span></span> <span data-ttu-id="fb253-115">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="fb253-115">Numeric expression.</span></span> <span data-ttu-id="fb253-116">El número de bits para desplazar el patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="fb253-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="fb253-117">El tipo de datos debe ser `Integer` o amplían `Integer`.</span><span class="sxs-lookup"><span data-stu-id="fb253-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb253-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb253-118">Remarks</span></span>  
 <span data-ttu-id="fb253-119">Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="fb253-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="fb253-120">En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits vacantes a la derecha se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="fb253-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="fb253-121">Para evitar que un cambio más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño que se corresponde con el tipo de datos de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="fb253-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="fb253-122">El operador AND binario de estos valores se utiliza para la cantidad de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="fb253-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="fb253-123">Las máscaras de tamaño son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb253-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="fb253-124">Tipo de datos de`pattern`</span><span class="sxs-lookup"><span data-stu-id="fb253-124">Data type of `pattern`</span></span>|<span data-ttu-id="fb253-125">Máscara de tamaño (decimal)</span><span class="sxs-lookup"><span data-stu-id="fb253-125">Size mask (decimal)</span></span>|<span data-ttu-id="fb253-126">Máscara de tamaño (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="fb253-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="fb253-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="fb253-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="fb253-128">7</span><span class="sxs-lookup"><span data-stu-id="fb253-128">7</span></span>|<span data-ttu-id="fb253-129">& H00000007</span><span class="sxs-lookup"><span data-stu-id="fb253-129">&H00000007</span></span>|  
|<span data-ttu-id="fb253-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="fb253-130">`Short`, `UShort`</span></span>|<span data-ttu-id="fb253-131">15</span><span class="sxs-lookup"><span data-stu-id="fb253-131">15</span></span>|<span data-ttu-id="fb253-132">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="fb253-132">&H0000000F</span></span>|  
|<span data-ttu-id="fb253-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="fb253-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="fb253-134">31</span><span class="sxs-lookup"><span data-stu-id="fb253-134">31</span></span>|<span data-ttu-id="fb253-135">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="fb253-135">&H0000001F</span></span>|  
|<span data-ttu-id="fb253-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="fb253-136">`Long`, `ULong`</span></span>|<span data-ttu-id="fb253-137">63</span><span class="sxs-lookup"><span data-stu-id="fb253-137">63</span></span>|<span data-ttu-id="fb253-138">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="fb253-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="fb253-139">Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="fb253-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="fb253-140">Si `amount` es negativo, se toma como un valor sin signo y enmascara con la máscara de tamaño adecuado.</span><span class="sxs-lookup"><span data-stu-id="fb253-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="fb253-141">Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="fb253-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb253-142">El `<<` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fb253-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fb253-143">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="fb253-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="fb253-144">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fb253-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb253-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb253-145">Example</span></span>  
 <span data-ttu-id="fb253-146">En el ejemplo siguiente se usa el `<<` operador para realizar operaciones aritméticas izquierda en valores enteros.</span><span class="sxs-lookup"><span data-stu-id="fb253-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="fb253-147">El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="fb253-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 <span data-ttu-id="fb253-148">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb253-148">The results of the previous example are as follows:</span></span>  
  
-   <span data-ttu-id="fb253-149">`result1`es 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="fb253-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
-   <span data-ttu-id="fb253-150">`result2`es 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="fb253-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
-   <span data-ttu-id="fb253-151">`result3`es de -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="fb253-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
-   <span data-ttu-id="fb253-152">`result4`es de tipo 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="fb253-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
-   <span data-ttu-id="fb253-153">`result5`es 0 (se desplaza 15 posiciones a la izquierda).</span><span class="sxs-lookup"><span data-stu-id="fb253-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="fb253-154">La cantidad de desplazamiento para `result4` se calcula como 17 AND 15, lo que es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="fb253-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb253-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb253-155">See Also</span></span>  
 [<span data-ttu-id="fb253-156">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="fb253-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="fb253-157">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="fb253-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="fb253-158">Operador <<=</span><span class="sxs-lookup"><span data-stu-id="fb253-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [<span data-ttu-id="fb253-159">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb253-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="fb253-160">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="fb253-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="fb253-161">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb253-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
