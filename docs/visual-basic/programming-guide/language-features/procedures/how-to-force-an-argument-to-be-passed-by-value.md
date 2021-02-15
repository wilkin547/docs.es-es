---
description: 'Más información sobre: Cómo forzar que un argumento se pase por valor (Visual Basic)'
title: Procedimiento para forzar un argumento para que pase como un valor
ms.date: 07/20/2015
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
ms.openlocfilehash: 471ddbf8993ad671dc4285729a11f5b17a5b19dc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475427"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="38078-103">Cómo: Forzar un argumento para que pase como un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38078-103">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>

<span data-ttu-id="38078-104">La declaración de procedimiento determina el mecanismo de paso.</span><span class="sxs-lookup"><span data-stu-id="38078-104">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="38078-105">Si un parámetro se declara como [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic espera pasar el argumento correspondiente por referencia.</span><span class="sxs-lookup"><span data-stu-id="38078-105">If a parameter is declared [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="38078-106">Esto permite al procedimiento cambiar el valor del elemento de programación subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="38078-106">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="38078-107">Si desea proteger el elemento subyacente contra este cambio, puede invalidar el `ByRef` mecanismo de paso en la llamada al procedimiento incluyendo el nombre del argumento entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="38078-107">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="38078-108">Estos paréntesis se suman a los paréntesis que rodean la lista de argumentos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="38078-108">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="38078-109">El código de llamada no puede invalidar un mecanismo [ByVal](../../../language-reference/modifiers/byval.md) .</span><span class="sxs-lookup"><span data-stu-id="38078-109">The calling code cannot override a [ByVal](../../../language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="38078-110">Para forzar que un argumento se pase por valor</span><span class="sxs-lookup"><span data-stu-id="38078-110">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="38078-111">Si el parámetro correspondiente se declara `ByVal` en el procedimiento, no es necesario realizar ningún paso adicional.</span><span class="sxs-lookup"><span data-stu-id="38078-111">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="38078-112">Visual Basic ya espera pasar el argumento por valor.</span><span class="sxs-lookup"><span data-stu-id="38078-112">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="38078-113">Si el parámetro correspondiente se declara `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="38078-113">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38078-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38078-114">Example</span></span>  

 <span data-ttu-id="38078-115">En el ejemplo siguiente se reemplaza una `ByRef` declaración de parámetro.</span><span class="sxs-lookup"><span data-stu-id="38078-115">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="38078-116">En la llamada que fuerza `ByVal` , tenga en cuenta los dos niveles de paréntesis.</span><span class="sxs-lookup"><span data-stu-id="38078-116">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="38078-117">Cuando `str` se incluye entre paréntesis adicionales en la lista de argumentos, el `setNewString` procedimiento no puede cambiar su valor en el código de llamada y `MsgBox` muestra "no se puede reemplazar si se pasa por ByVal".</span><span class="sxs-lookup"><span data-stu-id="38078-117">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="38078-118">Cuando `str` no se incluye entre paréntesis adicionales, el procedimiento puede cambiarlo y `MsgBox` muestra "este es un nuevo valor para el argumento instring".</span><span class="sxs-lookup"><span data-stu-id="38078-118">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="38078-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="38078-119">Compile the code</span></span>  

 <span data-ttu-id="38078-120">Al pasar una variable por referencia, debe usar la `ByRef` palabra clave para especificar este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="38078-120">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="38078-121">De forma predeterminada, en Visual Basic es pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="38078-121">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="38078-122">Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="38078-122">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="38078-123">Esto hace que el código sea más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="38078-123">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="38078-124">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="38078-124">Robust Programming</span></span>  

 <span data-ttu-id="38078-125">Si un procedimiento declara un parámetro [ByRef](../../../language-reference/modifiers/byref.md), la ejecución correcta del código podría depender de poder cambiar el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="38078-125">If a procedure declares a parameter [ByRef](../../../language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="38078-126">Si el código de llamada invalida este mecanismo de llamada incluyendo el argumento entre paréntesis, o si pasa un argumento no modificable, el procedimiento no puede cambiar el elemento subyacente.</span><span class="sxs-lookup"><span data-stu-id="38078-126">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="38078-127">Esto podría producir resultados inesperados en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="38078-127">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="38078-128">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="38078-128">.NET Framework Security</span></span>  

 <span data-ttu-id="38078-129">Siempre existe un riesgo potencial en permitir que un procedimiento cambie el valor subyacente de un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="38078-129">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="38078-130">Asegúrese de que espera que se cambie este valor y prepárese para comprobar su validez antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="38078-130">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38078-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38078-131">See also</span></span>

- [<span data-ttu-id="38078-132">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="38078-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="38078-133">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="38078-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="38078-134">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="38078-134">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="38078-135">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="38078-135">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="38078-136">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="38078-136">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="38078-137">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="38078-137">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="38078-138">Procedimiento para cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="38078-138">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="38078-139">Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="38078-139">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="38078-140">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="38078-140">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="38078-141">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="38078-141">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
