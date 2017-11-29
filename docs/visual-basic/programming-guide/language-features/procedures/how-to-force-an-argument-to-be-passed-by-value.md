---
title: "Cómo: Forzar un argumento para que pase como un valor (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdb2df7e114f49c23db9f5b322ca9dd32135ac88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="08c16-102">Cómo: Forzar un argumento para que pase como un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08c16-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="08c16-103">La declaración de procedimiento determina el mecanismo de paso.</span><span class="sxs-lookup"><span data-stu-id="08c16-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="08c16-104">Si se declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] espera pasar el argumento correspondiente por referencia.</span><span class="sxs-lookup"><span data-stu-id="08c16-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="08c16-105">Esto permite que el procedimiento cambiar el valor del elemento de programación subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08c16-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="08c16-106">Si desea proteger el elemento subyacente frente a estos cambios, puede invalidar el `ByRef` llame al mecanismo de paso en el procedimiento, incluya el nombre del argumento paréntesis.</span><span class="sxs-lookup"><span data-stu-id="08c16-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="08c16-107">Estos paréntesis son además de los paréntesis que encierran la lista de argumentos en la llamada.</span><span class="sxs-lookup"><span data-stu-id="08c16-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="08c16-108">El código de llamada no puede reemplazar un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mecanismo.</span><span class="sxs-lookup"><span data-stu-id="08c16-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="08c16-109">Para forzar un argumento para pasar por valor</span><span class="sxs-lookup"><span data-stu-id="08c16-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="08c16-110">Si el parámetro correspondiente está declarado `ByVal` en el procedimiento, no es necesario realizar ningún paso adicional.</span><span class="sxs-lookup"><span data-stu-id="08c16-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="08c16-111">ya tiene previsto pasar el argumento por valor.</span><span class="sxs-lookup"><span data-stu-id="08c16-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="08c16-112">Si el parámetro correspondiente está declarado `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08c16-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c16-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08c16-113">Example</span></span>  
 <span data-ttu-id="08c16-114">El siguiente ejemplo se reemplaza un `ByRef` declaración de parámetro.</span><span class="sxs-lookup"><span data-stu-id="08c16-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="08c16-115">En la llamada que obliga a `ByVal`, tenga en cuenta los dos niveles de paréntesis.</span><span class="sxs-lookup"><span data-stu-id="08c16-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="08c16-116">Cuando `str` se encierra entre paréntesis adicionales dentro de la lista de argumentos, la `setNewString` procedimiento no puede cambiar su valor en el código que realiza la llamada, y `MsgBox` muestra "No se puede reemplazar si pasa ByVal".</span><span class="sxs-lookup"><span data-stu-id="08c16-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="08c16-117">Cuando `str` no se incluye entre paréntesis adicionales, el procedimiento puede cambiar, y `MsgBox` muestra "Es un nuevo valor para el argumento inString".</span><span class="sxs-lookup"><span data-stu-id="08c16-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08c16-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="08c16-118">Compiling the Code</span></span>  
 <span data-ttu-id="08c16-119">Cuando se pasa una variable por referencia, debe utilizar el `ByRef` palabra clave para especificar este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="08c16-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="08c16-120">El valor predeterminado en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] consiste en pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="08c16-120">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="08c16-121">Sin embargo, resulta recomienda incluir la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="08c16-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="08c16-122">Esto hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="08c16-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="08c16-123">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="08c16-123">Robust Programming</span></span>  
 <span data-ttu-id="08c16-124">Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la correcta ejecución del código puede depender poder cambiar el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08c16-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="08c16-125">Si el código que realiza la llamada pasa por alto este mecanismo de llamada encerrando el argumento entre paréntesis, o si se pasa un argumento no modificable, el procedimiento no puede cambiar el elemento subyacente.</span><span class="sxs-lookup"><span data-stu-id="08c16-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="08c16-126">Esto podría producir resultados inesperados en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08c16-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="08c16-127">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="08c16-127">.NET Framework Security</span></span>  
 <span data-ttu-id="08c16-128">Siempre es un riesgo potencial al permitir a un procedimiento cambiar el valor subyacente a un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08c16-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="08c16-129">Asegúrese de que se espera que este valor puede cambiar, y estar preparado para comprobar su validez antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="08c16-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c16-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="08c16-130">See Also</span></span>  
 [<span data-ttu-id="08c16-131">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="08c16-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="08c16-132">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="08c16-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="08c16-133">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="08c16-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="08c16-134">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="08c16-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="08c16-135">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="08c16-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="08c16-136">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="08c16-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="08c16-137">Cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="08c16-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="08c16-138">Proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="08c16-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="08c16-139">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="08c16-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="08c16-140">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="08c16-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
