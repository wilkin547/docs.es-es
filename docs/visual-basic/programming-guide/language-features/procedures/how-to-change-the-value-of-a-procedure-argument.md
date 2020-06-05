---
title: Procedimiento para cambiar el valor de un argumento de procedimiento
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 46cf9062d01e248b6e90882a923a48210780f7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388509"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="4cb66-102">Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb66-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="4cb66-103">Cuando se llama a un procedimiento, cada argumento proporcionado corresponde a uno de los parámetros definidos en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="4cb66-104">En algunos casos, el código de procedimiento puede cambiar el valor subyacente de un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="4cb66-105">En otros casos, el procedimiento solo puede cambiar su copia local de un argumento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="4cb66-106">Cuando se llama al procedimiento, Visual Basic crea una copia local de todos los argumentos que se pasan por [ByVal](../../../language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="4cb66-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="4cb66-107">Para cada argumento pasado [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic proporciona al código de procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-107">For each argument passed [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="4cb66-108">Si el elemento subyacente del código de llamada es un elemento modificable y se pasa el argumento `ByRef` , el código de procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="4cb66-109">Cambiar el valor subyacente</span><span class="sxs-lookup"><span data-stu-id="4cb66-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="4cb66-110">Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada</span><span class="sxs-lookup"><span data-stu-id="4cb66-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="4cb66-111">En la declaración de procedimiento, especifique [ByRef](../../../language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-111">In the procedure declaration, specify [ByRef](../../../language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="4cb66-112">En el código de llamada, pase un elemento de programación modificable como argumento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="4cb66-113">En el código de llamada, no incluya el argumento entre paréntesis en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4cb66-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="4cb66-114">En el código de procedimiento, use el nombre de parámetro para asignar un valor al elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="4cb66-115">Vea el ejemplo más adelante para obtener una demostración.</span><span class="sxs-lookup"><span data-stu-id="4cb66-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="4cb66-116">Cambiar copias locales</span><span class="sxs-lookup"><span data-stu-id="4cb66-116">Changing Local Copies</span></span>  
 <span data-ttu-id="4cb66-117">Si el elemento subyacente del código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal` , el procedimiento no puede cambiar su valor en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="4cb66-118">Sin embargo, el procedimiento puede cambiar su copia local de este tipo de argumento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="4cb66-119">Para cambiar la copia de un argumento de procedimiento en el código de procedimiento</span><span class="sxs-lookup"><span data-stu-id="4cb66-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="4cb66-120">En la declaración de procedimiento, especifique [ByVal](../../../language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-120">In the procedure declaration, specify [ByVal](../../../language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="4cb66-121">O bien</span><span class="sxs-lookup"><span data-stu-id="4cb66-121">-or-</span></span>  
  
     <span data-ttu-id="4cb66-122">En el código de llamada, incluya el argumento entre paréntesis en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4cb66-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="4cb66-123">Esto obliga a Visual Basic a pasar el argumento por valor, incluso si el parámetro correspondiente especifica `ByRef` .</span><span class="sxs-lookup"><span data-stu-id="4cb66-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="4cb66-124">En el código del procedimiento, use el nombre del parámetro para asignar un valor a la copia local del argumento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="4cb66-125">No se cambia el valor subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cb66-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cb66-126">Example</span></span>  
 <span data-ttu-id="4cb66-127">En el ejemplo siguiente se muestran dos procedimientos que toman una variable de matriz y operan en sus elementos.</span><span class="sxs-lookup"><span data-stu-id="4cb66-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="4cb66-128">El `increase` procedimiento simplemente agrega uno a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="4cb66-129">El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="4cb66-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="4cb66-130">La primera `MsgBox` llamada muestra "después del aumento (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="4cb66-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="4cb66-131">Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque el mecanismo de paso sea `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="4cb66-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="4cb66-132">La segunda `MsgBox` llamada muestra "After Replace (n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="4cb66-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="4cb66-133">Dado `n` que se pasa `ByRef` , `replace` puede modificar la variable `n` en el código de llamada y asignarle una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="4cb66-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="4cb66-134">Dado `n` que es un tipo de referencia, `replace` también puede cambiar sus miembros.</span><span class="sxs-lookup"><span data-stu-id="4cb66-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="4cb66-135">Puede evitar que el procedimiento modifique la variable en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="4cb66-136">Consulte [Cómo: proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="4cb66-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="4cb66-137">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4cb66-137">Compile the code</span></span>  
 <span data-ttu-id="4cb66-138">Al pasar una variable por referencia, debe usar la `ByRef` palabra clave para especificar este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="4cb66-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="4cb66-139">De forma predeterminada, en Visual Basic es pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="4cb66-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="4cb66-140">Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con cada parámetro declarado.</span><span class="sxs-lookup"><span data-stu-id="4cb66-140">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="4cb66-141">Esto hace que el código sea más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="4cb66-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4cb66-142">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4cb66-142">.NET Framework Security</span></span>  
 <span data-ttu-id="4cb66-143">Siempre existe un riesgo potencial en permitir que un procedimiento cambie el valor subyacente de un argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cb66-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="4cb66-144">Asegúrese de que espera que se cambie este valor y prepárese para comprobar su validez antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="4cb66-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb66-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cb66-145">See also</span></span>

- [<span data-ttu-id="4cb66-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4cb66-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4cb66-147">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="4cb66-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4cb66-148">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="4cb66-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4cb66-149">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="4cb66-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4cb66-150">Diferencias entre argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="4cb66-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="4cb66-151">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="4cb66-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="4cb66-152">Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="4cb66-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="4cb66-153">Procedimiento para forzar un argumento para que pase como un valor</span><span class="sxs-lookup"><span data-stu-id="4cb66-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="4cb66-154">Pasar argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="4cb66-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="4cb66-155">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="4cb66-155">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
