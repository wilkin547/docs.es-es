---
title: '- Operador (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830674"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="c04c2-102">- (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c04c2-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="c04c2-103">Devuelve la diferencia entre dos expresiones numéricas o el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c04c2-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c04c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c04c2-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="c04c2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c04c2-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="c04c2-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c04c2-106">Required.</span></span> <span data-ttu-id="c04c2-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c04c2-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c04c2-108">Obligatoria a menos que el `–` operador calcula un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="c04c2-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="c04c2-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="c04c2-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="c04c2-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="c04c2-110">Result</span></span>  
 <span data-ttu-id="c04c2-111">El resultado es la diferencia entre `expression1` y `expression2`, o el valor negado de `expression1`.</span><span class="sxs-lookup"><span data-stu-id="c04c2-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="c04c2-112">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.</span><span class="sxs-lookup"><span data-stu-id="c04c2-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="c04c2-113">Vea las tablas "Aritmética de enteros" en [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="c04c2-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="c04c2-114">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="c04c2-114">Supported Types</span></span>  
 <span data-ttu-id="c04c2-115">todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="c04c2-115">All numeric types.</span></span> <span data-ttu-id="c04c2-116">Esto incluye los tipos sin signo y de punto flotante y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="c04c2-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c04c2-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c04c2-117">Remarks</span></span>  
 <span data-ttu-id="c04c2-118">En el primer uso, se muestra en la sintaxis mostrada anteriormente, el `–` operador es la *binario* operador aritmético de sustracción de la diferencia entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="c04c2-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="c04c2-119">En el segundo uso se muestra en la sintaxis mostrada anteriormente, el `–` operador es la *unario* operador de negación para el valor negativo de una expresión.</span><span class="sxs-lookup"><span data-stu-id="c04c2-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="c04c2-120">En este sentido, la negación invierte el signo de `expression1` para que el resultado es positivo si `expression1` es negativo.</span><span class="sxs-lookup"><span data-stu-id="c04c2-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="c04c2-121">Si una de las expresiones se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el `–` operador lo trata como cero.</span><span class="sxs-lookup"><span data-stu-id="c04c2-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c04c2-122">El `–` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c04c2-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c04c2-123">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que comprende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="c04c2-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="c04c2-124">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c04c2-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c04c2-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c04c2-125">Example</span></span>  
 <span data-ttu-id="c04c2-126">En el ejemplo siguiente se usa el `–` operador para calcular y devolver la diferencia entre dos números y, a continuación, para negar un número.</span><span class="sxs-lookup"><span data-stu-id="c04c2-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="c04c2-127">Tras la ejecución de estas instrucciones, `binaryResult` contiene 124.45 y `unaryResult` contiene -334.90.</span><span class="sxs-lookup"><span data-stu-id="c04c2-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04c2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c04c2-128">See also</span></span>

- [<span data-ttu-id="c04c2-129">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c04c2-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="c04c2-130">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="c04c2-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="c04c2-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c04c2-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c04c2-132">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="c04c2-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c04c2-133">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c04c2-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
