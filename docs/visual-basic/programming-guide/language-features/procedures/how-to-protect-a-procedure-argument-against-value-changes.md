---
title: 'Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59c0486bd9543167e4c17a3109c4b89b3502e80e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="7b9f8-102">Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b9f8-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="7b9f8-103">Si un procedimiento declara un parámetro como [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona el código del procedimiento una referencia directa al elemento de programación subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="7b9f8-104">Esto permite que el procedimiento para cambiar el valor subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="7b9f8-105">En algunos casos, el código de llamada conviene para protegerse frente a este tipo de cambios.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="7b9f8-106">Siempre puede proteger un argumento de cambio al declarar el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="7b9f8-107">Si desea poder cambiar un determinado argumento en algunos casos, pero no otros, puede declararlo `ByRef` y deje que el código que realiza la llamada a determinar el mecanismo de paso en cada llamada.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="7b9f8-108">Para ello, incluya el argumento correspondiente entre paréntesis para pasar por valor o no se incluye entre paréntesis para pasar por referencia.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="7b9f8-109">Para obtener más información, consulte [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="7b9f8-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b9f8-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b9f8-110">Example</span></span>  
 <span data-ttu-id="7b9f8-111">En el ejemplo siguiente se muestra dos procedimientos que toman una variable de matriz y operan con sus elementos.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="7b9f8-112">El `increase` procedimiento simplemente agrega una unidad a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="7b9f8-113">El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="7b9f8-114">Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 <span data-ttu-id="7b9f8-115">La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="7b9f8-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="7b9f8-116">Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo para pasar argumentos `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-116">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="7b9f8-117">El segundo `MsgBox` llamada a muestra "después Replace (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="7b9f8-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="7b9f8-118">Dado que `n` se pasa `ByVal`, `replace` no se puede modificar la variable `n` en el código que realiza la llamada mediante la asignación de una nueva matriz a él.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="7b9f8-119">Cuando `replace` crea la nueva instancia de la matriz `k` y lo asigna a la variable local `a`, pierde la referencia a `n` se pasa por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="7b9f8-120">Cuando cambia los miembros de `a`, solo la matriz local `k` se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="7b9f8-121">Por lo tanto, `replace` no incrementa los valores de matriz `n` en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b9f8-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="7b9f8-122">Compiling the Code</span></span>  
 <span data-ttu-id="7b9f8-123">El valor predeterminado en Visual Basic es pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="7b9f8-124">Sin embargo, resulta recomienda incluir la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="7b9f8-125">Esto hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="7b9f8-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b9f8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b9f8-126">See Also</span></span>  
 [<span data-ttu-id="7b9f8-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7b9f8-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="7b9f8-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="7b9f8-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="7b9f8-129">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="7b9f8-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="7b9f8-130">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="7b9f8-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="7b9f8-131">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="7b9f8-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="7b9f8-132">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="7b9f8-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="7b9f8-133">Cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="7b9f8-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="7b9f8-134">Forzar un argumento para que pase como un valor</span><span class="sxs-lookup"><span data-stu-id="7b9f8-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="7b9f8-135">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="7b9f8-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="7b9f8-136">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="7b9f8-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
