---
description: 'Más información acerca de: operador/(Visual Basic)'
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
ms.openlocfilehash: 717c8fdc6abae02de555040a3aadb92fed2bfbee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666009"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ad361-103">/ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad361-103">/ Operator (Visual Basic)</span></span>

<span data-ttu-id="ad361-104">Divide dos números y devuelve un resultado de coma flotante.</span><span class="sxs-lookup"><span data-stu-id="ad361-104">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad361-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad361-105">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ad361-106">Partes</span><span class="sxs-lookup"><span data-stu-id="ad361-106">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="ad361-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad361-107">Required.</span></span> <span data-ttu-id="ad361-108">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ad361-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ad361-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad361-109">Required.</span></span> <span data-ttu-id="ad361-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ad361-110">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="ad361-111">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="ad361-111">Supported Types</span></span>  

 <span data-ttu-id="ad361-112">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="ad361-112">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="ad361-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="ad361-113">Result</span></span>  

 <span data-ttu-id="ad361-114">El resultado es el cociente completo de `expression1` dividido entre `expression2` , incluido cualquier resto.</span><span class="sxs-lookup"><span data-stu-id="ad361-114">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="ad361-115">El [operador \ (Visual Basic)](integer-division-operator.md) devuelve el cociente entero, que quita el resto.</span><span class="sxs-lookup"><span data-stu-id="ad361-115">The [\ Operator (Visual Basic)](integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad361-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad361-116">Remarks</span></span>  

 <span data-ttu-id="ad361-117">El tipo de datos del resultado depende de los tipos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="ad361-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="ad361-118">En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="ad361-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="ad361-119">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="ad361-119">Operand data types</span></span>|<span data-ttu-id="ad361-120">Tipo de datos de resultados</span><span class="sxs-lookup"><span data-stu-id="ad361-120">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="ad361-121">Ambas expresiones son tipos de datos enteros ([SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="ad361-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="ad361-122">Una expresión es un tipo de datos [único](../data-types/single-data-type.md) y la otra no es [Double](../data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ad361-122">One expression is a [Single](../data-types/single-data-type.md) data type and the other is not a [Double](../data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="ad361-123">Una expresión es un tipo de datos [decimal](../data-types/decimal-data-type.md) y la otra no es [Single](../data-types/single-data-type.md) o [Double](../data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ad361-123">One expression is a [Decimal](../data-types/decimal-data-type.md) data type and the other is not a [Single](../data-types/single-data-type.md) or a [Double](../data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="ad361-124">Cualquier expresión es un tipo de datos [Double](../data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ad361-124">Either expression is a [Double](../data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="ad361-125">Antes de que se realice la división, cualquier expresión numérica entera se amplía a `Double` .</span><span class="sxs-lookup"><span data-stu-id="ad361-125">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="ad361-126">Si asigna el resultado a un tipo de datos entero, Visual Basic intenta convertir el resultado de `Double` a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="ad361-126">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="ad361-127">Esto puede producir una excepción si el resultado no cabe en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="ad361-127">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="ad361-128">En concreto, vea "se ha intentado la división por cero" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="ad361-128">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="ad361-129">Si `expression1` o `expression2` se evalúa como [Nothing](../nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="ad361-129">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="ad361-130">División intentada por cero</span><span class="sxs-lookup"><span data-stu-id="ad361-130">Attempted Division by Zero</span></span>  

 <span data-ttu-id="ad361-131">Si `expression2` se evalúa como cero, el `/` operador se comporta de forma diferente para los distintos tipos de datos de operando.</span><span class="sxs-lookup"><span data-stu-id="ad361-131">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="ad361-132">En la tabla siguiente se muestran los posibles comportamientos.</span><span class="sxs-lookup"><span data-stu-id="ad361-132">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="ad361-133">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="ad361-133">Operand data types</span></span>|<span data-ttu-id="ad361-134">Comportamiento si `expression2` es cero</span><span class="sxs-lookup"><span data-stu-id="ad361-134">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="ad361-135">Punto flotante ( `Single` o `Double` )</span><span class="sxs-lookup"><span data-stu-id="ad361-135">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="ad361-136">Devuelve Infinity ( <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity> ) o <xref:System.Double.NaN> (no un número) si `expression1` también es cero.</span><span class="sxs-lookup"><span data-stu-id="ad361-136">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="ad361-137">Produce <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="ad361-137">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="ad361-138">Entero (con signo o sin signo)</span><span class="sxs-lookup"><span data-stu-id="ad361-138">Integral (signed or unsigned)</span></span>|<span data-ttu-id="ad361-139">Se produce un intento de conversión de nuevo a un tipo entero <xref:System.OverflowException> , ya que los tipos enteros no pueden aceptar <xref:System.Double.PositiveInfinity> , <xref:System.Double.NegativeInfinity> o <xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="ad361-139">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="ad361-140">El `/` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ad361-140">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ad361-141">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="ad361-141">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ad361-142">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ad361-142">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad361-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad361-143">Example</span></span>  

 <span data-ttu-id="ad361-144">En este ejemplo se usa el `/` operador para realizar una división de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="ad361-144">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="ad361-145">El resultado es el cociente de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="ad361-145">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="ad361-146">Las expresiones del ejemplo anterior devuelven los valores 2,5 y 3,333333.</span><span class="sxs-lookup"><span data-stu-id="ad361-146">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="ad361-147">Tenga en cuenta que el resultado siempre es el punto flotante ( `Double` ), aunque ambos operandos son constantes de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="ad361-147">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad361-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad361-148">See also</span></span>

- [<span data-ttu-id="ad361-149">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad361-149">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="ad361-150">Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad361-150">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="ad361-151">Tipos de datos de los resultados de los operadores</span><span class="sxs-lookup"><span data-stu-id="ad361-151">Data Types of Operator Results</span></span>](data-types-of-operator-results.md)
- [<span data-ttu-id="ad361-152">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="ad361-152">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ad361-153">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad361-153">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="ad361-154">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="ad361-154">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="ad361-155">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad361-155">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
