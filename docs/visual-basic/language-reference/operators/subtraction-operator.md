---
description: 'Más información acerca de: operador (Visual Basic)'
title: '- Operator'
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
ms.openlocfilehash: 858e887fa7c5c0cc6129996c98bddb78bc53045c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795266"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="1c7ff-103">- (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c7ff-103">- Operator (Visual Basic)</span></span>

<span data-ttu-id="1c7ff-104">Devuelve la diferencia entre dos expresiones numéricas o el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-104">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c7ff-105">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="1c7ff-106">o</span><span class="sxs-lookup"><span data-stu-id="1c7ff-106">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="1c7ff-107">Partes</span><span class="sxs-lookup"><span data-stu-id="1c7ff-107">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="1c7ff-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-108">Required.</span></span> <span data-ttu-id="1c7ff-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-109">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="1c7ff-110">Obligatorio a menos que el `–` operador calcule un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-110">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="1c7ff-111">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-111">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="1c7ff-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="1c7ff-112">Result</span></span>  

 <span data-ttu-id="1c7ff-113">El resultado es la diferencia entre `expression1` y `expression2` , o el valor negado de `expression1` .</span><span class="sxs-lookup"><span data-stu-id="1c7ff-113">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="1c7ff-114">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="1c7ff-114">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="1c7ff-115">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="1c7ff-115">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="1c7ff-116">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="1c7ff-116">Supported Types</span></span>  

 <span data-ttu-id="1c7ff-117">todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-117">All numeric types.</span></span> <span data-ttu-id="1c7ff-118">Esto incluye los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="1c7ff-118">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c7ff-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c7ff-119">Remarks</span></span>  

 <span data-ttu-id="1c7ff-120">En el primer uso que se muestra en la sintaxis mostrada anteriormente, el operador `–` es el operador de resta aritmética *binaria* para la diferencia entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-120">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="1c7ff-121">En el segundo uso que se muestra en la sintaxis mostrada anteriormente, el `–` operador es el operador *unario* de negación para el valor negativo de una expresión.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-121">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="1c7ff-122">En este sentido, la negación consiste en invertir el signo de `expression1` para que el resultado sea positivo si `expression1` es negativo.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-122">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="1c7ff-123">Si alguna de las expresiones se evalúa como [Nothing](../nothing.md), el `–` operador la trata como cero.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-123">If either expression evaluates to [Nothing](../nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c7ff-124">El `–` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-124">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1c7ff-125">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-125">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="1c7ff-126">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1c7ff-126">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c7ff-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c7ff-127">Example</span></span>  

 <span data-ttu-id="1c7ff-128">En el ejemplo siguiente se usa el `–` operador para calcular y devolver la diferencia entre dos números y, a continuación, para negar un número.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-128">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="1c7ff-129">Después de la ejecución de estas instrucciones, `binaryResult` contiene 124,45 y `unaryResult` contiene – 334,90.</span><span class="sxs-lookup"><span data-stu-id="1c7ff-129">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7ff-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c7ff-130">See also</span></span>

- [<span data-ttu-id="1c7ff-131">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c7ff-131">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="1c7ff-132">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1c7ff-132">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="1c7ff-133">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c7ff-133">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="1c7ff-134">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1c7ff-134">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="1c7ff-135">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c7ff-135">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
