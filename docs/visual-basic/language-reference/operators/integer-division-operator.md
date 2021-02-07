---
description: 'Más información acerca de: operador (Visual Basic)'
title: '\ (Operador)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: e15a630d37e423b7a7d0040e495f2543889f37b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665788"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="1ab35-103">\ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ab35-103">\ Operator (Visual Basic)</span></span>

<span data-ttu-id="1ab35-104">Divide dos números y devuelve un resultado de número entero.</span><span class="sxs-lookup"><span data-stu-id="1ab35-104">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab35-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ab35-105">Syntax</span></span>  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="1ab35-106">Partes</span><span class="sxs-lookup"><span data-stu-id="1ab35-106">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="1ab35-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ab35-107">Required.</span></span> <span data-ttu-id="1ab35-108">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1ab35-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="1ab35-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ab35-109">Required.</span></span> <span data-ttu-id="1ab35-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1ab35-110">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="1ab35-111">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="1ab35-111">Supported Types</span></span>  

 <span data-ttu-id="1ab35-112">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="1ab35-112">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="1ab35-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="1ab35-113">Result</span></span>  

 <span data-ttu-id="1ab35-114">El resultado es el cociente entero de `expression1` divide by `expression2` , que descarta cualquier resto y solo conserva la parte entera.</span><span class="sxs-lookup"><span data-stu-id="1ab35-114">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="1ab35-115">Esto se conoce como *truncamiento*.</span><span class="sxs-lookup"><span data-stu-id="1ab35-115">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="1ab35-116">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="1ab35-116">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="1ab35-117">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="1ab35-117">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="1ab35-118">El [operador/(Visual Basic)](floating-point-division-operator.md) devuelve el cociente completo, que conserva el resto de la parte fraccionaria.</span><span class="sxs-lookup"><span data-stu-id="1ab35-118">The [/ Operator (Visual Basic)](floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab35-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ab35-119">Remarks</span></span>  

 <span data-ttu-id="1ab35-120">Antes de realizar la división, Visual Basic intenta convertir cualquier expresión numérica de punto flotante en `Long` .</span><span class="sxs-lookup"><span data-stu-id="1ab35-120">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="1ab35-121">Si `Option Strict` es `On` , se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="1ab35-121">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="1ab35-122">Si `Option Strict` es `Off` , <xref:System.OverflowException> es posible si el valor está fuera del intervalo del tipo de [datos Long](../data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="1ab35-122">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../data-types/long-data-type.md).</span></span> <span data-ttu-id="1ab35-123">La conversión a `Long` también está sujeta a *redondeo bancario*.</span><span class="sxs-lookup"><span data-stu-id="1ab35-123">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="1ab35-124">Para obtener más información, vea "partes fraccionarias" en [funciones de conversión de tipos](../functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1ab35-124">For more information, see "Fractional Parts" in [Type Conversion Functions](../functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="1ab35-125">Si `expression1` o `expression2` se evalúa como [Nothing](../nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="1ab35-125">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="1ab35-126">División intentada por cero</span><span class="sxs-lookup"><span data-stu-id="1ab35-126">Attempted Division by Zero</span></span>  

 <span data-ttu-id="1ab35-127">Si `expression2` se evalúa como cero, el `\` operador produce una <xref:System.DivideByZeroException> excepción.</span><span class="sxs-lookup"><span data-stu-id="1ab35-127">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="1ab35-128">Esto es así para todos los tipos de datos numéricos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="1ab35-128">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ab35-129">El `\` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1ab35-129">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1ab35-130">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="1ab35-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1ab35-131">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1ab35-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ab35-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ab35-132">Example</span></span>  

 <span data-ttu-id="1ab35-133">En el ejemplo siguiente se usa el `\` operador para realizar la división de enteros.</span><span class="sxs-lookup"><span data-stu-id="1ab35-133">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="1ab35-134">El resultado es un entero que representa el cociente entero de los dos operandos, con el resto descartado.</span><span class="sxs-lookup"><span data-stu-id="1ab35-134">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="1ab35-135">Las expresiones del ejemplo anterior devuelven los valores 2, 3, 33 y-22, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1ab35-135">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab35-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ab35-136">See also</span></span>

- [<span data-ttu-id="1ab35-137">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="1ab35-137">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="1ab35-138">Operador/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ab35-138">/ Operator (Visual Basic)</span></span>](floating-point-division-operator.md)
- [<span data-ttu-id="1ab35-139">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1ab35-139">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="1ab35-140">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1ab35-140">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="1ab35-141">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ab35-141">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="1ab35-142">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1ab35-142">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="1ab35-143">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ab35-143">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
