---
description: 'Más información acerca de: operador de  << (Visual Basic)'
title: Operador <<
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 079af61e5c4ce3834db0877feace724c74c8169c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665632"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e2b63-103">\<\< Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2b63-103">\<\< Operator (Visual Basic)</span></span>

<span data-ttu-id="e2b63-104">Realiza un desplazamiento aritmético a la izquierda en un patrón de bits.</span><span class="sxs-lookup"><span data-stu-id="e2b63-104">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2b63-105">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="e2b63-106">Partes</span><span class="sxs-lookup"><span data-stu-id="e2b63-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="e2b63-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e2b63-107">Required.</span></span> <span data-ttu-id="e2b63-108">Valor numérico entero.</span><span class="sxs-lookup"><span data-stu-id="e2b63-108">Integral numeric value.</span></span> <span data-ttu-id="e2b63-109">Resultado de desplazar el modelo de bits.</span><span class="sxs-lookup"><span data-stu-id="e2b63-109">The result of shifting the bit pattern.</span></span> <span data-ttu-id="e2b63-110">El tipo de datos es el mismo que el de `pattern`.</span><span class="sxs-lookup"><span data-stu-id="e2b63-110">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="e2b63-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-111">Required.</span></span> <span data-ttu-id="e2b63-112">Expresión numérica integral.</span><span class="sxs-lookup"><span data-stu-id="e2b63-112">Integral numeric expression.</span></span> <span data-ttu-id="e2b63-113">Modelo de bits que se va a desplazar.</span><span class="sxs-lookup"><span data-stu-id="e2b63-113">The bit pattern to be shifted.</span></span> <span data-ttu-id="e2b63-114">El tipo de datos debe ser un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="e2b63-114">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="e2b63-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-115">Required.</span></span> <span data-ttu-id="e2b63-116">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e2b63-116">Numeric expression.</span></span> <span data-ttu-id="e2b63-117">Número de bits que se va a desplazar el modelo de bits.</span><span class="sxs-lookup"><span data-stu-id="e2b63-117">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="e2b63-118">El tipo de datos debe ser `Integer` o ampliarse a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e2b63-118">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2b63-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2b63-119">Remarks</span></span>  

 <span data-ttu-id="e2b63-120">Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="e2b63-120">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="e2b63-121">En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits que quedan a la derecha se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="e2b63-121">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="e2b63-122">Para evitar que un desplazamiento entre más bits que el resultado pueda contener, Visual Basic enmascara el valor de `amount` con una máscara de tamaño que corresponde al tipo de datos de `pattern` .</span><span class="sxs-lookup"><span data-stu-id="e2b63-122">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="e2b63-123">El binario y estos valores se usan para la cantidad de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e2b63-123">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="e2b63-124">Las máscaras de tamaño son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2b63-124">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="e2b63-125">Tipo de datos de `pattern`</span><span class="sxs-lookup"><span data-stu-id="e2b63-125">Data type of `pattern`</span></span>|<span data-ttu-id="e2b63-126">Máscara de tamaño (decimal)</span><span class="sxs-lookup"><span data-stu-id="e2b63-126">Size mask (decimal)</span></span>|<span data-ttu-id="e2b63-127">Máscara de tamaño (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="e2b63-127">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="e2b63-128">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="e2b63-128">`SByte`, `Byte`</span></span>|<span data-ttu-id="e2b63-129">7</span><span class="sxs-lookup"><span data-stu-id="e2b63-129">7</span></span>|<span data-ttu-id="e2b63-130">&H00000007</span><span class="sxs-lookup"><span data-stu-id="e2b63-130">&H00000007</span></span>|  
|<span data-ttu-id="e2b63-131">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="e2b63-131">`Short`, `UShort`</span></span>|<span data-ttu-id="e2b63-132">15</span><span class="sxs-lookup"><span data-stu-id="e2b63-132">15</span></span>|<span data-ttu-id="e2b63-133">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="e2b63-133">&H0000000F</span></span>|  
|<span data-ttu-id="e2b63-134">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="e2b63-134">`Integer`, `UInteger`</span></span>|<span data-ttu-id="e2b63-135">31</span><span class="sxs-lookup"><span data-stu-id="e2b63-135">31</span></span>|<span data-ttu-id="e2b63-136">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="e2b63-136">&H0000001F</span></span>|  
|<span data-ttu-id="e2b63-137">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="e2b63-137">`Long`, `ULong`</span></span>|<span data-ttu-id="e2b63-138">63</span><span class="sxs-lookup"><span data-stu-id="e2b63-138">63</span></span>|<span data-ttu-id="e2b63-139">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="e2b63-139">&H0000003F</span></span>|  
  
 <span data-ttu-id="e2b63-140">Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern` .</span><span class="sxs-lookup"><span data-stu-id="e2b63-140">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="e2b63-141">Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.</span><span class="sxs-lookup"><span data-stu-id="e2b63-141">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="e2b63-142">Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="e2b63-142">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2b63-143">El `<<` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e2b63-143">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e2b63-144">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e2b63-144">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="e2b63-145">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e2b63-145">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2b63-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2b63-146">Example</span></span>  

 <span data-ttu-id="e2b63-147">En el ejemplo siguiente se usa el `<<` operador para realizar los desplazamientos aritméticos a la izquierda en valores enteros.</span><span class="sxs-lookup"><span data-stu-id="e2b63-147">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="e2b63-148">El resultado siempre tiene el mismo tipo de datos que la expresión que se está desplazando.</span><span class="sxs-lookup"><span data-stu-id="e2b63-148">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="e2b63-149">Los resultados del ejemplo anterior son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2b63-149">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="e2b63-150">`result1` es 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="e2b63-150">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="e2b63-151">`result2` es 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="e2b63-151">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="e2b63-152">`result3` es-32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="e2b63-152">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="e2b63-153">`result4` es 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="e2b63-153">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="e2b63-154">`result5` es 0 (se desplazan 15 posiciones hacia la izquierda).</span><span class="sxs-lookup"><span data-stu-id="e2b63-154">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="e2b63-155">La cantidad de desplazamiento de `result4` se calcula como 17 y 15, que es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="e2b63-155">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b63-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2b63-156">See also</span></span>

- [<span data-ttu-id="e2b63-157">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="e2b63-157">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="e2b63-158">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="e2b63-158">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="e2b63-159"><<= (operador)</span><span class="sxs-lookup"><span data-stu-id="e2b63-159"><<= Operator</span></span>](left-shift-assignment-operator.md)
- [<span data-ttu-id="e2b63-160">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2b63-160">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e2b63-161">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e2b63-161">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e2b63-162">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2b63-162">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
