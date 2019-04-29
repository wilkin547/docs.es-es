---
title: Argumentos y parámetros de procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: 80065cabcacdcf44b04fef7bacb978ca9c8077ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791916"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="42373-102">Argumentos y parámetros de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42373-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="42373-103">En la mayoría de los casos, un procedimiento necesita cierta información sobre las circunstancias en que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="42373-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="42373-104">Un procedimiento que realiza tareas repetitivas o compartidas utiliza información diferente para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="42373-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="42373-105">Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="42373-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="42373-106">Un *parámetro* representa un valor que el procedimiento espera que proporcione al llamarla.</span><span class="sxs-lookup"><span data-stu-id="42373-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="42373-107">La declaración del procedimiento define sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="42373-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="42373-108">Puede definir un procedimiento sin parámetros, un parámetro o más de uno.</span><span class="sxs-lookup"><span data-stu-id="42373-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="42373-109">La parte de la definición del procedimiento que especifica los parámetros se denomina el *lista_de_parámetros*.</span><span class="sxs-lookup"><span data-stu-id="42373-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="42373-110">Un *argumento* representa el valor que se proporciona a un parámetro de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="42373-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="42373-111">El código de llamada proporciona los argumentos cuando llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="42373-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="42373-112">La parte de la llamada de procedimiento que especifica los argumentos se denomina el *lista de argumentos*.</span><span class="sxs-lookup"><span data-stu-id="42373-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="42373-113">La siguiente ilustración muestra el código que llama al procedimiento `safeSquareRoot` desde dos lugares diferentes.</span><span class="sxs-lookup"><span data-stu-id="42373-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="42373-114">La primera llamada pasa el valor de la variable `x` (4.0) al parámetro `number`y el valor devuelto en `root` (2.0) se asigna a la variable `y`.</span><span class="sxs-lookup"><span data-stu-id="42373-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="42373-115">La segunda llamada pasa el valor literal 9.0 a `number`y asigna el valor devuelto (3.0) a la variable `z`.</span><span class="sxs-lookup"><span data-stu-id="42373-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![Diagrama que muestra pasa un argumento a un parámetro](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="42373-117">Para obtener más información, consulte [diferencias entre parámetros y argumentos](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="42373-117">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="42373-118">Tipo de datos de parámetro</span><span class="sxs-lookup"><span data-stu-id="42373-118">Parameter Data Type</span></span>  
 <span data-ttu-id="42373-119">Definir un tipo de datos para un parámetro mediante el `As` cláusula en su declaración.</span><span class="sxs-lookup"><span data-stu-id="42373-119">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="42373-120">Por ejemplo, la función siguiente acepta una cadena y un entero.</span><span class="sxs-lookup"><span data-stu-id="42373-120">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="42373-121">Si el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `Off,` el `As` cláusula es opcional, salvo que si lo utiliza un parámetro, todos los parámetros deben usarla.</span><span class="sxs-lookup"><span data-stu-id="42373-121">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="42373-122">Si la comprobación de tipos es `On`, el `As` cláusula es obligatoria para todos los parámetros de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="42373-122">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="42373-123">Si espera que el código de llamada proporcionar un argumento con un tipo de datos diferente del parámetro correspondiente, como `Byte` a un `String` parámetro, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42373-123">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="42373-124">Proporcionar sólo argumentos con tipos de datos que se convierten en el tipo de datos del parámetro;</span><span class="sxs-lookup"><span data-stu-id="42373-124">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="42373-125">Establecer `Option Strict Off` para permitir que las conversiones de restricción implícitas; o</span><span class="sxs-lookup"><span data-stu-id="42373-125">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="42373-126">Utilizar una palabra clave de conversión para convertir explícitamente el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="42373-126">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="42373-127">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="42373-127">Type Parameters</span></span>  
 <span data-ttu-id="42373-128">Un *procedimiento genérico* también define uno o más *parámetros de tipo* además de sus parámetros normales.</span><span class="sxs-lookup"><span data-stu-id="42373-128">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="42373-129">Un procedimiento genérico permite que el código de llamada pasar tipos de datos diferentes cada vez que llama al procedimiento, por lo que puede personalizar los tipos de datos a los requisitos de cada llamada individual.</span><span class="sxs-lookup"><span data-stu-id="42373-129">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="42373-130">Vea [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="42373-130">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42373-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="42373-131">See also</span></span>

- [<span data-ttu-id="42373-132">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42373-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="42373-133">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="42373-133">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="42373-134">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="42373-134">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="42373-135">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="42373-135">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="42373-136">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="42373-136">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="42373-137">Cómo: Definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="42373-137">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="42373-138">Cómo: Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="42373-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="42373-139">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="42373-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="42373-140">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="42373-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="42373-141">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42373-141">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
