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
ms.openlocfilehash: 42f85ed98f399c96f89879129b085f25ab117096
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731743"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="a246e-102">Argumentos y parámetros de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a246e-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="a246e-103">En la mayoría de los casos, un procedimiento necesita cierta información sobre las circunstancias en que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="a246e-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="a246e-104">Un procedimiento que realiza tareas repetitivas o compartidas utiliza información diferente para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="a246e-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="a246e-105">Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a246e-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="a246e-106">Un *parámetro* representa un valor que el procedimiento espera que proporcione al llamarla.</span><span class="sxs-lookup"><span data-stu-id="a246e-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="a246e-107">La declaración del procedimiento define sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="a246e-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="a246e-108">Puede definir un procedimiento sin parámetros, un parámetro o más de uno.</span><span class="sxs-lookup"><span data-stu-id="a246e-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="a246e-109">La parte de la definición del procedimiento que especifica los parámetros se denomina el *lista_de_parámetros*.</span><span class="sxs-lookup"><span data-stu-id="a246e-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="a246e-110">Un *argumento* representa el valor que se proporciona a un parámetro de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a246e-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="a246e-111">El código de llamada proporciona los argumentos cuando llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a246e-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="a246e-112">La parte de la llamada de procedimiento que especifica los argumentos se denomina el *lista de argumentos*.</span><span class="sxs-lookup"><span data-stu-id="a246e-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="a246e-113">La siguiente ilustración muestra el código que llama al procedimiento `safeSquareRoot` desde dos lugares diferentes.</span><span class="sxs-lookup"><span data-stu-id="a246e-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="a246e-114">La primera llamada pasa el valor de la variable `x` (4.0) al parámetro `number`y el valor devuelto en `root` (2.0) se asigna a la variable `y`.</span><span class="sxs-lookup"><span data-stu-id="a246e-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="a246e-115">La segunda llamada pasa el valor literal 9.0 a `number`y asigna el valor devuelto (3.0) a la variable `z`.</span><span class="sxs-lookup"><span data-stu-id="a246e-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="a246e-116">![Diagrama gráfico de paso de argumentos al parámetro](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="a246e-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="a246e-117">Pasar un argumento a un parámetro</span><span class="sxs-lookup"><span data-stu-id="a246e-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="a246e-118">Para obtener más información, consulte [diferencias entre parámetros y argumentos](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="a246e-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="a246e-119">Tipo de datos de parámetro</span><span class="sxs-lookup"><span data-stu-id="a246e-119">Parameter Data Type</span></span>  
 <span data-ttu-id="a246e-120">Definir un tipo de datos para un parámetro mediante el `As` cláusula en su declaración.</span><span class="sxs-lookup"><span data-stu-id="a246e-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="a246e-121">Por ejemplo, la función siguiente acepta una cadena y un entero.</span><span class="sxs-lookup"><span data-stu-id="a246e-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 <span data-ttu-id="a246e-122">Si el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `Off,` el `As` cláusula es opcional, salvo que si lo utiliza un parámetro, todos los parámetros deben usarla.</span><span class="sxs-lookup"><span data-stu-id="a246e-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="a246e-123">Si la comprobación de tipos es `On`, el `As` cláusula es obligatoria para todos los parámetros de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a246e-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="a246e-124">Si espera que el código de llamada proporcionar un argumento con un tipo de datos diferente del parámetro correspondiente, como `Byte` a un `String` parámetro, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a246e-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="a246e-125">Proporcionar sólo argumentos con tipos de datos que se convierten en el tipo de datos del parámetro;</span><span class="sxs-lookup"><span data-stu-id="a246e-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="a246e-126">Establecer `Option Strict Off` para permitir que las conversiones de restricción implícitas; o</span><span class="sxs-lookup"><span data-stu-id="a246e-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="a246e-127">Utilizar una palabra clave de conversión para convertir explícitamente el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a246e-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="a246e-128">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a246e-128">Type Parameters</span></span>  
 <span data-ttu-id="a246e-129">Un *procedimiento genérico* también define uno o más *parámetros de tipo* además de sus parámetros normales.</span><span class="sxs-lookup"><span data-stu-id="a246e-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="a246e-130">Un procedimiento genérico permite que el código de llamada pasar tipos de datos diferentes cada vez que llama al procedimiento, por lo que puede personalizar los tipos de datos a los requisitos de cada llamada individual.</span><span class="sxs-lookup"><span data-stu-id="a246e-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="a246e-131">Vea [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a246e-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a246e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a246e-132">See also</span></span>
- [<span data-ttu-id="a246e-133">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="a246e-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a246e-134">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="a246e-134">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a246e-135">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="a246e-135">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="a246e-136">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="a246e-136">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a246e-137">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="a246e-137">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="a246e-138">Cómo: Definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="a246e-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="a246e-139">Cómo: Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="a246e-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="a246e-140">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="a246e-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="a246e-141">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="a246e-141">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="a246e-142">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a246e-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
