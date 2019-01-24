---
title: Procedimientos de operador (Visual Basic)
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
ms.openlocfilehash: 611195143fd216caab0b5f89badefb93d7dea017
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589115"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="e97f4-102">Procedimientos de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e97f4-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="e97f4-103">Un procedimiento de operador es una serie de instrucciones de Visual Basic que definen el comportamiento de un operador estándar (como `*`, `<>`, o `And`) en una clase o estructura que ha definido.</span><span class="sxs-lookup"><span data-stu-id="e97f4-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="e97f4-104">Esto también se denomina *sobrecarga de operadores*.</span><span class="sxs-lookup"><span data-stu-id="e97f4-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="e97f4-105">Cuándo se debe definir los procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="e97f4-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="e97f4-106">Cuando haya definido una clase o estructura, puede declarar variables sea del tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="e97f4-107">A veces este tipo de variable debe participar en una operación como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="e97f4-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="e97f4-108">Para ello, debe ser un operando de un operador.</span><span class="sxs-lookup"><span data-stu-id="e97f4-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="e97f4-109">Visual Basic sólo define operadores en sus tipos de datos fundamentales.</span><span class="sxs-lookup"><span data-stu-id="e97f4-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="e97f4-110">Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="e97f4-111">Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e97f4-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="e97f4-112">Tipos de procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="e97f4-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="e97f4-113">Un procedimiento de operador puede ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="e97f4-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="e97f4-114">Una definición de un operador unario donde el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="e97f4-115">Una definición de un operador binario donde al menos uno de los argumentos es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="e97f4-116">Una definición de un operador de conversión donde el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="e97f4-117">Una definición de un operador de conversión que devuelve el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="e97f4-118">Los operadores de conversión siempre son unarias y siempre utilizan `CType` como el operador que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="e97f4-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="e97f4-119">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="e97f4-119">Declaration Syntax</span></span>  
 <span data-ttu-id="e97f4-120">La sintaxis para declarar un procedimiento de operador es como sigue:</span><span class="sxs-lookup"><span data-stu-id="e97f4-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="e97f4-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="e97f4-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="e97f4-122">Usa el `Widening` o `Narrowing` palabra clave solo en un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="e97f4-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="e97f4-123">El símbolo del operador es siempre [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="e97f4-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="e97f4-124">Declare dos operandos para definir un operador binario y declare un operando para definir un operador unario, como un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="e97f4-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="e97f4-125">Todos los operandos deben declararse `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="e97f4-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="e97f4-126">Declarar cada operando de la misma manera que declarar los parámetros para [subprocedimientos](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e97f4-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="e97f4-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e97f4-127">Data Type</span></span>  
 <span data-ttu-id="e97f4-128">Dado que va a definir un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="e97f4-129">Para un operador de conversión de tipos, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e97f4-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="e97f4-130">Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e97f4-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="e97f4-131">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="e97f4-131">Calling Syntax</span></span>  
 <span data-ttu-id="e97f4-132">Invocar un procedimiento de operador implícitamente mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e97f4-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="e97f4-133">Proporcione los operandos de la misma manera que para los operadores predefinidos.</span><span class="sxs-lookup"><span data-stu-id="e97f4-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="e97f4-134">La sintaxis de una llamada implícita a un procedimiento de operador es como sigue:</span><span class="sxs-lookup"><span data-stu-id="e97f4-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="e97f4-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="e97f4-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="e97f4-136">`Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol*   `10`</span><span class="sxs-lookup"><span data-stu-id="e97f4-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="e97f4-137">Ilustración de la declaración y llamada</span><span class="sxs-lookup"><span data-stu-id="e97f4-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="e97f4-138">La siguiente estructura almacena un valor entero de 128 bits con signo como las partes constituyentes de orden superior y orden inferior.</span><span class="sxs-lookup"><span data-stu-id="e97f4-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="e97f4-139">Define el `+` operador para agregar dos `veryLong` valores y generar una resultante `veryLong` valor.</span><span class="sxs-lookup"><span data-stu-id="e97f4-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 <span data-ttu-id="e97f4-140">El ejemplo siguiente muestra una llamada típica para la `+` operador definido en `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="e97f4-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 <span data-ttu-id="e97f4-141">Para obtener más información y ejemplos, vea [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx) (Sobrecarga de operadores en Visual Basic 2005).</span><span class="sxs-lookup"><span data-stu-id="e97f4-141">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e97f4-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="e97f4-142">See also</span></span>
- [<span data-ttu-id="e97f4-143">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e97f4-143">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e97f4-144">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="e97f4-144">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e97f4-145">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="e97f4-145">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="e97f4-146">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="e97f4-146">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e97f4-147">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="e97f4-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e97f4-148">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e97f4-148">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="e97f4-149">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="e97f4-149">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="e97f4-150">Cómo: Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="e97f4-150">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="e97f4-151">Cómo: Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="e97f4-151">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="e97f4-152">Cómo: Usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="e97f4-152">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
