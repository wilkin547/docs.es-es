---
title: / (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: e9400b50a84522f87a9a2ea4cd05b479d7a4538e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371173"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e83a4-102">/ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e83a4-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="e83a4-103">Divide dos números y devuelve un resultado de coma flotante.</span><span class="sxs-lookup"><span data-stu-id="e83a4-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e83a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e83a4-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e83a4-105">Partes</span><span class="sxs-lookup"><span data-stu-id="e83a4-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="e83a4-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e83a4-106">Required.</span></span> <span data-ttu-id="e83a4-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e83a4-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e83a4-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e83a4-108">Required.</span></span> <span data-ttu-id="e83a4-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e83a4-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="e83a4-110">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="e83a4-110">Supported Types</span></span>  
 <span data-ttu-id="e83a4-111">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="e83a4-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="e83a4-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="e83a4-112">Result</span></span>  
 <span data-ttu-id="e83a4-113">El resultado es el cociente completo de `expression1` dividido entre `expression2` , incluido cualquier resto.</span><span class="sxs-lookup"><span data-stu-id="e83a4-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="e83a4-114">El [operador \ (Visual Basic)](integer-division-operator.md) devuelve el cociente entero, que quita el resto.</span><span class="sxs-lookup"><span data-stu-id="e83a4-114">The [\ Operator (Visual Basic)](integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e83a4-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e83a4-115">Remarks</span></span>  
 <span data-ttu-id="e83a4-116">El tipo de datos del resultado depende de los tipos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="e83a4-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="e83a4-117">En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="e83a4-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="e83a4-118">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="e83a4-118">Operand data types</span></span>|<span data-ttu-id="e83a4-119">Tipo de datos de resultados</span><span class="sxs-lookup"><span data-stu-id="e83a4-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="e83a4-120">Ambas expresiones son tipos de datos enteros ([SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="e83a4-120">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="e83a4-121">Una expresión es un tipo de datos [único](../data-types/single-data-type.md) y la otra no es [Double](../data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="e83a4-121">One expression is a [Single](../data-types/single-data-type.md) data type and the other is not a [Double](../data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="e83a4-122">Una expresión es un tipo de datos [decimal](../data-types/decimal-data-type.md) y la otra no es [Single](../data-types/single-data-type.md) o [Double](../data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="e83a4-122">One expression is a [Decimal](../data-types/decimal-data-type.md) data type and the other is not a [Single](../data-types/single-data-type.md) or a [Double](../data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="e83a4-123">Cualquier expresión es un tipo de datos [Double](../data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="e83a4-123">Either expression is a [Double](../data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="e83a4-124">Antes de que se realice la división, cualquier expresión numérica entera se amplía a `Double` .</span><span class="sxs-lookup"><span data-stu-id="e83a4-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="e83a4-125">Si asigna el resultado a un tipo de datos entero, Visual Basic intenta convertir el resultado de `Double` a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="e83a4-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="e83a4-126">Esto puede producir una excepción si el resultado no cabe en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="e83a4-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="e83a4-127">En concreto, vea "se ha intentado la división por cero" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="e83a4-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="e83a4-128">Si `expression1` o `expression2` se evalúa como [Nothing](../nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="e83a4-128">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="e83a4-129">División intentada por cero</span><span class="sxs-lookup"><span data-stu-id="e83a4-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="e83a4-130">Si `expression2` se evalúa como cero, el `/` operador se comporta de forma diferente para los distintos tipos de datos de operando.</span><span class="sxs-lookup"><span data-stu-id="e83a4-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="e83a4-131">En la tabla siguiente se muestran los posibles comportamientos.</span><span class="sxs-lookup"><span data-stu-id="e83a4-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="e83a4-132">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="e83a4-132">Operand data types</span></span>|<span data-ttu-id="e83a4-133">Comportamiento si `expression2` es cero</span><span class="sxs-lookup"><span data-stu-id="e83a4-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="e83a4-134">Punto flotante ( `Single` o `Double` )</span><span class="sxs-lookup"><span data-stu-id="e83a4-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="e83a4-135">Devuelve Infinity ( <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity> ) o <xref:System.Double.NaN> (no un número) si `expression1` también es cero.</span><span class="sxs-lookup"><span data-stu-id="e83a4-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="e83a4-136">Produce<xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="e83a4-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="e83a4-137">Entero (con signo o sin signo)</span><span class="sxs-lookup"><span data-stu-id="e83a4-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="e83a4-138">Se produce un intento de conversión de nuevo a un tipo entero <xref:System.OverflowException> , ya que los tipos enteros no pueden aceptar <xref:System.Double.PositiveInfinity> , <xref:System.Double.NegativeInfinity> o<xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="e83a4-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="e83a4-139">El `/` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e83a4-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e83a4-140">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e83a4-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e83a4-141">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e83a4-141">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e83a4-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e83a4-142">Example</span></span>  
 <span data-ttu-id="e83a4-143">En este ejemplo se usa el `/` operador para realizar una división de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e83a4-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="e83a4-144">El resultado es el cociente de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="e83a4-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="e83a4-145">Las expresiones del ejemplo anterior devuelven los valores 2,5 y 3,333333.</span><span class="sxs-lookup"><span data-stu-id="e83a4-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="e83a4-146">Tenga en cuenta que el resultado siempre es el punto flotante ( `Double` ), aunque ambos operandos son constantes de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="e83a4-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e83a4-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e83a4-147">See also</span></span>

- [<span data-ttu-id="e83a4-148">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e83a4-148">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="e83a4-149">Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e83a4-149">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="e83a4-150">Tipos de datos de los resultados de los operadores</span><span class="sxs-lookup"><span data-stu-id="e83a4-150">Data Types of Operator Results</span></span>](data-types-of-operator-results.md)
- [<span data-ttu-id="e83a4-151">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="e83a4-151">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e83a4-152">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e83a4-152">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e83a4-153">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e83a4-153">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e83a4-154">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e83a4-154">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
