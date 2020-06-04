---
title: '* Operador'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: f1a7653fb3006ab3c9736ec168a8c5ea028f4763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409331"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c261e-102">\* (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c261e-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="c261e-103">Multiplica dos números.</span><span class="sxs-lookup"><span data-stu-id="c261e-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c261e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c261e-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="c261e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c261e-105">Parts</span></span>  
  
|<span data-ttu-id="c261e-106">Término</span><span class="sxs-lookup"><span data-stu-id="c261e-106">Term</span></span>|<span data-ttu-id="c261e-107">Definición</span><span class="sxs-lookup"><span data-stu-id="c261e-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="c261e-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c261e-108">Required.</span></span> <span data-ttu-id="c261e-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c261e-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="c261e-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c261e-110">Required.</span></span> <span data-ttu-id="c261e-111">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c261e-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="c261e-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="c261e-112">Result</span></span>  
 <span data-ttu-id="c261e-113">El resultado es el producto de `number1` y `number2` .</span><span class="sxs-lookup"><span data-stu-id="c261e-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="c261e-114">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="c261e-114">Supported Types</span></span>  
 <span data-ttu-id="c261e-115">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="c261e-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c261e-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c261e-116">Remarks</span></span>  
 <span data-ttu-id="c261e-117">El tipo de datos del resultado depende de los tipos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="c261e-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="c261e-118">En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="c261e-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="c261e-119">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="c261e-119">Operand data types</span></span>|<span data-ttu-id="c261e-120">Tipo de datos de resultados</span><span class="sxs-lookup"><span data-stu-id="c261e-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="c261e-121">Ambas expresiones son tipos de datos enteros ([SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="c261e-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="c261e-122">Un tipo de datos numérico adecuado para los tipos de datos de `number1` y `number2` .</span><span class="sxs-lookup"><span data-stu-id="c261e-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="c261e-123">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="c261e-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="c261e-124">Ambas expresiones son [decimales](../data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="c261e-124">Both expressions are [Decimal](../data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="c261e-125">Ambas expresiones son [únicas](../data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="c261e-125">Both expressions are [Single](../data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="c261e-126">Cualquier expresión es un tipo de datos de punto flotante ( `Single` o [Double](../data-types/double-data-type.md)), pero no ambos `Single` ( `Decimal` la nota no es un tipo de datos de punto flotante)</span><span class="sxs-lookup"><span data-stu-id="c261e-126">Either expression is a floating-point data type (`Single` or [Double](../data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="c261e-127">Si una expresión se evalúa como [Nothing](../nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="c261e-127">If an expression evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c261e-128">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="c261e-128">Overloading</span></span>  
 <span data-ttu-id="c261e-129">El `*` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c261e-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c261e-130">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="c261e-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c261e-131">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c261e-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c261e-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c261e-132">Example</span></span>  
 <span data-ttu-id="c261e-133">En este ejemplo se usa el `*` operador para multiplicar dos números.</span><span class="sxs-lookup"><span data-stu-id="c261e-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="c261e-134">El resultado es el producto de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="c261e-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c261e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c261e-135">See also</span></span>

- [<span data-ttu-id="c261e-136">\* = (Operador)</span><span class="sxs-lookup"><span data-stu-id="c261e-136">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="c261e-137">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="c261e-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="c261e-138">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c261e-138">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c261e-139">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="c261e-139">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c261e-140">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c261e-140">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
