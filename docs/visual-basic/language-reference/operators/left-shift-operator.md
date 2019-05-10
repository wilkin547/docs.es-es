---
title: << (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: e11dbc453934f1aac4a8092cdc6539ec11f0cc21
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663180"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="18690-102">\<\< Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18690-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="18690-103">Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="18690-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18690-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18690-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="18690-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="18690-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="18690-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="18690-106">Required.</span></span> <span data-ttu-id="18690-107">Valor numérico integral.</span><span class="sxs-lookup"><span data-stu-id="18690-107">Integral numeric value.</span></span> <span data-ttu-id="18690-108">El resultado de desplazar el patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="18690-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="18690-109">El tipo de datos es el mismo que el de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="18690-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="18690-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="18690-110">Required.</span></span> <span data-ttu-id="18690-111">Expresión numérica integral.</span><span class="sxs-lookup"><span data-stu-id="18690-111">Integral numeric expression.</span></span> <span data-ttu-id="18690-112">Patrón de bits que se van a desplazar.</span><span class="sxs-lookup"><span data-stu-id="18690-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="18690-113">El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="18690-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="18690-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="18690-114">Required.</span></span> <span data-ttu-id="18690-115">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="18690-115">Numeric expression.</span></span> <span data-ttu-id="18690-116">El número de bits para desplazar el patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="18690-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="18690-117">El tipo de datos debe ser `Integer` o ampliarse a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="18690-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18690-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18690-118">Remarks</span></span>  
 <span data-ttu-id="18690-119">Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelve a insertar en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="18690-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="18690-120">En un desplazamiento aritmético a la izquierda, se descartan los bits que se desplazan más allá del intervalo del tipo de datos del resultado y las posiciones de bits vacantes en la parte derecha se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="18690-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="18690-121">Para evitar que un cambio más bits que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño que se corresponde con el tipo de datos de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="18690-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="18690-122">La operación AND binario de estos valores se utiliza para la cantidad de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="18690-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="18690-123">Las máscaras de tamaño son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="18690-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="18690-124">Tipo de datos `pattern`</span><span class="sxs-lookup"><span data-stu-id="18690-124">Data type of `pattern`</span></span>|<span data-ttu-id="18690-125">Máscara de tamaño (decimal)</span><span class="sxs-lookup"><span data-stu-id="18690-125">Size mask (decimal)</span></span>|<span data-ttu-id="18690-126">Máscara de tamaño (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="18690-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="18690-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="18690-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="18690-128">7</span><span class="sxs-lookup"><span data-stu-id="18690-128">7</span></span>|<span data-ttu-id="18690-129">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="18690-129">&H00000007</span></span>|  
|<span data-ttu-id="18690-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="18690-130">`Short`, `UShort`</span></span>|<span data-ttu-id="18690-131">15</span><span class="sxs-lookup"><span data-stu-id="18690-131">15</span></span>|<span data-ttu-id="18690-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="18690-132">&H0000000F</span></span>|  
|<span data-ttu-id="18690-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="18690-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="18690-134">31</span><span class="sxs-lookup"><span data-stu-id="18690-134">31</span></span>|<span data-ttu-id="18690-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="18690-135">&H0000001F</span></span>|  
|<span data-ttu-id="18690-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="18690-136">`Long`, `ULong`</span></span>|<span data-ttu-id="18690-137">63</span><span class="sxs-lookup"><span data-stu-id="18690-137">63</span></span>|<span data-ttu-id="18690-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="18690-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="18690-139">Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="18690-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="18690-140">Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuado.</span><span class="sxs-lookup"><span data-stu-id="18690-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="18690-141">Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="18690-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18690-142">El `<<` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="18690-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="18690-143">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que comprende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="18690-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="18690-144">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="18690-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18690-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18690-145">Example</span></span>  
 <span data-ttu-id="18690-146">En el ejemplo siguiente se usa el `<<` operador para realizar operaciones aritméticas izquierda en los valores enteros.</span><span class="sxs-lookup"><span data-stu-id="18690-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="18690-147">El resultado siempre tiene los mismos datos de tipo que el de la expresión que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="18690-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="18690-148">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="18690-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="18690-149">`result1` es 192 (0000 0000 0000 de 1100).</span><span class="sxs-lookup"><span data-stu-id="18690-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="18690-150">`result2` es 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="18690-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="18690-151">`result3` es de -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="18690-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="18690-152">`result4` es de tipo 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="18690-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="18690-153">`result5` es 0 (se desplaza 15 posiciones a la izquierda).</span><span class="sxs-lookup"><span data-stu-id="18690-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="18690-154">La cantidad de desplazamiento para `result4` se calcula como 17 y 15, que es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="18690-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18690-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="18690-155">See also</span></span>

- [<span data-ttu-id="18690-156">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="18690-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="18690-157">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="18690-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="18690-158">Operador <<=</span><span class="sxs-lookup"><span data-stu-id="18690-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="18690-159">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18690-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="18690-160">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="18690-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="18690-161">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18690-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
