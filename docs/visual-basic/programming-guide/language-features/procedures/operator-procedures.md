---
title: Procedimientos de operador
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: a1dd183570c8aa50efff85bdaebef90bd3b0120f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364323"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="10b60-102">Procedimientos de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10b60-102">Operator Procedures (Visual Basic)</span></span>

<span data-ttu-id="10b60-103">Un procedimiento de operador es una serie de instrucciones Visual Basic que definen el comportamiento de un operador estándar (como `*` , `<>` o `And` ) en una clase o estructura que ha definido.</span><span class="sxs-lookup"><span data-stu-id="10b60-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="10b60-104">Esto también se denomina *sobrecarga de operadores*.</span><span class="sxs-lookup"><span data-stu-id="10b60-104">This is also called *operator overloading*.</span></span>

## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="10b60-105">Cuándo definir procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="10b60-105">When to Define Operator Procedures</span></span>

<span data-ttu-id="10b60-106">Cuando haya definido una clase o estructura, puede declarar variables para que sean del tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="10b60-107">A veces, una variable de este tipo debe participar en una operación como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="10b60-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="10b60-108">Para ello, debe ser un operando de un operador.</span><span class="sxs-lookup"><span data-stu-id="10b60-108">To do this, it must be an operand of an operator.</span></span>

<span data-ttu-id="10b60-109">Visual Basic define operadores solo en sus tipos de datos fundamentales.</span><span class="sxs-lookup"><span data-stu-id="10b60-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="10b60-110">Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>

<span data-ttu-id="10b60-111">Para obtener más información, vea [Operator Statement](../../../language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="10b60-111">For more information, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="types-of-operator-procedure"></a><span data-ttu-id="10b60-112">Tipos de procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="10b60-112">Types of Operator Procedure</span></span>

<span data-ttu-id="10b60-113">Un procedimiento de operador puede ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="10b60-113">An operator procedure can be one of the following types:</span></span>

- <span data-ttu-id="10b60-114">Definición de un operador unario en el que el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="10b60-115">Definición de un operador binario en el que al menos uno de los argumentos es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>

- <span data-ttu-id="10b60-116">Definición de un operador de conversión en el que el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="10b60-117">Definición de un operador de conversión que devuelve el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>

 <span data-ttu-id="10b60-118">Los operadores de conversión siempre son unarios y siempre se usan `CType` como el operador que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="10b60-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="10b60-119">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="10b60-119">Declaration Syntax</span></span>

<span data-ttu-id="10b60-120">La sintaxis para declarar un procedimiento de operador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="10b60-120">The syntax for declaring an operator procedure is as follows:</span></span>

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

<span data-ttu-id="10b60-121">La `Widening` `Narrowing` palabra clave o solo se usa en un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="10b60-121">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="10b60-122">El símbolo del operador siempre es la [función ctype](../../../language-reference/functions/ctype-function.md) para un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="10b60-122">The operator symbol is always [CType Function](../../../language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>

<span data-ttu-id="10b60-123">Se declaran dos operandos para definir un operador binario y se declara un operando para definir un operador unario, incluido un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="10b60-123">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="10b60-124">Se deben declarar todos los operandos `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="10b60-124">All operands must be declared `ByVal`.</span></span>

<span data-ttu-id="10b60-125">Cada operando se declara de la misma manera que se declaran los parámetros para [los procedimientos sub](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="10b60-125">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="10b60-126">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="10b60-126">Data Type</span></span>

<span data-ttu-id="10b60-127">Dado que está definiendo un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-127">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="10b60-128">Para un operador de conversión de tipos, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="10b60-128">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>

<span data-ttu-id="10b60-129">Para obtener más información, vea [Operator Statement](../../../language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="10b60-129">For more details, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="10b60-130">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="10b60-130">Calling Syntax</span></span>

<span data-ttu-id="10b60-131">Un procedimiento de operador se invoca implícitamente mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="10b60-131">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="10b60-132">Los operandos se proporcionan de la misma manera que para los operadores predefinidos.</span><span class="sxs-lookup"><span data-stu-id="10b60-132">You supply the operands the same way you do for predefined operators.</span></span>

<span data-ttu-id="10b60-133">La sintaxis de una llamada implícita a un procedimiento de operador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="10b60-133">The syntax for an implicit call to an operator procedure is as follows:</span></span>

<span data-ttu-id="10b60-134">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="10b60-134">`Dim testStruct As`  *structurename*</span></span>

<span data-ttu-id="10b60-135">`Dim testNewStruct As`  *structurename* `= testStruct` *símbolodeoperador*      `10`</span><span class="sxs-lookup"><span data-stu-id="10b60-135">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="10b60-136">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="10b60-136">Illustration of Declaration and Call</span></span>

<span data-ttu-id="10b60-137">La siguiente estructura almacena un valor entero de 128 bits con signo como el componente de orden superior y de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="10b60-137">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="10b60-138">Define el `+` operador para sumar dos `veryLong` valores y generar un `veryLong` valor resultante.</span><span class="sxs-lookup"><span data-stu-id="10b60-138">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

<span data-ttu-id="10b60-139">En el ejemplo siguiente se muestra una llamada típica al `+` operador definido en `veryLong` .</span><span class="sxs-lookup"><span data-stu-id="10b60-139">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="10b60-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10b60-140">See also</span></span>

- [<span data-ttu-id="10b60-141">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="10b60-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="10b60-142">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="10b60-142">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="10b60-143">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="10b60-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="10b60-144">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="10b60-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="10b60-145">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="10b60-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="10b60-146">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="10b60-146">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="10b60-147">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="10b60-147">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="10b60-148">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="10b60-148">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="10b60-149">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="10b60-149">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="10b60-150">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="10b60-150">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
