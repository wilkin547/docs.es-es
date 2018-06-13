---
title: '&gt;&gt; (Operador) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605412"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="16241-102">&gt;&gt; (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16241-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="16241-103">Realiza un desplazamiento aritmético a la derecha en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="16241-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16241-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16241-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="16241-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="16241-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="16241-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="16241-106">Required.</span></span> <span data-ttu-id="16241-107">Valor numérico integral.</span><span class="sxs-lookup"><span data-stu-id="16241-107">Integral numeric value.</span></span> <span data-ttu-id="16241-108">El resultado de desplazar el patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="16241-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="16241-109">El tipo de datos es el mismo que el de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="16241-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="16241-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="16241-110">Required.</span></span> <span data-ttu-id="16241-111">Expresión numérica integral.</span><span class="sxs-lookup"><span data-stu-id="16241-111">Integral numeric expression.</span></span> <span data-ttu-id="16241-112">El patrón de bits que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="16241-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="16241-113">El tipo de datos debe ser un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="16241-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="16241-114">Requerido.</span><span class="sxs-lookup"><span data-stu-id="16241-114">Required.</span></span> <span data-ttu-id="16241-115">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="16241-115">Numeric expression.</span></span> <span data-ttu-id="16241-116">El número de bits para desplazar el patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="16241-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="16241-117">El tipo de datos debe ser `Integer` o amplían `Integer`.</span><span class="sxs-lookup"><span data-stu-id="16241-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16241-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16241-118">Remarks</span></span>  
 <span data-ttu-id="16241-119">Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="16241-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="16241-120">En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit de la derecha y el bit de la izquierda (inicio de sesión) se propaga a las posiciones de bits vacantes a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="16241-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="16241-121">Esto significa que si `pattern` tiene un valor negativo, las posiciones vacantes se establecen en uno; en caso contrario se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="16241-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="16241-122">Tenga en cuenta que los tipos de datos `Byte`, `UShort`, `UInteger`, y `ULong` están firmados, así que no hay ningún bit de signo para propagar.</span><span class="sxs-lookup"><span data-stu-id="16241-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="16241-123">Si `pattern` es de cualquier tipo sin signo, las posiciones vacías siempre se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="16241-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="16241-124">Para evitar que se desplace más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="16241-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="16241-125">El operador AND binario de estos valores se utiliza para la cantidad de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="16241-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="16241-126">Las máscaras de tamaño son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="16241-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="16241-127">Tipo de datos de `pattern`</span><span class="sxs-lookup"><span data-stu-id="16241-127">Data type of `pattern`</span></span>|<span data-ttu-id="16241-128">Máscara de tamaño (decimal)</span><span class="sxs-lookup"><span data-stu-id="16241-128">Size mask (decimal)</span></span>|<span data-ttu-id="16241-129">Máscara de tamaño (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="16241-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="16241-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="16241-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="16241-131">7</span><span class="sxs-lookup"><span data-stu-id="16241-131">7</span></span>|<span data-ttu-id="16241-132">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="16241-132">&H00000007</span></span>|  
|<span data-ttu-id="16241-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="16241-133">`Short`, `UShort`</span></span>|<span data-ttu-id="16241-134">15</span><span class="sxs-lookup"><span data-stu-id="16241-134">15</span></span>|<span data-ttu-id="16241-135">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="16241-135">&H0000000F</span></span>|  
|<span data-ttu-id="16241-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="16241-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="16241-137">31</span><span class="sxs-lookup"><span data-stu-id="16241-137">31</span></span>|<span data-ttu-id="16241-138">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="16241-138">&H0000001F</span></span>|  
|<span data-ttu-id="16241-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="16241-139">`Long`, `ULong`</span></span>|<span data-ttu-id="16241-140">63</span><span class="sxs-lookup"><span data-stu-id="16241-140">63</span></span>|<span data-ttu-id="16241-141">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="16241-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="16241-142">Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="16241-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="16241-143">Si `amount` es negativo, se toma como un valor sin signo y enmascara con la máscara de tamaño adecuado.</span><span class="sxs-lookup"><span data-stu-id="16241-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="16241-144">Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="16241-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="16241-145">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="16241-145">Overloading</span></span>  
 <span data-ttu-id="16241-146">El `>>` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="16241-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="16241-147">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="16241-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="16241-148">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="16241-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16241-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16241-149">Example</span></span>  
 <span data-ttu-id="16241-150">En el ejemplo siguiente se usa el `>>` operador que se va a realizar desplazamientos aritméticos a la derecha en valores enteros.</span><span class="sxs-lookup"><span data-stu-id="16241-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="16241-151">El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="16241-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="16241-152">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="16241-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="16241-153">`result1` es 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="16241-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="16241-154">`result2` es de 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="16241-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="16241-155">`result3` es 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="16241-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="16241-156">`result4` es 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="16241-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="16241-157">`result5` es 0 (se desplaza 15 posiciones a la derecha).</span><span class="sxs-lookup"><span data-stu-id="16241-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="16241-158">La cantidad de desplazamiento para `result4` se calcula como 18 AND 15, lo que es igual a 2.</span><span class="sxs-lookup"><span data-stu-id="16241-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="16241-159">El ejemplo siguiente muestra los desplazamientos aritméticos en un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="16241-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="16241-160">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="16241-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="16241-161">`negresult1` es -512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="16241-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="16241-162">`negresult2` es -1 (se propaga el bit de signo).</span><span class="sxs-lookup"><span data-stu-id="16241-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16241-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="16241-163">See Also</span></span>  
 [<span data-ttu-id="16241-164">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="16241-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="16241-165">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="16241-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="16241-166">Operador >>=</span><span class="sxs-lookup"><span data-stu-id="16241-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [<span data-ttu-id="16241-167">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16241-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="16241-168">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="16241-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="16241-169">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16241-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
