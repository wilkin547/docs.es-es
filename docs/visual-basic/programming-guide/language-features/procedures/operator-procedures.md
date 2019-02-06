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
ms.openlocfilehash: 6b9912f5206633a45d5d5d2d9c8c25ffab94ed9b
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739571"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="9ced6-102">Procedimientos de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ced6-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="9ced6-103">Un procedimiento de operador es una serie de instrucciones de Visual Basic que definen el comportamiento de un operador estándar (como `*`, `<>`, o `And`) en una clase o estructura que ha definido.</span><span class="sxs-lookup"><span data-stu-id="9ced6-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="9ced6-104">Esto también se denomina *sobrecarga de operadores*.</span><span class="sxs-lookup"><span data-stu-id="9ced6-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="9ced6-105">Cuándo se debe definir los procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="9ced6-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="9ced6-106">Cuando haya definido una clase o estructura, puede declarar variables sea del tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="9ced6-107">A veces este tipo de variable debe participar en una operación como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="9ced6-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="9ced6-108">Para ello, debe ser un operando de un operador.</span><span class="sxs-lookup"><span data-stu-id="9ced6-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="9ced6-109">Visual Basic sólo define operadores en sus tipos de datos fundamentales.</span><span class="sxs-lookup"><span data-stu-id="9ced6-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="9ced6-110">Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="9ced6-111">Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9ced6-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="9ced6-112">Tipos de procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="9ced6-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="9ced6-113">Un procedimiento de operador puede ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="9ced6-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="9ced6-114">Una definición de un operador unario donde el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="9ced6-115">Una definición de un operador binario donde al menos uno de los argumentos es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="9ced6-116">Una definición de un operador de conversión donde el argumento es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="9ced6-117">Una definición de un operador de conversión que devuelve el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="9ced6-118">Los operadores de conversión siempre son unarias y siempre utilizan `CType` como el operador que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="9ced6-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="9ced6-119">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="9ced6-119">Declaration Syntax</span></span>  
 <span data-ttu-id="9ced6-120">La sintaxis para declarar un procedimiento de operador es como sigue:</span><span class="sxs-lookup"><span data-stu-id="9ced6-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="9ced6-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="9ced6-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="9ced6-122">Usa el `Widening` o `Narrowing` palabra clave solo en un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="9ced6-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="9ced6-123">El símbolo del operador es siempre [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="9ced6-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="9ced6-124">Declare dos operandos para definir un operador binario y declare un operando para definir un operador unario, como un operador de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="9ced6-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="9ced6-125">Todos los operandos deben declararse `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="9ced6-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="9ced6-126">Declarar cada operando de la misma manera que declarar los parámetros para [subprocedimientos](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9ced6-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="9ced6-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9ced6-127">Data Type</span></span>  
 <span data-ttu-id="9ced6-128">Dado que va a definir un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="9ced6-129">Para un operador de conversión de tipos, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="9ced6-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="9ced6-130">Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9ced6-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="9ced6-131">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="9ced6-131">Calling Syntax</span></span>  
 <span data-ttu-id="9ced6-132">Invocar un procedimiento de operador implícitamente mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="9ced6-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="9ced6-133">Proporcione los operandos de la misma manera que para los operadores predefinidos.</span><span class="sxs-lookup"><span data-stu-id="9ced6-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="9ced6-134">La sintaxis de una llamada implícita a un procedimiento de operador es como sigue:</span><span class="sxs-lookup"><span data-stu-id="9ced6-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="9ced6-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="9ced6-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="9ced6-136">`Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol*  `10`</span><span class="sxs-lookup"><span data-stu-id="9ced6-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="9ced6-137">Ilustración de la declaración y llamada</span><span class="sxs-lookup"><span data-stu-id="9ced6-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="9ced6-138">La siguiente estructura almacena un valor entero de 128 bits con signo como las partes constituyentes de orden superior y orden inferior.</span><span class="sxs-lookup"><span data-stu-id="9ced6-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="9ced6-139">Define el `+` operador para agregar dos `veryLong` valores y generar una resultante `veryLong` valor.</span><span class="sxs-lookup"><span data-stu-id="9ced6-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 <span data-ttu-id="9ced6-140">El ejemplo siguiente muestra una llamada típica para la `+` operador definido en `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="9ced6-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
  
## <a name="see-also"></a><span data-ttu-id="9ced6-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ced6-141">See also</span></span>
- [<span data-ttu-id="9ced6-142">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced6-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9ced6-143">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="9ced6-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="9ced6-144">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="9ced6-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="9ced6-145">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="9ced6-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="9ced6-146">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="9ced6-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9ced6-147">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9ced6-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="9ced6-148">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="9ced6-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="9ced6-149">Cómo: Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="9ced6-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="9ced6-150">Cómo: Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="9ced6-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="9ced6-151">Cómo: Usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="9ced6-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
