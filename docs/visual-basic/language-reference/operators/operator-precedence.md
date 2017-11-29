---
title: Prioridad de operador en Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="b78a5-102">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b78a5-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="b78a5-103">Cuando se producen varias operaciones en una expresión, cada parte se evalúa y se resuelve en un orden predeterminado denominado *precedencia de operadores*.</span><span class="sxs-lookup"><span data-stu-id="b78a5-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="b78a5-104">Reglas de prioridad</span><span class="sxs-lookup"><span data-stu-id="b78a5-104">Precedence Rules</span></span>  
 <span data-ttu-id="b78a5-105">Cuando las expresiones contienen operadores de más de una categoría, se evalúan según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b78a5-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="b78a5-106">Los operadores aritméticos y de concatenación tienen el orden de prioridad que se describe en la sección siguiente y todos tienen mayor prioridad que la comparación, lógicos y operadores bit a bit.</span><span class="sxs-lookup"><span data-stu-id="b78a5-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="b78a5-107">Todos los operadores de comparación tienen la misma precedencia y todos tienen mayor prioridad que los operadores lógicos y bit a bit, pero menor prioridad que los operadores aritméticos y de concatenación.</span><span class="sxs-lookup"><span data-stu-id="b78a5-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="b78a5-108">Los operadores lógicos y bit a bit tienen el orden de prioridad que se describe en la sección siguiente y todos tienen menos prioridad que los aritméticos, de concatenación y operadores de comparación.</span><span class="sxs-lookup"><span data-stu-id="b78a5-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="b78a5-109">Operadores con la misma prioridad se evalúan de izquierda a derecha en el orden en que aparecen en la expresión.</span><span class="sxs-lookup"><span data-stu-id="b78a5-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="b78a5-110">Orden de prioridad</span><span class="sxs-lookup"><span data-stu-id="b78a5-110">Precedence Order</span></span>  
 <span data-ttu-id="b78a5-111">Los operadores se evalúan en el siguiente orden de prioridad:</span><span class="sxs-lookup"><span data-stu-id="b78a5-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="b78a5-112">Await (Operador)</span><span class="sxs-lookup"><span data-stu-id="b78a5-112">Await Operator</span></span>  
 <span data-ttu-id="b78a5-113">await</span><span class="sxs-lookup"><span data-stu-id="b78a5-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="b78a5-114">Operaciones aritméticas y operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="b78a5-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="b78a5-115">Exponenciación (`^`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="b78a5-116">Unario identidad y negación (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="b78a5-117">Multiplicación y división de coma flotante (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="b78a5-118">División de enteros (`\`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="b78a5-119">Módulo aritmético (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="b78a5-120">Suma y resta (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="b78a5-121">Concatenación de cadenas (`&`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="b78a5-122">Desplazamiento de bits aritmético (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="b78a5-123">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="b78a5-123">Comparison Operators</span></span>  
 <span data-ttu-id="b78a5-124">Todos los operadores de comparación (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="b78a5-125">Operadores lógicos y bit a bit</span><span class="sxs-lookup"><span data-stu-id="b78a5-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="b78a5-126">Negación (`Not`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="b78a5-127">Conjunción (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="b78a5-128">Disyunción inclusiva (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="b78a5-129">Disyunción exclusiva (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="b78a5-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="b78a5-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b78a5-130">Comments</span></span>  
 <span data-ttu-id="b78a5-131">El `=` operador es solo el operador de comparación de igualdad, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="b78a5-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="b78a5-132">El operador de concatenación de cadenas (`&`) no es un operador aritmético, pero en prioridad, se agrupa con los operadores aritméticos.</span><span class="sxs-lookup"><span data-stu-id="b78a5-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="b78a5-133">El `Is` y `IsNot` operadores son operadores de comparación de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="b78a5-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="b78a5-134">No se comparan los valores de dos objetos; sólo comprueban y para determinar si dos variables de objeto hacen referencia a la misma instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="b78a5-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="b78a5-135">Asociatividad</span><span class="sxs-lookup"><span data-stu-id="b78a5-135">Associativity</span></span>  
 <span data-ttu-id="b78a5-136">Cuando los operadores tienen la misma precedencia aparecen juntas en una expresión, por ejemplo, multiplicación y división, el compilador evalúa cada operación tal y como encuentra de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="b78a5-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="b78a5-137">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b78a5-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="b78a5-138">La primera expresión se evalúa como la división de 96 / 8 (que da como resultado 12) y, a continuación, la división de 12 / 4, lo que resulta en tres.</span><span class="sxs-lookup"><span data-stu-id="b78a5-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="b78a5-139">Dado que el compilador evalúa las operaciones de `n1` de izquierda a derecha, la evaluación equivale cuando ese orden está indicado de forma explícita `n2`.</span><span class="sxs-lookup"><span data-stu-id="b78a5-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="b78a5-140">Ambos `n1` y `n2` dan como resultado un de tres.</span><span class="sxs-lookup"><span data-stu-id="b78a5-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="b78a5-141">Por el contrario, `n3` ha producido como resultado 48, porque los paréntesis fuerzan al compilador que evaluar 8 / 4 primero.</span><span class="sxs-lookup"><span data-stu-id="b78a5-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="b78a5-142">Debido a este comportamiento, se dice que los operadores *asociativos a la izquierda* en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b78a5-142">Because of this behavior, operators are said to be *left associative* in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="b78a5-143">Reemplazar la prioridad y asociatividad</span><span class="sxs-lookup"><span data-stu-id="b78a5-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="b78a5-144">Puede usar paréntesis para forzar que algunas partes de una expresión se evalúe antes que otras.</span><span class="sxs-lookup"><span data-stu-id="b78a5-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="b78a5-145">Esto puede invalidar el orden de prioridad y asociatividad por la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b78a5-145">This can override both the order of precedence and the left associativity.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="b78a5-146">siempre realiza operaciones que se encierran entre paréntesis antes de aquellos que no pertenecen.</span><span class="sxs-lookup"><span data-stu-id="b78a5-146"> always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="b78a5-147">Sin embargo, entre paréntesis, mantiene normal prioridad y asociatividad, a menos que utilice paréntesis dentro del paréntesis.</span><span class="sxs-lookup"><span data-stu-id="b78a5-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="b78a5-148">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b78a5-148">The following example illustrates this.</span></span>  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a><span data-ttu-id="b78a5-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="b78a5-149">See Also</span></span>  
 [<span data-ttu-id="b78a5-150">Operador =</span><span class="sxs-lookup"><span data-stu-id="b78a5-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="b78a5-151">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="b78a5-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="b78a5-152">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="b78a5-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="b78a5-153">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="b78a5-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="b78a5-154">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="b78a5-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="b78a5-155">Await (operador)</span><span class="sxs-lookup"><span data-stu-id="b78a5-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="b78a5-156">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="b78a5-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b78a5-157">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="b78a5-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
