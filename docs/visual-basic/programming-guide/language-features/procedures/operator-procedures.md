---
description: 'Más información sobre: procedimientos de operador (Visual Basic)'
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
ms.openlocfilehash: 836eeb2e705a96c49b5fa53e277ccf025d1915b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479964"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="002ff-103">Procedimientos de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="002ff-103">Operator Procedures (Visual Basic)</span></span>

<span data-ttu-id="002ff-104">Un procedimiento de operador es una serie de instrucciones Visual Basic que definen el comportamiento de un operador estándar (como `*` , `<>` o `And` ) en una clase o estructura que ha definido.</span><span class="sxs-lookup"><span data-stu-id="002ff-104">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="002ff-105">Esto también se denomina *sobrecarga de operadores*.</span><span class="sxs-lookup"><span data-stu-id="002ff-105">This is also called *operator overloading*.</span></span>

## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="002ff-106">Cuándo definir procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="002ff-106">When to Define Operator Procedures</span></span>

<span data-ttu-id="002ff-107">Cuando haya definido una clase o estructura, puede declarar variables para que sean del tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-107">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="002ff-108">A veces, una variable de este tipo debe participar en una operación como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="002ff-108">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="002ff-109">Para ello, debe ser un operando de un operador.</span><span class="sxs-lookup"><span data-stu-id="002ff-109">To do this, it must be an operand of an operator.</span></span>

<span data-ttu-id="002ff-110">Visual Basic define operadores solo en sus tipos de datos fundamentales.</span><span class="sxs-lookup"><span data-stu-id="002ff-110">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="002ff-111">Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-111">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>

<span data-ttu-id="002ff-112">Para obtener más información, vea [Operator Statement](../../../language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="002ff-112">For more information, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="types-of-operator-procedure"></a><span data-ttu-id="002ff-113">Tipos de procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="002ff-113">Types of Operator Procedure</span></span>

<span data-ttu-id="002ff-114">Un procedimiento de operador puede ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="002ff-114">An operator procedure can be one of the following types:</span></span>

- <span data-ttu-id="002ff-115">Definición de un operador unario en el que el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-115">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="002ff-116">Definición de un operador binario en el que al menos uno de los argumentos es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-116">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>

- <span data-ttu-id="002ff-117">Definición de un operador de conversión en el que el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-117">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="002ff-118">Definición de un operador de conversión que devuelve el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-118">A definition of a conversion operator that returns the type of your class or structure.</span></span>

 <span data-ttu-id="002ff-119">Los operadores de conversión siempre son unarios y siempre se usan `CType` como el operador que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="002ff-119">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="002ff-120">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="002ff-120">Declaration Syntax</span></span>

<span data-ttu-id="002ff-121">La sintaxis para declarar un procedimiento de operador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="002ff-121">The syntax for declaring an operator procedure is as follows:</span></span>

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

<span data-ttu-id="002ff-122">La `Widening` `Narrowing` palabra clave o solo se usa en un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="002ff-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="002ff-123">El símbolo del operador siempre es la [función ctype](../../../language-reference/functions/ctype-function.md) para un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="002ff-123">The operator symbol is always [CType Function](../../../language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>

<span data-ttu-id="002ff-124">Se declaran dos operandos para definir un operador binario y se declara un operando para definir un operador unario, incluido un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="002ff-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="002ff-125">Se deben declarar todos los operandos `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="002ff-125">All operands must be declared `ByVal`.</span></span>

<span data-ttu-id="002ff-126">Cada operando se declara de la misma manera que se declaran los parámetros para [los procedimientos sub](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="002ff-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="002ff-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="002ff-127">Data Type</span></span>

<span data-ttu-id="002ff-128">Dado que está definiendo un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="002ff-129">Para un operador de conversión de tipos, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="002ff-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>

<span data-ttu-id="002ff-130">Para obtener más información, vea [Operator Statement](../../../language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="002ff-130">For more details, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="002ff-131">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="002ff-131">Calling Syntax</span></span>

<span data-ttu-id="002ff-132">Un procedimiento de operador se invoca implícitamente mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="002ff-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="002ff-133">Los operandos se proporcionan de la misma manera que para los operadores predefinidos.</span><span class="sxs-lookup"><span data-stu-id="002ff-133">You supply the operands the same way you do for predefined operators.</span></span>

<span data-ttu-id="002ff-134">La sintaxis de una llamada implícita a un procedimiento de operador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="002ff-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>

<span data-ttu-id="002ff-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="002ff-135">`Dim testStruct As`  *structurename*</span></span>

<span data-ttu-id="002ff-136">`Dim testNewStruct As`  *structurename* `= testStruct` *símbolodeoperador*      `10`</span><span class="sxs-lookup"><span data-stu-id="002ff-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="002ff-137">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="002ff-137">Illustration of Declaration and Call</span></span>

<span data-ttu-id="002ff-138">La siguiente estructura almacena un valor entero de 128 bits con signo como el componente de orden superior y de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="002ff-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="002ff-139">Define el `+` operador para sumar dos `veryLong` valores y generar un `veryLong` valor resultante.</span><span class="sxs-lookup"><span data-stu-id="002ff-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

<span data-ttu-id="002ff-140">En el ejemplo siguiente se muestra una llamada típica al `+` operador definido en `veryLong` .</span><span class="sxs-lookup"><span data-stu-id="002ff-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="002ff-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="002ff-141">See also</span></span>

- [<span data-ttu-id="002ff-142">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="002ff-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="002ff-143">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="002ff-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="002ff-144">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="002ff-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="002ff-145">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="002ff-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="002ff-146">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="002ff-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="002ff-147">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="002ff-147">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="002ff-148">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="002ff-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="002ff-149">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="002ff-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="002ff-150">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="002ff-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="002ff-151">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="002ff-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
