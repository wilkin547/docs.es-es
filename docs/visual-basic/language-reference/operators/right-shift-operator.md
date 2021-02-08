---
description: 'Más información acerca de: operador de  >> (Visual Basic)'
title: '>> Operator'
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
ms.openlocfilehash: 125b93f129734d196bd1f7f9c4fde86ab5d66319
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795305"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f3873-103">Operador >> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3873-103">>> Operator (Visual Basic)</span></span>

<span data-ttu-id="f3873-104">Realiza un desplazamiento aritmético a la derecha en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="f3873-104">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3873-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3873-105">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="f3873-106">Partes</span><span class="sxs-lookup"><span data-stu-id="f3873-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="f3873-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f3873-107">Required.</span></span> <span data-ttu-id="f3873-108">Valor numérico entero.</span><span class="sxs-lookup"><span data-stu-id="f3873-108">Integral numeric value.</span></span> <span data-ttu-id="f3873-109">Resultado de desplazar el modelo de bits.</span><span class="sxs-lookup"><span data-stu-id="f3873-109">The result of shifting the bit pattern.</span></span> <span data-ttu-id="f3873-110">El tipo de datos es el mismo que el de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="f3873-110">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="f3873-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f3873-111">Required.</span></span> <span data-ttu-id="f3873-112">Expresión numérica integral.</span><span class="sxs-lookup"><span data-stu-id="f3873-112">Integral numeric expression.</span></span> <span data-ttu-id="f3873-113">Modelo de bits que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="f3873-113">The bit pattern to be shifted.</span></span> <span data-ttu-id="f3873-114">El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="f3873-114">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="f3873-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f3873-115">Required.</span></span> <span data-ttu-id="f3873-116">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f3873-116">Numeric expression.</span></span> <span data-ttu-id="f3873-117">Número de bits que se va a desplazar el modelo de bits.</span><span class="sxs-lookup"><span data-stu-id="f3873-117">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="f3873-118">El tipo de datos debe ser `Integer` o ampliarse a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f3873-118">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3873-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3873-119">Remarks</span></span>  

 <span data-ttu-id="f3873-120">Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="f3873-120">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="f3873-121">En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición del bit más a la derecha y el bit de la izquierda (signo) se propaga a las posiciones de bits que quedan a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="f3873-121">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="f3873-122">Esto significa que si `pattern` tiene un valor negativo, las posiciones vacías se establecen en uno; de lo contrario, se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="f3873-122">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="f3873-123">Tenga en cuenta que los tipos de datos `Byte` ,, `UShort` `UInteger` y `ULong` están sin signo, por lo que no hay ningún bit de signo que propagar.</span><span class="sxs-lookup"><span data-stu-id="f3873-123">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="f3873-124">Si `pattern` es de cualquier tipo sin signo, las posiciones vacías siempre se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="f3873-124">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="f3873-125">Para evitar el desplazamiento por más bits del que puede contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern` .</span><span class="sxs-lookup"><span data-stu-id="f3873-125">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="f3873-126">El binario y estos valores se usan para la cantidad de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="f3873-126">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="f3873-127">Las máscaras de tamaño son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3873-127">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="f3873-128">Tipo de datos de `pattern`</span><span class="sxs-lookup"><span data-stu-id="f3873-128">Data type of `pattern`</span></span>|<span data-ttu-id="f3873-129">Máscara de tamaño (decimal)</span><span class="sxs-lookup"><span data-stu-id="f3873-129">Size mask (decimal)</span></span>|<span data-ttu-id="f3873-130">Máscara de tamaño (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="f3873-130">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="f3873-131">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="f3873-131">`SByte`, `Byte`</span></span>|<span data-ttu-id="f3873-132">7</span><span class="sxs-lookup"><span data-stu-id="f3873-132">7</span></span>|<span data-ttu-id="f3873-133">&H00000007</span><span class="sxs-lookup"><span data-stu-id="f3873-133">&H00000007</span></span>|  
|<span data-ttu-id="f3873-134">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="f3873-134">`Short`, `UShort`</span></span>|<span data-ttu-id="f3873-135">15</span><span class="sxs-lookup"><span data-stu-id="f3873-135">15</span></span>|<span data-ttu-id="f3873-136">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="f3873-136">&H0000000F</span></span>|  
|<span data-ttu-id="f3873-137">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="f3873-137">`Integer`, `UInteger`</span></span>|<span data-ttu-id="f3873-138">31</span><span class="sxs-lookup"><span data-stu-id="f3873-138">31</span></span>|<span data-ttu-id="f3873-139">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="f3873-139">&H0000001F</span></span>|  
|<span data-ttu-id="f3873-140">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="f3873-140">`Long`, `ULong`</span></span>|<span data-ttu-id="f3873-141">63</span><span class="sxs-lookup"><span data-stu-id="f3873-141">63</span></span>|<span data-ttu-id="f3873-142">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="f3873-142">&H0000003F</span></span>|  
  
 <span data-ttu-id="f3873-143">Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern` .</span><span class="sxs-lookup"><span data-stu-id="f3873-143">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="f3873-144">Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.</span><span class="sxs-lookup"><span data-stu-id="f3873-144">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="f3873-145">Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="f3873-145">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f3873-146">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f3873-146">Overloading</span></span>  

 <span data-ttu-id="f3873-147">El `>>` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f3873-147">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f3873-148">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f3873-148">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f3873-149">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f3873-149">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3873-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3873-150">Example</span></span>  

 <span data-ttu-id="f3873-151">En el ejemplo siguiente se usa el `>>` operador para realizar los desplazamientos aritméticos a la derecha en los valores enteros.</span><span class="sxs-lookup"><span data-stu-id="f3873-151">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="f3873-152">El resultado siempre tiene el mismo tipo de datos que la expresión que se está desplazando.</span><span class="sxs-lookup"><span data-stu-id="f3873-152">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="f3873-153">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3873-153">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="f3873-154">`result1` es 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="f3873-154">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="f3873-155">`result2` es 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="f3873-155">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="f3873-156">`result3` es 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="f3873-156">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="f3873-157">`result4` es 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="f3873-157">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="f3873-158">`result5` es 0 (se desplazan 15 posiciones a la derecha).</span><span class="sxs-lookup"><span data-stu-id="f3873-158">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="f3873-159">La cantidad de desplazamiento de `result4` se calcula como 18 y 15, que es igual a 2.</span><span class="sxs-lookup"><span data-stu-id="f3873-159">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="f3873-160">En el ejemplo siguiente se muestran los cambios aritméticos en un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="f3873-160">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="f3873-161">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3873-161">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="f3873-162">`negresult1` es-512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="f3873-162">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="f3873-163">`negresult2` es-1 (el bit de signo se propaga).</span><span class="sxs-lookup"><span data-stu-id="f3873-163">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3873-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3873-164">See also</span></span>

- [<span data-ttu-id="f3873-165">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="f3873-165">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="f3873-166">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="f3873-166">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="f3873-167">>>= (operador)</span><span class="sxs-lookup"><span data-stu-id="f3873-167">>>= Operator</span></span>](right-shift-assignment-operator.md)
- [<span data-ttu-id="f3873-168">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3873-168">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="f3873-169">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f3873-169">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="f3873-170">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3873-170">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
