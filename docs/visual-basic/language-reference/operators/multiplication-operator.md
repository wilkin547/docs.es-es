---
title: '* (Operador) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 450d728e44ef5639d75369e05b47cb3009b4d769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="57745-102">* (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57745-102">* Operator (Visual Basic)</span></span>
<span data-ttu-id="57745-103">Multiplica dos números.</span><span class="sxs-lookup"><span data-stu-id="57745-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57745-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57745-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="57745-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="57745-105">Parts</span></span>  
  
|<span data-ttu-id="57745-106">Término</span><span class="sxs-lookup"><span data-stu-id="57745-106">Term</span></span>|<span data-ttu-id="57745-107">Definición</span><span class="sxs-lookup"><span data-stu-id="57745-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="57745-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="57745-108">Required.</span></span> <span data-ttu-id="57745-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="57745-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="57745-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="57745-110">Required.</span></span> <span data-ttu-id="57745-111">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="57745-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="57745-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="57745-112">Result</span></span>  
 <span data-ttu-id="57745-113">El resultado es el producto de `number1` y `number2`.</span><span class="sxs-lookup"><span data-stu-id="57745-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="57745-114">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="57745-114">Supported Types</span></span>  
 <span data-ttu-id="57745-115">Todos los tipos numéricos, incluidos los tipos sin signo y de punto flotante y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="57745-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57745-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57745-116">Remarks</span></span>  
 <span data-ttu-id="57745-117">El tipo de datos del resultado depende de los tipos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="57745-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="57745-118">En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="57745-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="57745-119">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="57745-119">Operand data types</span></span>|<span data-ttu-id="57745-120">Tipo de datos de resultado</span><span class="sxs-lookup"><span data-stu-id="57745-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="57745-121">Ambas expresiones son tipos de datos integrales ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [bytes](../../../visual-basic/language-reference/data-types/byte-data-type.md), [corto](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [entero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [largo](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="57745-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="57745-122">Tipo de datos numérico adecuado para los tipos de datos de `number1` y `number2`.</span><span class="sxs-lookup"><span data-stu-id="57745-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="57745-123">Vea las tablas "Aritmética de enteros" en [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="57745-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="57745-124">Ambas expresiones son [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="57745-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="57745-125">Ambas expresiones son [único](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="57745-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="57745-126">Cualquier expresión es un tipo de datos de punto flotante (`Single` o [doble](../../../visual-basic/language-reference/data-types/double-data-type.md)), pero no ambos `Single` (Nota `Decimal` no es un tipo de datos de punto flotante)</span><span class="sxs-lookup"><span data-stu-id="57745-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="57745-127">Si una expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="57745-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="57745-128">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="57745-128">Overloading</span></span>  
 <span data-ttu-id="57745-129">El `*` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="57745-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="57745-130">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="57745-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="57745-131">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="57745-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57745-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57745-132">Example</span></span>  
 <span data-ttu-id="57745-133">Este ejemplo se utiliza la `*` operador para multiplicar dos números.</span><span class="sxs-lookup"><span data-stu-id="57745-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="57745-134">El resultado es el producto de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="57745-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="57745-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="57745-135">See Also</span></span>  
 [<span data-ttu-id="57745-136">Operador *=</span><span class="sxs-lookup"><span data-stu-id="57745-136">*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="57745-137">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="57745-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="57745-138">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57745-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="57745-139">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="57745-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="57745-140">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57745-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
