---
title: "Cómo: Definir parámetros para un procedimiento (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c909cfe1b45a42aae91948917f310474575f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="51c08-102">Cómo: Definir parámetros para un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51c08-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="51c08-103">A *parámetro* permite que el código que realiza la llamada pasar un valor al procedimiento cuando lo llama.</span><span class="sxs-lookup"><span data-stu-id="51c08-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="51c08-104">Declarar cada parámetro para un procedimiento de la misma manera que se declara una variable, especificando su nombre y tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="51c08-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="51c08-105">También especifica el mecanismo para pasar argumentos, y si el parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="51c08-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="51c08-106">Para obtener más información, consulte [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="51c08-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="51c08-107">Para definir un parámetro de procedimiento</span><span class="sxs-lookup"><span data-stu-id="51c08-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="51c08-108">En la declaración de procedimiento, agregue el nombre de parámetro a la lista de parámetros del procedimiento, sepárelo de otros parámetros mediante comas.</span><span class="sxs-lookup"><span data-stu-id="51c08-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="51c08-109">Decida el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="51c08-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="51c08-110">Siga el nombre del parámetro con un `As` cláusula para especificar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="51c08-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="51c08-111">Decida el mecanismo de paso que desee para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="51c08-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="51c08-112">Normalmente se pasa un parámetro por valor, a menos que desee que el procedimiento para que pueda cambiar su valor en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="51c08-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="51c08-113">Delante del nombre de parámetro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para especificar el mecanismo de paso.</span><span class="sxs-lookup"><span data-stu-id="51c08-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="51c08-114">Para obtener más información, consulte [las diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="51c08-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="51c08-115">Si el parámetro es opcional, precedido por el mecanismo de paso con [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) y siga el tipo de datos de parámetro con un signo igual (`=`) y un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="51c08-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="51c08-116">En el ejemplo siguiente se define el esquema de un `Sub` procedimiento con tres parámetros.</span><span class="sxs-lookup"><span data-stu-id="51c08-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="51c08-117">Los dos primeros son necesarios y el tercero es opcional.</span><span class="sxs-lookup"><span data-stu-id="51c08-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="51c08-118">Las declaraciones de parámetros se separan en la lista de parámetros mediante comas.</span><span class="sxs-lookup"><span data-stu-id="51c08-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     <span data-ttu-id="51c08-119">El primer parámetro acepta un `customer` objeto, y `updateCustomer` puede actualizar directamente la variable pasada a `c` porque el argumento se pasa [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="51c08-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="51c08-120">El procedimiento no puede cambiar los valores de los últimos dos argumentos porque se pasan [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="51c08-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="51c08-121">Si el código de llamada no proporciona un valor para el `level` parámetro, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] lo establece en el valor predeterminado de 0.</span><span class="sxs-lookup"><span data-stu-id="51c08-121">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="51c08-122">Si la comprobación de tipos cambia ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `Off`, el `As` cláusula es opcional cuando se define un parámetro.</span><span class="sxs-lookup"><span data-stu-id="51c08-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="51c08-123">Sin embargo, si utiliza un parámetro un `As` cláusula, todas ellas deben usarlo.</span><span class="sxs-lookup"><span data-stu-id="51c08-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="51c08-124">Si el modificador de comprobación de tipo es `On`, el `As` cláusula es necesaria para cada definición de parámetro.</span><span class="sxs-lookup"><span data-stu-id="51c08-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="51c08-125">Especificar los tipos de datos para todos los elementos de programación se conoce como *establecimiento inflexible de tipos*.</span><span class="sxs-lookup"><span data-stu-id="51c08-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="51c08-126">Al establecer `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] exige el establecimiento inflexible de tipos.</span><span class="sxs-lookup"><span data-stu-id="51c08-126">When you set `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enforces strong typing.</span></span> <span data-ttu-id="51c08-127">Esto se recomienda, por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="51c08-127">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="51c08-128">Habilita la compatibilidad con IntelliSense para las variables y parámetros.</span><span class="sxs-lookup"><span data-stu-id="51c08-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="51c08-129">Esto le permite ver sus propiedades y otros miembros como un tipo en el código.</span><span class="sxs-lookup"><span data-stu-id="51c08-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="51c08-130">Permite al compilador realizar la comprobación de tipos.</span><span class="sxs-lookup"><span data-stu-id="51c08-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="51c08-131">Esto ayuda a detectar las instrucciones que pueden producir un error en tiempo de ejecución debido a errores, como el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="51c08-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="51c08-132">También detecta llamadas a métodos en objetos que no las admiten.</span><span class="sxs-lookup"><span data-stu-id="51c08-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="51c08-133">Se produce una ejecución más rápida del código.</span><span class="sxs-lookup"><span data-stu-id="51c08-133">It results in faster execution of your code.</span></span> <span data-ttu-id="51c08-134">Una razón para esto es que si no especifica un tipo de datos para un elemento de programación, la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador lo asigna el `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="51c08-134">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="51c08-135">El código compilado que sea necesario convertir entre `Object` y otros tipos de datos, lo que reduce el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="51c08-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c08-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="51c08-136">See Also</span></span>  
 [<span data-ttu-id="51c08-137">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="51c08-137">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="51c08-138">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="51c08-138">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="51c08-139">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="51c08-139">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="51c08-140">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="51c08-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="51c08-141">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="51c08-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="51c08-142">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="51c08-142">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="51c08-143">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="51c08-143">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="51c08-144">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="51c08-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="51c08-145">Programación orientada a objetos</span><span class="sxs-lookup"><span data-stu-id="51c08-145">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
