---
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
ms.openlocfilehash: b5129c2dbb361940fa6da2cb424ee23736ba72c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875332"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="ce9e0-102">- (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce9e0-102">- Operator (Visual Basic)</span></span>

<span data-ttu-id="ce9e0-103">Devuelve la diferencia entre dos expresiones numéricas o el valor negativo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce9e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce9e0-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="ce9e0-105">o</span><span class="sxs-lookup"><span data-stu-id="ce9e0-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="ce9e0-106">Partes</span><span class="sxs-lookup"><span data-stu-id="ce9e0-106">Parts</span></span>  

 `expression1`  
 <span data-ttu-id="ce9e0-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-107">Required.</span></span> <span data-ttu-id="ce9e0-108">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ce9e0-109">Obligatorio a menos que el `–` operador calcule un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="ce9e0-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="ce9e0-111">Resultado</span><span class="sxs-lookup"><span data-stu-id="ce9e0-111">Result</span></span>  

 <span data-ttu-id="ce9e0-112">El resultado es la diferencia entre `expression1` y `expression2` , o el valor negado de `expression1` .</span><span class="sxs-lookup"><span data-stu-id="ce9e0-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="ce9e0-113">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="ce9e0-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="ce9e0-114">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="ce9e0-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="ce9e0-115">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="ce9e0-115">Supported Types</span></span>  

 <span data-ttu-id="ce9e0-116">todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-116">All numeric types.</span></span> <span data-ttu-id="ce9e0-117">Esto incluye los tipos de punto flotante y sin signo y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="ce9e0-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce9e0-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce9e0-118">Remarks</span></span>  

 <span data-ttu-id="ce9e0-119">En el primer uso que se muestra en la sintaxis mostrada anteriormente, el operador `–` es el operador de resta aritmética *binaria* para la diferencia entre dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="ce9e0-120">En el segundo uso que se muestra en la sintaxis mostrada anteriormente, el `–` operador es el operador *unario* de negación para el valor negativo de una expresión.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="ce9e0-121">En este sentido, la negación consiste en invertir el signo de `expression1` para que el resultado sea positivo si `expression1` es negativo.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="ce9e0-122">Si alguna de las expresiones se evalúa como [Nothing](../nothing.md), el `–` operador la trata como cero.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-122">If either expression evaluates to [Nothing](../nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce9e0-123">El `–` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ce9e0-124">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="ce9e0-125">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ce9e0-125">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce9e0-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce9e0-126">Example</span></span>  

 <span data-ttu-id="ce9e0-127">En el ejemplo siguiente se usa el `–` operador para calcular y devolver la diferencia entre dos números y, a continuación, para negar un número.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="ce9e0-128">Después de la ejecución de estas instrucciones, `binaryResult` contiene 124,45 y `unaryResult` contiene – 334,90.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9e0-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce9e0-129">See also</span></span>

- [<span data-ttu-id="ce9e0-130">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce9e0-130">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="ce9e0-131">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="ce9e0-131">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ce9e0-132">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce9e0-132">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="ce9e0-133">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="ce9e0-133">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="ce9e0-134">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce9e0-134">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
