---
description: 'Más información sobre: parámetros y argumentos de procedimientos (Visual Basic)'
title: Argumentos y parámetros de procedimiento
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
ms.openlocfilehash: c2239c76450f503e74dbf5f191cd212e05d11600
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423165"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="ea224-103">Argumentos y parámetros de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea224-103">Procedure Parameters and Arguments (Visual Basic)</span></span>

<span data-ttu-id="ea224-104">En la mayoría de los casos, un procedimiento necesita cierta información sobre las circunstancias en las que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="ea224-104">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="ea224-105">Un procedimiento que realiza tareas repetidas o compartidas utiliza información diferente para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="ea224-105">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="ea224-106">Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="ea224-106">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="ea224-107">Un *parámetro* representa un valor que el procedimiento espera que proporcione al llamarlo.</span><span class="sxs-lookup"><span data-stu-id="ea224-107">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="ea224-108">La declaración del procedimiento define sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="ea224-108">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="ea224-109">Puede definir un procedimiento sin parámetros, un parámetro o más de uno.</span><span class="sxs-lookup"><span data-stu-id="ea224-109">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="ea224-110">La parte de la definición de procedimiento que especifica los parámetros se denomina *lista de parámetros*.</span><span class="sxs-lookup"><span data-stu-id="ea224-110">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="ea224-111">Un *argumento* representa el valor que se proporciona a un parámetro de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ea224-111">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="ea224-112">El código de llamada proporciona los argumentos cuando llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ea224-112">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="ea224-113">La parte de la llamada a procedimiento que especifica los argumentos se denomina *lista de argumentos*.</span><span class="sxs-lookup"><span data-stu-id="ea224-113">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="ea224-114">En la ilustración siguiente se muestra el código que llama al procedimiento `safeSquareRoot` desde dos lugares diferentes.</span><span class="sxs-lookup"><span data-stu-id="ea224-114">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="ea224-115">La primera llamada pasa el valor de la variable `x` (4,0) al parámetro `number` y el valor devuelto en `root` (2,0) se asigna a la variable `y` .</span><span class="sxs-lookup"><span data-stu-id="ea224-115">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="ea224-116">La segunda llamada pasa el valor literal 9,0 a `number` y asigna el valor devuelto (3,0) a la variable `z` .</span><span class="sxs-lookup"><span data-stu-id="ea224-116">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![Diagrama que muestra cómo pasar un argumento a un parámetro](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="ea224-118">Para obtener más información, vea [diferencias entre parámetros y argumentos](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="ea224-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="ea224-119">Parámetro, tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ea224-119">Parameter Data Type</span></span>  

 <span data-ttu-id="ea224-120">Para definir un tipo de datos para un parámetro, use la `As` cláusula en su declaración.</span><span class="sxs-lookup"><span data-stu-id="ea224-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="ea224-121">Por ejemplo, la función siguiente acepta una cadena y un entero.</span><span class="sxs-lookup"><span data-stu-id="ea224-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="ea224-122">Si el modificador de comprobación de tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) es `Off,` la `As` cláusula es opcional, salvo que si alguno de los parámetros lo usa, todos los parámetros deben utilizarla.</span><span class="sxs-lookup"><span data-stu-id="ea224-122">If the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="ea224-123">Si la comprobación de tipos es `On` , la `As` cláusula es necesaria para todos los parámetros de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ea224-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="ea224-124">Si el código de llamada espera proporcionar un argumento con un tipo de datos diferente del parámetro correspondiente, como `Byte` un `String` parámetro, debe realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ea224-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="ea224-125">Proporcione solo argumentos con tipos de datos que se amplíen al tipo de datos del parámetro;</span><span class="sxs-lookup"><span data-stu-id="ea224-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="ea224-126">`Option Strict Off`Se establece para permitir las conversiones de restricción implícitas; o</span><span class="sxs-lookup"><span data-stu-id="ea224-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="ea224-127">Use una palabra clave de conversión para convertir explícitamente el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ea224-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="ea224-128">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ea224-128">Type Parameters</span></span>  

 <span data-ttu-id="ea224-129">Un *procedimiento genérico* también define uno o varios *parámetros de tipo* además de sus parámetros normales.</span><span class="sxs-lookup"><span data-stu-id="ea224-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="ea224-130">Un procedimiento genérico permite al código de llamada pasar tipos de datos diferentes cada vez que llama al procedimiento, por lo que puede personalizar los tipos de datos según los requisitos de cada llamada individual.</span><span class="sxs-lookup"><span data-stu-id="ea224-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="ea224-131">Vea [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ea224-131">See [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea224-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea224-132">See also</span></span>

- [<span data-ttu-id="ea224-133">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ea224-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ea224-134">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="ea224-134">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ea224-135">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="ea224-135">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="ea224-136">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="ea224-136">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ea224-137">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="ea224-137">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="ea224-138">Procedimiento para definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ea224-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="ea224-139">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ea224-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="ea224-140">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="ea224-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ea224-141">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ea224-141">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="ea224-142">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea224-142">Type Conversions in Visual Basic</span></span>](../data-types/type-conversions.md)
