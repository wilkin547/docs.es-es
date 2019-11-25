---
title: 'Cómo: Forzar un argumento para que pase como un valor'
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
ms.openlocfilehash: 8261d126f988bdcf05b4a2af3106b38717e46bc8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344516"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="f108c-102">Cómo: Forzar un argumento para que pase como un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f108c-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="f108c-103">The procedure declaration determines the passing mechanism.</span><span class="sxs-lookup"><span data-stu-id="f108c-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="f108c-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span><span class="sxs-lookup"><span data-stu-id="f108c-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="f108c-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span><span class="sxs-lookup"><span data-stu-id="f108c-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="f108c-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span><span class="sxs-lookup"><span data-stu-id="f108c-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="f108c-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span><span class="sxs-lookup"><span data-stu-id="f108c-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="f108c-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span><span class="sxs-lookup"><span data-stu-id="f108c-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="f108c-109">To force an argument to be passed by value</span><span class="sxs-lookup"><span data-stu-id="f108c-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="f108c-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span><span class="sxs-lookup"><span data-stu-id="f108c-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="f108c-111">Visual Basic already expects to pass the argument by value.</span><span class="sxs-lookup"><span data-stu-id="f108c-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="f108c-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span><span class="sxs-lookup"><span data-stu-id="f108c-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f108c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f108c-113">Example</span></span>  
 <span data-ttu-id="f108c-114">The following example overrides a `ByRef` parameter declaration.</span><span class="sxs-lookup"><span data-stu-id="f108c-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="f108c-115">In the call that forces `ByVal`, note the two levels of parentheses.</span><span class="sxs-lookup"><span data-stu-id="f108c-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="f108c-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span><span class="sxs-lookup"><span data-stu-id="f108c-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="f108c-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span><span class="sxs-lookup"><span data-stu-id="f108c-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f108c-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f108c-118">Compiling the Code</span></span>  
 <span data-ttu-id="f108c-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span><span class="sxs-lookup"><span data-stu-id="f108c-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="f108c-120">The default in Visual Basic is to pass arguments by value.</span><span class="sxs-lookup"><span data-stu-id="f108c-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="f108c-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span><span class="sxs-lookup"><span data-stu-id="f108c-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="f108c-122">This makes your code easier to read.</span><span class="sxs-lookup"><span data-stu-id="f108c-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f108c-123">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f108c-123">Robust Programming</span></span>  
 <span data-ttu-id="f108c-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span><span class="sxs-lookup"><span data-stu-id="f108c-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="f108c-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span><span class="sxs-lookup"><span data-stu-id="f108c-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="f108c-126">This might produce unexpected results in the calling code.</span><span class="sxs-lookup"><span data-stu-id="f108c-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f108c-127">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f108c-127">.NET Framework Security</span></span>  
 <span data-ttu-id="f108c-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span><span class="sxs-lookup"><span data-stu-id="f108c-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="f108c-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span><span class="sxs-lookup"><span data-stu-id="f108c-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f108c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f108c-130">See also</span></span>

- [<span data-ttu-id="f108c-131">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f108c-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f108c-132">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="f108c-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f108c-133">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="f108c-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="f108c-134">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="f108c-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="f108c-135">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="f108c-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="f108c-136">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="f108c-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="f108c-137">Cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="f108c-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="f108c-138">Proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="f108c-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="f108c-139">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="f108c-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="f108c-140">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="f108c-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
