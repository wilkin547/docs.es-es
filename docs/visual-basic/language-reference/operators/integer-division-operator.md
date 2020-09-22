---
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
ms.openlocfilehash: cf2dc66532925d56cea6fd141f44a245bc2dd8dd
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873399"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b064a-102">\ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b064a-102">\ Operator (Visual Basic)</span></span>

<span data-ttu-id="b064a-103">Divide dos números y devuelve un resultado de número entero.</span><span class="sxs-lookup"><span data-stu-id="b064a-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b064a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b064a-104">Syntax</span></span>  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="b064a-105">Partes</span><span class="sxs-lookup"><span data-stu-id="b064a-105">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="b064a-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b064a-106">Required.</span></span> <span data-ttu-id="b064a-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="b064a-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="b064a-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b064a-108">Required.</span></span> <span data-ttu-id="b064a-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="b064a-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="b064a-110">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="b064a-110">Supported Types</span></span>  

 <span data-ttu-id="b064a-111">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="b064a-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="b064a-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="b064a-112">Result</span></span>  

 <span data-ttu-id="b064a-113">El resultado es el cociente entero de `expression1` divide by `expression2` , que descarta cualquier resto y solo conserva la parte entera.</span><span class="sxs-lookup"><span data-stu-id="b064a-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="b064a-114">Esto se conoce como *truncamiento*.</span><span class="sxs-lookup"><span data-stu-id="b064a-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="b064a-115">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="b064a-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="b064a-116">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="b064a-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="b064a-117">El [operador/(Visual Basic)](floating-point-division-operator.md) devuelve el cociente completo, que conserva el resto de la parte fraccionaria.</span><span class="sxs-lookup"><span data-stu-id="b064a-117">The [/ Operator (Visual Basic)](floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b064a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b064a-118">Remarks</span></span>  

 <span data-ttu-id="b064a-119">Antes de realizar la división, Visual Basic intenta convertir cualquier expresión numérica de punto flotante en `Long` .</span><span class="sxs-lookup"><span data-stu-id="b064a-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="b064a-120">Si `Option Strict` es `On` , se produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="b064a-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="b064a-121">Si `Option Strict` es `Off` , <xref:System.OverflowException> es posible si el valor está fuera del intervalo del tipo de [datos Long](../data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b064a-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../data-types/long-data-type.md).</span></span> <span data-ttu-id="b064a-122">La conversión a `Long` también está sujeta a *redondeo bancario*.</span><span class="sxs-lookup"><span data-stu-id="b064a-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="b064a-123">Para obtener más información, vea "partes fraccionarias" en [funciones de conversión de tipos](../functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="b064a-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="b064a-124">Si `expression1` o `expression2` se evalúa como [Nothing](../nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="b064a-124">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="b064a-125">División intentada por cero</span><span class="sxs-lookup"><span data-stu-id="b064a-125">Attempted Division by Zero</span></span>  

 <span data-ttu-id="b064a-126">Si `expression2` se evalúa como cero, el `\` operador produce una <xref:System.DivideByZeroException> excepción.</span><span class="sxs-lookup"><span data-stu-id="b064a-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="b064a-127">Esto es así para todos los tipos de datos numéricos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="b064a-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b064a-128">El `\` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b064a-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b064a-129">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="b064a-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b064a-130">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b064a-130">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b064a-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b064a-131">Example</span></span>  

 <span data-ttu-id="b064a-132">En el ejemplo siguiente se usa el `\` operador para realizar la división de enteros.</span><span class="sxs-lookup"><span data-stu-id="b064a-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="b064a-133">El resultado es un entero que representa el cociente entero de los dos operandos, con el resto descartado.</span><span class="sxs-lookup"><span data-stu-id="b064a-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="b064a-134">Las expresiones del ejemplo anterior devuelven los valores 2, 3, 33 y-22, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b064a-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b064a-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b064a-135">See also</span></span>

- [<span data-ttu-id="b064a-136">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="b064a-136">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="b064a-137">Operador/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b064a-137">/ Operator (Visual Basic)</span></span>](floating-point-division-operator.md)
- [<span data-ttu-id="b064a-138">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b064a-138">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="b064a-139">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="b064a-139">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b064a-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b064a-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b064a-141">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="b064a-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b064a-142">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b064a-142">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
