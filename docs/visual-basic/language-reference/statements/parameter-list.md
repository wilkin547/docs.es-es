---
title: Lista de parámetros
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
ms.openlocfilehash: 706fc2414806db5608cce410bf4156839ec2d83e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404322"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="08650-102">Lista de parámetros (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08650-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="08650-103">Especifica los parámetros que un procedimiento espera cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="08650-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="08650-104">Varios parámetros se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="08650-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="08650-105">A continuación se encuentra la sintaxis de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="08650-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="08650-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08650-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="08650-107">Partes</span><span class="sxs-lookup"><span data-stu-id="08650-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="08650-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="08650-108">Optional.</span></span> <span data-ttu-id="08650-109">Lista de atributos que se aplican a este parámetro.</span><span class="sxs-lookup"><span data-stu-id="08650-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="08650-110">Debe incluir la [lista de atributos](attribute-list.md) entre corchetes angulares (" `<` " y " `>` ").</span><span class="sxs-lookup"><span data-stu-id="08650-110">You must enclose the [Attribute List](attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="08650-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="08650-111">Optional.</span></span> <span data-ttu-id="08650-112">Especifica que este parámetro no es necesario cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08650-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="08650-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="08650-113">Optional.</span></span> <span data-ttu-id="08650-114">Especifica que el procedimiento no puede reemplazar o volver a asignar el elemento variable subyacente al argumento correspondiente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08650-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="08650-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="08650-115">Optional.</span></span> <span data-ttu-id="08650-116">Especifica que el procedimiento puede modificar el elemento variable subyacente en el código de llamada de la misma manera que el propio código de llamada puede.</span><span class="sxs-lookup"><span data-stu-id="08650-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="08650-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="08650-117">Optional.</span></span> <span data-ttu-id="08650-118">Especifica que el último parámetro de la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="08650-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="08650-119">Esto permite al código de llamada pasar un número arbitrario de argumentos al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08650-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="08650-120">Necesario.</span><span class="sxs-lookup"><span data-stu-id="08650-120">Required.</span></span> <span data-ttu-id="08650-121">Nombre de la variable local que representa el parámetro.</span><span class="sxs-lookup"><span data-stu-id="08650-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="08650-122">Obligatorio si `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="08650-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="08650-123">Tipo de datos de la variable local que representa el parámetro.</span><span class="sxs-lookup"><span data-stu-id="08650-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="08650-124">Obligatorio para `Optional` los parámetros.</span><span class="sxs-lookup"><span data-stu-id="08650-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="08650-125">Cualquier expresión constante o constante que se evalúe como el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="08650-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="08650-126">Si el tipo es `Object` , o una clase, interfaz, matriz o estructura, el valor predeterminado solo puede ser `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="08650-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="08650-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="08650-127">Remarks</span></span>

<span data-ttu-id="08650-128">Los parámetros se incluyen entre paréntesis y se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="08650-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="08650-129">Un parámetro se puede declarar con cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="08650-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="08650-130">Si no especifica, el `parametertype` valor predeterminado es `Object` .</span><span class="sxs-lookup"><span data-stu-id="08650-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="08650-131">Cuando el código de llamada llama al procedimiento, pasa un *argumento* a cada parámetro necesario.</span><span class="sxs-lookup"><span data-stu-id="08650-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="08650-132">Para obtener más información, vea [diferencias entre parámetros y argumentos](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="08650-132">For more information, see [Differences Between Parameters and Arguments](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="08650-133">El argumento que el código de llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08650-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="08650-134">Si este elemento no es *variable* (una constante, un literal, una enumeración o una expresión), es imposible que cualquier código lo cambie.</span><span class="sxs-lookup"><span data-stu-id="08650-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="08650-135">Si es un elemento *variable* (una variable declarada, un campo, una propiedad, un elemento de matriz o un elemento de estructura), el código de llamada puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="08650-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="08650-136">Para obtener más información, vea [diferencias entre argumentos modificables y no modificables](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="08650-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="08650-137">Si se pasa un elemento variable `ByRef` , el procedimiento también lo puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="08650-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="08650-138">Para obtener más información, vea [diferencias entre pasar un argumento por valor y por referencia](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="08650-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="08650-139">Reglas</span><span class="sxs-lookup"><span data-stu-id="08650-139">Rules</span></span>

- <span data-ttu-id="08650-140">**Paréntesis.**</span><span class="sxs-lookup"><span data-stu-id="08650-140">**Parentheses.**</span></span> <span data-ttu-id="08650-141">Si especifica una lista de parámetros, debe escribirla entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="08650-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="08650-142">Si no hay ningún parámetro, todavía puede usar paréntesis que incluyan una lista vacía.</span><span class="sxs-lookup"><span data-stu-id="08650-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="08650-143">Esto mejora la legibilidad del código al aclarar que el elemento es un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08650-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="08650-144">**Parámetros opcionales.**</span><span class="sxs-lookup"><span data-stu-id="08650-144">**Optional Parameters.**</span></span> <span data-ttu-id="08650-145">Si utiliza el `Optional` modificador en un parámetro, todos los parámetros subsiguientes de la lista también deben ser opcionales y declararse mediante el `Optional` modificador.</span><span class="sxs-lookup"><span data-stu-id="08650-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="08650-146">Cada declaración de parámetro opcional debe proporcionar la `defaultvalue` cláusula.</span><span class="sxs-lookup"><span data-stu-id="08650-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="08650-147">Para obtener más información, vea [parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="08650-147">For more information, see [Optional Parameters](../../programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="08650-148">**Matrices de parámetros.**</span><span class="sxs-lookup"><span data-stu-id="08650-148">**Parameter Arrays.**</span></span> <span data-ttu-id="08650-149">Debe especificar `ByVal` para un `ParamArray` parámetro.</span><span class="sxs-lookup"><span data-stu-id="08650-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="08650-150">No puede utilizar `Optional` y `ParamArray` en la misma lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="08650-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="08650-151">Para obtener más información, consulte [matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="08650-151">For more information, see [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="08650-152">**Pasando el mecanismo.**</span><span class="sxs-lookup"><span data-stu-id="08650-152">**Passing Mechanism.**</span></span> <span data-ttu-id="08650-153">El mecanismo predeterminado para cada argumento es `ByVal` , lo que significa que el procedimiento no puede cambiar el elemento variable subyacente.</span><span class="sxs-lookup"><span data-stu-id="08650-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="08650-154">Sin embargo, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, aunque no puede reemplazar o volver a asignar el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="08650-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="08650-155">**Nombres de parámetro.**</span><span class="sxs-lookup"><span data-stu-id="08650-155">**Parameter Names.**</span></span> <span data-ttu-id="08650-156">Si el tipo de datos del parámetro es una matriz, siga `parametername` inmediatamente entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="08650-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="08650-157">Para obtener más información sobre los nombres de parámetros, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="08650-157">For more information on parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="08650-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08650-158">Example</span></span>

<span data-ttu-id="08650-159">En el ejemplo siguiente se muestra un `Function` procedimiento que define dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="08650-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="08650-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08650-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="08650-161">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="08650-161">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="08650-162">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="08650-162">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="08650-163">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="08650-163">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="08650-164">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="08650-164">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="08650-165">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="08650-165">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="08650-166">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="08650-166">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="08650-167">Procedimiento Interrupción y combinación de instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="08650-167">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
