---
title: Lista de parámetros (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 7c5f6fa4015c90802cdd48d3a70f06f56c926c7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662288"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="89534-102">Lista de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89534-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="89534-103">Especifica los parámetros que se espera que un procedimiento cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="89534-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="89534-104">Varios parámetros están separados por comas.</span><span class="sxs-lookup"><span data-stu-id="89534-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="89534-105">La siguiente es la sintaxis para un parámetro.</span><span class="sxs-lookup"><span data-stu-id="89534-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89534-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89534-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="89534-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="89534-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="89534-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="89534-108">Optional.</span></span> <span data-ttu-id="89534-109">Lista de atributos que se aplican a este parámetro.</span><span class="sxs-lookup"><span data-stu-id="89534-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="89534-110">Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").</span><span class="sxs-lookup"><span data-stu-id="89534-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="89534-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="89534-111">Optional.</span></span> <span data-ttu-id="89534-112">Especifica que este parámetro no es necesario cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="89534-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="89534-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="89534-113">Optional.</span></span> <span data-ttu-id="89534-114">Especifica que el procedimiento no se puede reemplazar o volver a asignar el elemento de variable subyacente del argumento correspondiente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="89534-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="89534-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="89534-115">Optional.</span></span> <span data-ttu-id="89534-116">Especifica que el procedimiento puede modificar la variable subyacente en el código de llamada del mismo modo que el propio código de llamada.</span><span class="sxs-lookup"><span data-stu-id="89534-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="89534-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="89534-117">Optional.</span></span> <span data-ttu-id="89534-118">Especifica que el último parámetro en la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="89534-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="89534-119">Esto permite que el código que realiza la llamada pasar un número arbitrario de argumentos al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="89534-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="89534-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="89534-120">Required.</span></span> <span data-ttu-id="89534-121">Nombre de la variable local que representa el parámetro.</span><span class="sxs-lookup"><span data-stu-id="89534-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="89534-122">Es necesario si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="89534-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="89534-123">Tipo de datos de la variable local que representa el parámetro.</span><span class="sxs-lookup"><span data-stu-id="89534-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="89534-124">Necesario para `Optional` parámetros.</span><span class="sxs-lookup"><span data-stu-id="89534-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="89534-125">Cualquier constante o expresión constante que se evalúa como el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="89534-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="89534-126">Si el tipo es `Object`, o una clase, interfaz, matriz o estructura, el valor predeterminado solo puede ser `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="89534-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89534-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89534-127">Remarks</span></span>  
 <span data-ttu-id="89534-128">Parámetros entre paréntesis y separados por comas.</span><span class="sxs-lookup"><span data-stu-id="89534-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="89534-129">Un parámetro se puede declarar con cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="89534-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="89534-130">Si no especifica `parametertype`, el valor predeterminado es `Object`.</span><span class="sxs-lookup"><span data-stu-id="89534-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="89534-131">Cuando el código de llamada llama al procedimiento, pasa un *argumento* para cada parámetro obligatorio.</span><span class="sxs-lookup"><span data-stu-id="89534-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="89534-132">Para obtener más información, consulte [diferencias entre parámetros y argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="89534-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="89534-133">El argumento que el código que realiza la llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="89534-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="89534-134">Si este elemento es *no modificable* (una constante, literal, enumeración o expresión), es imposible que cualquier código que cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="89534-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="89534-135">Si es un *variable* elemento (una variable declarada, campo, propiedad, elemento de matriz o elemento de estructura), puede cambiar el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="89534-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="89534-136">Para obtener más información, consulte [argumentos modificables y las diferencias entre modificable](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="89534-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="89534-137">Si se pasa un elemento de la variable `ByRef`, el procedimiento puede cambiar también.</span><span class="sxs-lookup"><span data-stu-id="89534-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="89534-138">Para obtener más información, consulte [las diferencias entre pasar un argumento por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="89534-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="89534-139">Reglas</span><span class="sxs-lookup"><span data-stu-id="89534-139">Rules</span></span>  
  
-   <span data-ttu-id="89534-140">**Paréntesis.**</span><span class="sxs-lookup"><span data-stu-id="89534-140">**Parentheses.**</span></span> <span data-ttu-id="89534-141">Si especifica una lista de parámetros, debe encerrarlo entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="89534-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="89534-142">Si no hay ningún parámetro, todavía puede usar paréntesis para delimitar una lista vacía.</span><span class="sxs-lookup"><span data-stu-id="89534-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="89534-143">Esto mejora la legibilidad del código aclarar que el elemento es un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="89534-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="89534-144">**Parámetros opcionales.**</span><span class="sxs-lookup"><span data-stu-id="89534-144">**Optional Parameters.**</span></span> <span data-ttu-id="89534-145">Si usas el `Optional` modificador en un parámetro, todos los parámetros posteriores en la lista también deben ser opcionales y declarados mediante el `Optional` modificador.</span><span class="sxs-lookup"><span data-stu-id="89534-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="89534-146">Cada declaración de parámetro opcional debe proporcionar el `defaultvalue` cláusula.</span><span class="sxs-lookup"><span data-stu-id="89534-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="89534-147">Para obtener más información, consulte [parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="89534-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="89534-148">**Matrices de parámetros.**</span><span class="sxs-lookup"><span data-stu-id="89534-148">**Parameter Arrays.**</span></span> <span data-ttu-id="89534-149">Debe especificar `ByVal` para un `ParamArray` parámetro.</span><span class="sxs-lookup"><span data-stu-id="89534-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="89534-150">No se puede usar ambos `Optional` y `ParamArray` en la misma lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="89534-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="89534-151">Para obtener más información, consulte [las matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="89534-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="89534-152">**Mecanismo de paso.**</span><span class="sxs-lookup"><span data-stu-id="89534-152">**Passing Mechanism.**</span></span> <span data-ttu-id="89534-153">Es el mecanismo predeterminado para cada argumento `ByVal`, lo que significa que el procedimiento no puede cambiar la variable subyacente.</span><span class="sxs-lookup"><span data-stu-id="89534-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="89534-154">Sin embargo, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, aunque no puede reemplazar o reasignar el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="89534-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="89534-155">**Nombres de parámetro.**</span><span class="sxs-lookup"><span data-stu-id="89534-155">**Parameter Names.**</span></span> <span data-ttu-id="89534-156">Si el tipo de datos del parámetro es una matriz, siga `parametername` inmediatamente mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="89534-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="89534-157">Para obtener más información sobre los nombres de parámetros, vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="89534-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89534-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89534-158">Example</span></span>  
 <span data-ttu-id="89534-159">El ejemplo siguiente se muestra un `Function` procedimiento que define dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="89534-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="89534-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="89534-160">See also</span></span>
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="89534-161">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="89534-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="89534-162">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="89534-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="89534-163">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="89534-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="89534-164">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="89534-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="89534-165">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="89534-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="89534-166">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="89534-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="89534-167">Cómo: Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="89534-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
