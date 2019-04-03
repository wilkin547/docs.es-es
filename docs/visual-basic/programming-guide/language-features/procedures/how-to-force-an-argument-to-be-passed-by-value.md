---
title: Filtrar Forzar un argumento para pasar por valor (Visual Basic)
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
ms.openlocfilehash: 497ae11b858b7d164ba3b5607ff2109254a154de
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842051"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="a14f8-102">Filtrar Forzar un argumento para pasar por valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a14f8-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="a14f8-103">La declaración de procedimiento determina el mecanismo de paso.</span><span class="sxs-lookup"><span data-stu-id="a14f8-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="a14f8-104">Si se declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), espera que Visual Basic pasar el argumento correspondiente por referencia.</span><span class="sxs-lookup"><span data-stu-id="a14f8-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="a14f8-105">Esto permite que el procedimiento cambiar el valor del elemento de programación subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a14f8-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="a14f8-106">Si desea proteger el elemento subyacente frente a estos cambios, puede invalidar el `ByRef` llame al mecanismo de paso en el procedimiento, incluya entre paréntesis el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="a14f8-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="a14f8-107">Los paréntesis son además de los paréntesis para delimitar la lista de argumentos en la llamada.</span><span class="sxs-lookup"><span data-stu-id="a14f8-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="a14f8-108">El código de llamada no se puede invalidar un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mecanismo.</span><span class="sxs-lookup"><span data-stu-id="a14f8-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="a14f8-109">Para forzar un argumento para pasar por valor</span><span class="sxs-lookup"><span data-stu-id="a14f8-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="a14f8-110">Si se declara el correspondiente parámetro `ByVal` en el procedimiento, es necesario realizar ningún paso adicional.</span><span class="sxs-lookup"><span data-stu-id="a14f8-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="a14f8-111">Ya espera Visual Basic pasar el argumento por valor.</span><span class="sxs-lookup"><span data-stu-id="a14f8-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="a14f8-112">Si se declara el correspondiente parámetro `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a14f8-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a14f8-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a14f8-113">Example</span></span>  
 <span data-ttu-id="a14f8-114">En el ejemplo siguiente se invalida un `ByRef` declaración de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a14f8-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="a14f8-115">En la llamada que obliga a `ByVal`, tenga en cuenta los dos niveles de paréntesis.</span><span class="sxs-lookup"><span data-stu-id="a14f8-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="a14f8-116">Cuando `str` se encierra entre paréntesis adicionales dentro de la lista de argumentos, el `setNewString` procedimiento no puede cambiar su valor en el código que realiza la llamada, y `MsgBox` muestra "No se puede reemplazar si pasa ByVal".</span><span class="sxs-lookup"><span data-stu-id="a14f8-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="a14f8-117">Cuando `str` no está entre paréntesis adicionales, puede cambiar el procedimiento, y `MsgBox` muestra "Es un nuevo valor para el argumento inString".</span><span class="sxs-lookup"><span data-stu-id="a14f8-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a14f8-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a14f8-118">Compiling the Code</span></span>  
 <span data-ttu-id="a14f8-119">Cuando se pasa una variable por referencia, debe usar el `ByRef` palabra clave para especificar este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="a14f8-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="a14f8-120">El valor predeterminado en Visual Basic consiste en pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="a14f8-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="a14f8-121">Sin embargo, es buena práctica para incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="a14f8-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="a14f8-122">Esto hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="a14f8-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a14f8-123">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a14f8-123">Robust Programming</span></span>  
 <span data-ttu-id="a14f8-124">Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la ejecución correcta del código podría depender poder cambiar el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a14f8-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="a14f8-125">Si el código de llamada reemplaza este mecanismo de llamada, incluya el argumento entre paréntesis, o si pasa un argumento, el procedimiento no puede cambiar el elemento subyacente.</span><span class="sxs-lookup"><span data-stu-id="a14f8-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="a14f8-126">Esto podría producir resultados inesperados en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a14f8-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a14f8-127">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a14f8-127">.NET Framework Security</span></span>  
 <span data-ttu-id="a14f8-128">Siempre hay un riesgo potencial de permitir que un procedimiento cambiar el valor subyacente a un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a14f8-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="a14f8-129">Asegúrese de que se espera que este valor se puede cambiar, y estar preparado para comprobar su validez antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="a14f8-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14f8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a14f8-130">See also</span></span>

- [<span data-ttu-id="a14f8-131">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="a14f8-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a14f8-132">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="a14f8-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a14f8-133">Cómo: Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="a14f8-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="a14f8-134">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="a14f8-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="a14f8-135">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="a14f8-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="a14f8-136">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="a14f8-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="a14f8-137">Cómo: Cambie el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="a14f8-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="a14f8-138">Cómo: Proteger un argumento de procedimiento contra cambios de valor</span><span class="sxs-lookup"><span data-stu-id="a14f8-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="a14f8-139">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="a14f8-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="a14f8-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="a14f8-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
