---
title: Operadores - Guía de programación de C#
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 551d4cd8bf26a1c1caf3cbf611d9f338ae2581be
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609502"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="150c7-102">Operadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="150c7-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="150c7-103">En C#, un *operador* es un elemento de programa que se aplica a uno o varios *operandos* en una expresión o instrucción.</span><span class="sxs-lookup"><span data-stu-id="150c7-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="150c7-104">Los operadores que toman un operando, como el operador de incremento (`++`) o `new`, se conocen como operadores *unarios* .</span><span class="sxs-lookup"><span data-stu-id="150c7-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="150c7-105">Los operadores que toman dos operandos, como los operadores aritméticos (`+`,`-`,`*`,`/`) se conocen como operadores *binarios* .</span><span class="sxs-lookup"><span data-stu-id="150c7-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="150c7-106">Un operador, el operador condicional (`?:`), toma tres operandos y es el único operador ternario de C#.</span><span class="sxs-lookup"><span data-stu-id="150c7-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="150c7-107">La instrucción de C# siguiente contiene un solo operador unario y un único operando.</span><span class="sxs-lookup"><span data-stu-id="150c7-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="150c7-108">El operador de incremento, `++`, modifica el valor del operando `y`.</span><span class="sxs-lookup"><span data-stu-id="150c7-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="150c7-109">La instrucción de C# siguiente contiene dos operadores binarios, cada uno con dos operandos.</span><span class="sxs-lookup"><span data-stu-id="150c7-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="150c7-110">El operador de asignaciones, `=`, tiene la variable de entero `y` y la expresión `2 + 3` como operandos.</span><span class="sxs-lookup"><span data-stu-id="150c7-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="150c7-111">La propia expresión `2 + 3` está compuesta del operador de suma y dos operandos, `2` y `3`.</span><span class="sxs-lookup"><span data-stu-id="150c7-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="150c7-112">Un operando puede ser una expresión válida que se compone de código de una longitud indeterminada y puede incluir un número cualquiera de subexpresiones.</span><span class="sxs-lookup"><span data-stu-id="150c7-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="150c7-113">En una expresión que contiene varios operadores, el orden de aplicación de estos viene determinado por la *prioridad de operador*, la *asociatividad*y los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="150c7-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="150c7-114">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="150c7-114">Operator precedence</span></span>
  
<span data-ttu-id="150c7-115">Cada operador tiene una prioridad definida.</span><span class="sxs-lookup"><span data-stu-id="150c7-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="150c7-116">En una expresión que contiene varios operadores con distintos niveles de prioridad, la prioridad de los operadores determina el orden en que estos se evalúan.</span><span class="sxs-lookup"><span data-stu-id="150c7-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="150c7-117">Por ejemplo, la instrucción siguiente asigna 3 a `n1`:</span><span class="sxs-lookup"><span data-stu-id="150c7-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="150c7-118">La multiplicación se ejecuta en primer lugar porque tiene prioridad sobre la resta.</span><span class="sxs-lookup"><span data-stu-id="150c7-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="150c7-119">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea [Operadores de C#](../../language-reference/operators/index.md).</span><span class="sxs-lookup"><span data-stu-id="150c7-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="150c7-120">asociatividad</span><span class="sxs-lookup"><span data-stu-id="150c7-120">Associativity</span></span>

 <span data-ttu-id="150c7-121">Cuando dos o más operadores con la misma prioridad están presentes en una expresión, se evalúan según su asociatividad.</span><span class="sxs-lookup"><span data-stu-id="150c7-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="150c7-122">Los operadores asociativos a la izquierda se evalúan, por orden, de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="150c7-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="150c7-123">Por ejemplo, `x * y / z` se evalúa como `(x * y) / z`.</span><span class="sxs-lookup"><span data-stu-id="150c7-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="150c7-124">Los operadores asociativos a la derecha se evalúan, por orden, de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="150c7-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="150c7-125">Por ejemplo, el operador de asignación es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="150c7-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="150c7-126">De lo contrario, el código siguiente produciría un error.</span><span class="sxs-lookup"><span data-stu-id="150c7-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="150c7-127">Otro ejemplo sería el operador ternario ([?:](../../../csharp/language-reference/operators/conditional-operator.md)), que es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="150c7-127">As another example the ternary operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="150c7-128">La mayoría de los operadores binarios son asociativos a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="150c7-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="150c7-129">Independientemente de que los operadores de una expresión sean asociativos a la izquierda o a la derecha, los operandos de cada expresión se evalúan primero, de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="150c7-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="150c7-130">En los siguientes ejemplos se muestra el orden de evaluación de los operadores y los operandos.</span><span class="sxs-lookup"><span data-stu-id="150c7-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="150c7-131">Instrucción</span><span class="sxs-lookup"><span data-stu-id="150c7-131">Statement</span></span>|<span data-ttu-id="150c7-132">Orden de evaluación</span><span class="sxs-lookup"><span data-stu-id="150c7-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="150c7-133">a, b, =</span><span class="sxs-lookup"><span data-stu-id="150c7-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="150c7-134">a, b, c, +, =</span><span class="sxs-lookup"><span data-stu-id="150c7-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="150c7-135">a, b, c, d, \*, +, =</span><span class="sxs-lookup"><span data-stu-id="150c7-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="150c7-136">a, b, c, \*, d, +, =</span><span class="sxs-lookup"><span data-stu-id="150c7-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="150c7-137">a, b, c, -, d, +, =</span><span class="sxs-lookup"><span data-stu-id="150c7-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="150c7-138">a, b, c, -=, +=</span><span class="sxs-lookup"><span data-stu-id="150c7-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="150c7-139">Agregar paréntesis</span><span class="sxs-lookup"><span data-stu-id="150c7-139">Adding parentheses</span></span>

 <span data-ttu-id="150c7-140">Se puede cambiar el orden impuesto por la prioridad de operador y la asociatividad mediante el uso de paréntesis.</span><span class="sxs-lookup"><span data-stu-id="150c7-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="150c7-141">Por ejemplo, `2 + 3 * 2` suele evaluarse como 8, porque los operadores de multiplicación tienen prioridad sobre los operadores de suma.</span><span class="sxs-lookup"><span data-stu-id="150c7-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="150c7-142">Sin embargo, si se escribe la expresión como `(2 + 3) * 2`, la suma se evalúa antes que la multiplicación y el resultado es 10.</span><span class="sxs-lookup"><span data-stu-id="150c7-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="150c7-143">En los siguientes ejemplos se muestra el orden de evaluación en las expresiones entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="150c7-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="150c7-144">Como en ejemplos anteriores, los operandos se evalúan antes de aplicarse el operador.</span><span class="sxs-lookup"><span data-stu-id="150c7-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="150c7-145">Instrucción</span><span class="sxs-lookup"><span data-stu-id="150c7-145">Statement</span></span>|<span data-ttu-id="150c7-146">Orden de evaluación</span><span class="sxs-lookup"><span data-stu-id="150c7-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="150c7-147">a, b, c, +, d, \*, =</span><span class="sxs-lookup"><span data-stu-id="150c7-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="150c7-148">a, b, c, d, +, -, =</span><span class="sxs-lookup"><span data-stu-id="150c7-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="150c7-149">a, b, c, +, d, e, -, \*, =</span><span class="sxs-lookup"><span data-stu-id="150c7-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="150c7-150">Sobrecarga de operadores</span><span class="sxs-lookup"><span data-stu-id="150c7-150">Operator overloading</span></span>

<span data-ttu-id="150c7-151">Puede definir el comportamiento de algunos operadores para clases y estructuras personalizadas.</span><span class="sxs-lookup"><span data-stu-id="150c7-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="150c7-152">Este proceso se conoce como *sobrecarga de operadores*.</span><span class="sxs-lookup"><span data-stu-id="150c7-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="150c7-153">Para obtener más información, vea [Sobrecarga de operadores](../../language-reference/operators/operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="150c7-153">For more information, see [Operator overloading](../../language-reference/operators/operator-overloading.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="150c7-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="150c7-154">See also</span></span>

- [<span data-ttu-id="150c7-155">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="150c7-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="150c7-156">Instrucciones, expresiones y operadores</span><span class="sxs-lookup"><span data-stu-id="150c7-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="150c7-157">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="150c7-157">C# Operators</span></span>](../../language-reference/operators/index.md)
