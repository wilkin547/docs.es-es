---
title: Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor
ms.date: 07/20/2015
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
ms.openlocfilehash: 84eadf3d364b69120221d80e464b1175b1602e13
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071487"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="01930-102">Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01930-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>

<span data-ttu-id="01930-103">Si un procedimiento declara un parámetro como [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic proporciona al código de procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="01930-103">If a procedure declares a parameter as [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="01930-104">Esto permite al procedimiento cambiar el valor subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="01930-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="01930-105">En algunos casos, es posible que el código de llamada desee proteger contra este tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="01930-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="01930-106">Siempre puede proteger un argumento del cambio declarando el parámetro correspondiente [ByVal](../../../language-reference/modifiers/byval.md) en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01930-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="01930-107">Si desea poder cambiar un argumento determinado en algunos casos, pero no en otros, puede declararlo `ByRef` y permitir que el código de llamada determine el mecanismo de paso en cada llamada.</span><span class="sxs-lookup"><span data-stu-id="01930-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="01930-108">Para ello, incluye el argumento correspondiente entre paréntesis para pasarlo por valor o no lo incluye entre paréntesis para pasarlo por referencia.</span><span class="sxs-lookup"><span data-stu-id="01930-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="01930-109">Para obtener más información, vea [Cómo: forzar un argumento para que se pase por valor](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="01930-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01930-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01930-110">Example</span></span>  

 <span data-ttu-id="01930-111">En el ejemplo siguiente se muestran dos procedimientos que toman una variable de matriz y operan en sus elementos.</span><span class="sxs-lookup"><span data-stu-id="01930-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="01930-112">El `increase` procedimiento simplemente agrega uno a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="01930-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="01930-113">El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="01930-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="01930-114">Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="01930-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="01930-115">La primera `MsgBox` llamada muestra "después del aumento (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="01930-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="01930-116">Dado que la matriz `n` es un tipo de referencia, `increase` puede cambiar sus miembros, aunque el mecanismo de paso sea `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="01930-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="01930-117">La segunda `MsgBox` llamada muestra "After Replace (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="01930-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="01930-118">Dado `n` que se pasa `ByVal` , `replace` no se puede modificar la variable `n` en el código de llamada mediante la asignación de una nueva matriz a ella.</span><span class="sxs-lookup"><span data-stu-id="01930-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="01930-119">Cuando `replace` crea la nueva instancia de la matriz `k` y la asigna a la variable local `a` , pierde la referencia a `n` pasada por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="01930-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="01930-120">Cuando cambia los miembros de `a` , solo `k` se ve afectada la matriz local.</span><span class="sxs-lookup"><span data-stu-id="01930-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="01930-121">Por lo tanto, no `replace` incrementa los valores de array `n` en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="01930-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="01930-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="01930-122">Compile the code</span></span>  

 <span data-ttu-id="01930-123">De forma predeterminada, en Visual Basic es pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="01930-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="01930-124">Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="01930-124">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="01930-125">Esto hace que el código sea más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="01930-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01930-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="01930-126">See also</span></span>

- [<span data-ttu-id="01930-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="01930-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="01930-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="01930-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="01930-129">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="01930-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="01930-130">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="01930-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="01930-131">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="01930-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="01930-132">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="01930-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="01930-133">Procedimiento para cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="01930-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="01930-134">Procedimiento para forzar un argumento para que pase como un valor</span><span class="sxs-lookup"><span data-stu-id="01930-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="01930-135">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="01930-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="01930-136">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="01930-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
