---
title: 'Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)'
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 93d9cc11e919e45fdd3b48dd2731b165f3466640
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="5877b-102">Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5877b-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="5877b-103">Cuando se llama a un procedimiento, cada argumento proporcionado se corresponde a uno de los parámetros definidos en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5877b-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="5877b-104">En algunos casos, el código del procedimiento puede cambiar el valor subyacente a un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="5877b-105">En otros casos, el procedimiento puede cambiar solo su copia local de un argumento.</span><span class="sxs-lookup"><span data-stu-id="5877b-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="5877b-106">Cuando se llama al procedimiento, Visual Basic realiza una copia local de cada argumento que se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="5877b-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="5877b-107">Para cada argumento pasado [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona el código del procedimiento una referencia directa al elemento de programación subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="5877b-108">Si el elemento subyacente en el código de llamada es un elemento modificable y el argumento se pasa `ByRef`, el código del procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="5877b-109">Cambiar el valor subyacente</span><span class="sxs-lookup"><span data-stu-id="5877b-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="5877b-110">Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada</span><span class="sxs-lookup"><span data-stu-id="5877b-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="5877b-111">En la declaración de procedimiento, especifique [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.</span><span class="sxs-lookup"><span data-stu-id="5877b-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="5877b-112">En el código que realiza la llamada, pasar un elemento de programación modificable como argumento.</span><span class="sxs-lookup"><span data-stu-id="5877b-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="5877b-113">En el código que realiza la llamada, no incluya el argumento entre paréntesis en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="5877b-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="5877b-114">En el código de procedimiento, utilice el nombre de parámetro para asignar un valor al elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="5877b-115">Vea el ejemplo más abajo para ver una demostración.</span><span class="sxs-lookup"><span data-stu-id="5877b-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="5877b-116">Cambiar las copias locales</span><span class="sxs-lookup"><span data-stu-id="5877b-116">Changing Local Copies</span></span>  
 <span data-ttu-id="5877b-117">Si el elemento subyacente en el código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal`, el procedimiento no puede cambiar su valor en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="5877b-118">Sin embargo, el procedimiento puede cambiar su copia local de dicho argumento.</span><span class="sxs-lookup"><span data-stu-id="5877b-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="5877b-119">Para cambiar la copia de un argumento de procedimiento en el código de procedimiento</span><span class="sxs-lookup"><span data-stu-id="5877b-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="5877b-120">En la declaración de procedimiento, especifique [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.</span><span class="sxs-lookup"><span data-stu-id="5877b-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="5877b-121">-o bien-</span><span class="sxs-lookup"><span data-stu-id="5877b-121">-or-</span></span>  
  
     <span data-ttu-id="5877b-122">En el código que realiza la llamada, incluya el argumento entre paréntesis en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="5877b-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="5877b-123">Esto obligará a Visual Basic para pasar el argumento por valor, incluso si el parámetro correspondiente especifica `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="5877b-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="5877b-124">En el código de procedimiento, utilice el nombre de parámetro para asignar un valor a la copia local del argumento.</span><span class="sxs-lookup"><span data-stu-id="5877b-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="5877b-125">No se cambia el valor subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5877b-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5877b-126">Example</span></span>  
 <span data-ttu-id="5877b-127">En el ejemplo siguiente se muestra dos procedimientos que toman una variable de matriz y operan con sus elementos.</span><span class="sxs-lookup"><span data-stu-id="5877b-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="5877b-128">El `increase` procedimiento simplemente agrega una unidad a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="5877b-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="5877b-129">El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="5877b-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="5877b-130">La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="5877b-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="5877b-131">Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo para pasar argumentos `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="5877b-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="5877b-132">El segundo `MsgBox` llamada a muestra "después Replace (n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="5877b-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="5877b-133">Dado que `n` se pasa `ByRef`, `replace` puede modificar la variable `n` en el código que realiza la llamada y asignar una nueva matriz a él.</span><span class="sxs-lookup"><span data-stu-id="5877b-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="5877b-134">Dado que `n` es un tipo de referencia, `replace` también se puede cambiar sus miembros.</span><span class="sxs-lookup"><span data-stu-id="5877b-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="5877b-135">Puede impedir que el procedimiento modificar la variable en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="5877b-136">Vea [Cómo: proteger un argumento de procedimiento no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="5877b-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5877b-137">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5877b-137">Compiling the Code</span></span>  
 <span data-ttu-id="5877b-138">Cuando se pasa una variable por referencia, debe utilizar el `ByRef` palabra clave para especificar este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="5877b-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="5877b-139">El valor predeterminado en Visual Basic es pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="5877b-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="5877b-140">Sin embargo, resulta recomienda incluir la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="5877b-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="5877b-141">Esto hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="5877b-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5877b-142">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5877b-142">.NET Framework Security</span></span>  
 <span data-ttu-id="5877b-143">Siempre es un riesgo potencial al permitir a un procedimiento cambiar el valor subyacente a un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5877b-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="5877b-144">Asegúrese de que se espera que este valor puede cambiar, y estar preparado para comprobar su validez antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="5877b-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5877b-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="5877b-145">See Also</span></span>  
 [<span data-ttu-id="5877b-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="5877b-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="5877b-147">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="5877b-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="5877b-148">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="5877b-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="5877b-149">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="5877b-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="5877b-150">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="5877b-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="5877b-151">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="5877b-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="5877b-152">Proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="5877b-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="5877b-153">Forzar un argumento para que pase como un valor</span><span class="sxs-lookup"><span data-stu-id="5877b-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="5877b-154">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="5877b-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="5877b-155">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="5877b-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
