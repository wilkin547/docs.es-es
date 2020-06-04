---
title: Prioridad de los operadores
ms.date: 07/20/2015
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
ms.openlocfilehash: eef6314f5fc1f5a7fffa7997559f697130f6f755
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401451"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="b1f30-102">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1f30-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="b1f30-103">Cuando se producen varias operaciones en una expresión, cada parte se evalúa y se resuelve en un orden predeterminado denominado *precedencia de operadores*.</span><span class="sxs-lookup"><span data-stu-id="b1f30-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="b1f30-104">Reglas de precedencia</span><span class="sxs-lookup"><span data-stu-id="b1f30-104">Precedence Rules</span></span>
 <span data-ttu-id="b1f30-105">Cuando las expresiones contienen operadores de más de una categoría, se evalúan según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1f30-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="b1f30-106">Los operadores aritméticos y de concatenación tienen el orden de prioridad que se describe en la sección siguiente y todos tienen mayor prioridad que los operadores de comparación, lógicos y bit a bit.</span><span class="sxs-lookup"><span data-stu-id="b1f30-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="b1f30-107">Todos los operadores de comparación tienen la misma prioridad y todos tienen mayor prioridad que los operadores lógicos y bit a bit, pero tienen menor prioridad que los operadores aritméticos y de concatenación.</span><span class="sxs-lookup"><span data-stu-id="b1f30-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="b1f30-108">Los operadores lógicos y bit a bit tienen el orden de prioridad que se describe en la sección siguiente y todos tienen menor prioridad que los operadores aritméticos, de concatenación y de comparación.</span><span class="sxs-lookup"><span data-stu-id="b1f30-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="b1f30-109">Los operadores con la misma prioridad se evalúan de izquierda a derecha en el orden en que aparecen en la expresión.</span><span class="sxs-lookup"><span data-stu-id="b1f30-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="b1f30-110">Orden de prioridad</span><span class="sxs-lookup"><span data-stu-id="b1f30-110">Precedence Order</span></span>
 <span data-ttu-id="b1f30-111">Los operadores se evalúan en el orden de prioridad siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1f30-111">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="b1f30-112">Await (Operador)</span><span class="sxs-lookup"><span data-stu-id="b1f30-112">Await Operator</span></span>
 <span data-ttu-id="b1f30-113">Operador</span><span class="sxs-lookup"><span data-stu-id="b1f30-113">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="b1f30-114">Operadores aritméticos y de concatenación</span><span class="sxs-lookup"><span data-stu-id="b1f30-114">Arithmetic and Concatenation Operators</span></span>
 <span data-ttu-id="b1f30-115">Exponenciación ( `^` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-115">Exponentiation (`^`)</span></span>

 <span data-ttu-id="b1f30-116">Identidad unaria y negación ( `+` , `–` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-116">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="b1f30-117">Multiplicación y división de punto flotante ( `*` , `/` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-117">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="b1f30-118">División de enteros ( `\` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-118">Integer division (`\`)</span></span>

 <span data-ttu-id="b1f30-119">Aritmética modular ( `Mod` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-119">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="b1f30-120">Suma y resta ( `+` , `–` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-120">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="b1f30-121">Concatenación de cadenas ( `&` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-121">String concatenation (`&`)</span></span>

 <span data-ttu-id="b1f30-122">Desplazamiento de bits aritmético ( `<<` , `>>` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-122">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="b1f30-123">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="b1f30-123">Comparison Operators</span></span>
 <span data-ttu-id="b1f30-124">Todos los operadores de comparación ( `=` , `<>` , `<` , `<=` , `>` , `>=` , `Is` , `IsNot` , `Like` , `TypeOf` ... `Is` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="b1f30-125">Operadores lógicos y bit a bit</span><span class="sxs-lookup"><span data-stu-id="b1f30-125">Logical and Bitwise Operators</span></span>
 <span data-ttu-id="b1f30-126">Negación ( `Not` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-126">Negation (`Not`)</span></span>

 <span data-ttu-id="b1f30-127">Conjunción ( `And` , `AndAlso` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-127">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="b1f30-128">Disyunción inclusiva ( `Or` , `OrElse` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="b1f30-129">Disyunción exclusiva ( `Xor` )</span><span class="sxs-lookup"><span data-stu-id="b1f30-129">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="b1f30-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1f30-130">Comments</span></span>
 <span data-ttu-id="b1f30-131">El `=` operador es solo el operador de comparación de igualdad, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="b1f30-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="b1f30-132">El operador de concatenación de cadenas ( `&` ) no es un operador aritmético, pero en su precedencia está agrupado con los operadores aritméticos.</span><span class="sxs-lookup"><span data-stu-id="b1f30-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="b1f30-133">Los `Is` `IsNot` operadores y son operadores de comparación de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="b1f30-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="b1f30-134">No comparan los valores de dos objetos; solo comprueban si dos variables de objeto hacen referencia a la misma instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="b1f30-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="b1f30-135">asociatividad</span><span class="sxs-lookup"><span data-stu-id="b1f30-135">Associativity</span></span>
 <span data-ttu-id="b1f30-136">Cuando los operadores de igual precedencia aparecen juntos en una expresión, por ejemplo multiplicación y división, el compilador evalúa cada operación a medida que la encuentra de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="b1f30-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="b1f30-137">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b1f30-137">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="b1f30-138">La primera expresión evalúa la división 96/8 (que da como resultado 12) y, a continuación, la división 12/4, que da como resultado tres.</span><span class="sxs-lookup"><span data-stu-id="b1f30-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="b1f30-139">Dado que el compilador evalúa las operaciones de `n1` izquierda a derecha, la evaluación es la misma cuando ese orden se indica explícitamente para `n2` .</span><span class="sxs-lookup"><span data-stu-id="b1f30-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="b1f30-140">`n1`Y `n2` tienen el resultado de tres.</span><span class="sxs-lookup"><span data-stu-id="b1f30-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="b1f30-141">Por el contrario, `n3` tiene un resultado de 48, porque los paréntesis obligan al compilador a evaluar 8/4 primero.</span><span class="sxs-lookup"><span data-stu-id="b1f30-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="b1f30-142">Debido a este comportamiento, se dice que los operadores son *asociativos* a la izquierda en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b1f30-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="b1f30-143">Reemplazar precedencia y asociatividad</span><span class="sxs-lookup"><span data-stu-id="b1f30-143">Overriding Precedence and Associativity</span></span>
 <span data-ttu-id="b1f30-144">Puede usar paréntesis para forzar que se evalúen algunas partes de una expresión antes que otras.</span><span class="sxs-lookup"><span data-stu-id="b1f30-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="b1f30-145">Esto puede invalidar el orden de prioridad y la asociatividad izquierda.</span><span class="sxs-lookup"><span data-stu-id="b1f30-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="b1f30-146">Visual Basic siempre realiza las operaciones que se incluyen entre paréntesis antes de las externas.</span><span class="sxs-lookup"><span data-stu-id="b1f30-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="b1f30-147">Sin embargo, entre paréntesis, mantiene la prioridad y la asociatividad ordinarias, a menos que use paréntesis dentro de los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="b1f30-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="b1f30-148">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b1f30-148">The following example illustrates this.</span></span>

```vb
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

## <a name="see-also"></a><span data-ttu-id="b1f30-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1f30-149">See also</span></span>

- [<span data-ttu-id="b1f30-150">= (Operador)</span><span class="sxs-lookup"><span data-stu-id="b1f30-150">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="b1f30-151">Operador is</span><span class="sxs-lookup"><span data-stu-id="b1f30-151">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="b1f30-152">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="b1f30-152">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="b1f30-153">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="b1f30-153">Like Operator</span></span>](like-operator.md)
- [<span data-ttu-id="b1f30-154">Typeof (operador)</span><span class="sxs-lookup"><span data-stu-id="b1f30-154">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="b1f30-155">Await (operador)</span><span class="sxs-lookup"><span data-stu-id="b1f30-155">Await Operator</span></span>](await-operator.md)
- [<span data-ttu-id="b1f30-156">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="b1f30-156">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b1f30-157">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="b1f30-157">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
