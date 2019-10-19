---
title: Operator (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: c4fae40992fa665121aff637ae427ef0cafbf547
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582383"
---
# <a name="operator-statement"></a><span data-ttu-id="6f654-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="6f654-102">Operator Statement</span></span>

<span data-ttu-id="6f654-103">Declara el símbolo del operador, los operandos y el código que definen un procedimiento de operador en una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="6f654-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f654-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f654-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="6f654-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6f654-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="6f654-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f654-106">Optional.</span></span> <span data-ttu-id="6f654-107">Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="6f654-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="6f654-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-108">Required.</span></span> <span data-ttu-id="6f654-109">Indica que este procedimiento de operador tiene acceso [público](../../../visual-basic/language-reference/modifiers/public.md) .</span><span class="sxs-lookup"><span data-stu-id="6f654-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="6f654-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f654-110">Optional.</span></span> <span data-ttu-id="6f654-111">Vea [sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="6f654-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="6f654-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-112">Required.</span></span> <span data-ttu-id="6f654-113">Indica que este procedimiento de operador es un procedimiento [compartido](../../../visual-basic/language-reference/modifiers/shared.md) .</span><span class="sxs-lookup"><span data-stu-id="6f654-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="6f654-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f654-114">Optional.</span></span> <span data-ttu-id="6f654-115">Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="6f654-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="6f654-116">Obligatorio para un operador de conversión a menos que especifique `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="6f654-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="6f654-117">Indica que este procedimiento de operador define una conversión de [ampliación](../../../visual-basic/language-reference/modifiers/widening.md) .</span><span class="sxs-lookup"><span data-stu-id="6f654-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="6f654-118">Vea "conversiones de ampliación y de restricción" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="6f654-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="6f654-119">Obligatorio para un operador de conversión a menos que especifique `Widening`.</span><span class="sxs-lookup"><span data-stu-id="6f654-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="6f654-120">Indica que este procedimiento de operador define una conversión de [restricción](../../../visual-basic/language-reference/modifiers/narrowing.md) .</span><span class="sxs-lookup"><span data-stu-id="6f654-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="6f654-121">Vea "conversiones de ampliación y de restricción" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="6f654-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="6f654-122">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-122">Required.</span></span> <span data-ttu-id="6f654-123">Símbolo o identificador del operador que define este procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="6f654-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="6f654-124">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-124">Required.</span></span> <span data-ttu-id="6f654-125">El nombre y el tipo del operando único de un operador unario (incluido un operador de conversión) o el operando izquierdo de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="6f654-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="6f654-126">Requerido para los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="6f654-126">Required for binary operators.</span></span> <span data-ttu-id="6f654-127">Nombre y tipo del operando derecho de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="6f654-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="6f654-128">`operand1` y `operand2` tienen la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f654-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="6f654-129">Parte</span><span class="sxs-lookup"><span data-stu-id="6f654-129">Part</span></span>|<span data-ttu-id="6f654-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f654-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="6f654-131">Opcional, pero el mecanismo de paso debe ser [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="6f654-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="6f654-132">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-132">Required.</span></span> <span data-ttu-id="6f654-133">Nombre de la variable que representa este operando.</span><span class="sxs-lookup"><span data-stu-id="6f654-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="6f654-134">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="6f654-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="6f654-135">Opcional a menos que se `On` `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="6f654-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="6f654-136">Tipo de datos de este operando.</span><span class="sxs-lookup"><span data-stu-id="6f654-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="6f654-137">Opcional a menos que se `On` `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="6f654-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="6f654-138">Tipo de datos del valor que el procedimiento del operador devuelve.</span><span class="sxs-lookup"><span data-stu-id="6f654-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="6f654-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f654-139">Optional.</span></span> <span data-ttu-id="6f654-140">Bloque de instrucciones que ejecuta el procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="6f654-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="6f654-141">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-141">Required.</span></span> <span data-ttu-id="6f654-142">Valor que el procedimiento del operador devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="6f654-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="6f654-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="6f654-143">`End` `Operator`</span></span>  
<span data-ttu-id="6f654-144">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6f654-144">Required.</span></span> <span data-ttu-id="6f654-145">Finaliza la definición de este procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="6f654-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f654-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f654-146">Remarks</span></span>

<span data-ttu-id="6f654-147">Solo se puede usar `Operator` en una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="6f654-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="6f654-148">Esto significa que el contexto de la *declaración* de un operador no puede ser un archivo de código fuente, un espacio de nombres, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="6f654-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="6f654-149">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="6f654-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="6f654-150">Todos los operadores deben ser `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="6f654-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="6f654-151">No se puede especificar `ByRef`, `Optional` o `ParamArray` para ninguno de los operandos.</span><span class="sxs-lookup"><span data-stu-id="6f654-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="6f654-152">No se puede utilizar el símbolo de operador o el identificador para contener un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6f654-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="6f654-153">Debe utilizar la instrucción `Return` y debe especificar un valor.</span><span class="sxs-lookup"><span data-stu-id="6f654-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="6f654-154">Cualquier número de instrucciones `Return` puede aparecer en cualquier parte del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6f654-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="6f654-155">La definición de un operador de este modo se denomina *sobrecarga de operadores*, tanto si se usa la palabra clave `Overloads` como si no.</span><span class="sxs-lookup"><span data-stu-id="6f654-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="6f654-156">En la tabla siguiente se enumeran los operadores que se pueden definir.</span><span class="sxs-lookup"><span data-stu-id="6f654-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="6f654-157">Type</span><span class="sxs-lookup"><span data-stu-id="6f654-157">Type</span></span>|<span data-ttu-id="6f654-158">Operadores</span><span class="sxs-lookup"><span data-stu-id="6f654-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="6f654-159">Unario</span><span class="sxs-lookup"><span data-stu-id="6f654-159">Unary</span></span>|<span data-ttu-id="6f654-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="6f654-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="6f654-161">Binary</span><span class="sxs-lookup"><span data-stu-id="6f654-161">Binary</span></span>|<span data-ttu-id="6f654-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="6f654-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="6f654-163">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="6f654-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="6f654-164">Tenga en cuenta que el operador `=` de la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="6f654-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="6f654-165">Al definir `CType`, debe especificar `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="6f654-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="6f654-166">Pares coincidentes</span><span class="sxs-lookup"><span data-stu-id="6f654-166">Matched Pairs</span></span>

<span data-ttu-id="6f654-167">Debe definir ciertos operadores como pares coincidentes.</span><span class="sxs-lookup"><span data-stu-id="6f654-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="6f654-168">Si define un operador de este tipo, debe definir también el otro.</span><span class="sxs-lookup"><span data-stu-id="6f654-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="6f654-169">Los pares coincidentes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f654-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="6f654-170">`=` y `<>`</span><span class="sxs-lookup"><span data-stu-id="6f654-170">`=` and `<>`</span></span>

- <span data-ttu-id="6f654-171">`>` y `<`</span><span class="sxs-lookup"><span data-stu-id="6f654-171">`>` and `<`</span></span>

- <span data-ttu-id="6f654-172">`>=` y `<=`</span><span class="sxs-lookup"><span data-stu-id="6f654-172">`>=` and `<=`</span></span>

- <span data-ttu-id="6f654-173">`IsTrue` y `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="6f654-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="6f654-174">Restricciones de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6f654-174">Data Type Restrictions</span></span>

<span data-ttu-id="6f654-175">Cada operador que defina debe incluir la clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="6f654-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="6f654-176">Esto significa que la clase o estructura debe aparecer como el tipo de datos de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f654-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="6f654-177">Operando de un operador unario.</span><span class="sxs-lookup"><span data-stu-id="6f654-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="6f654-178">Al menos uno de los operandos de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="6f654-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="6f654-179">El operando o el tipo de valor devuelto de un operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="6f654-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="6f654-180">Ciertos operadores tienen restricciones de tipo de datos adicionales, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6f654-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="6f654-181">Si define los operadores `IsTrue` y `IsFalse`, ambos deben devolver el tipo de `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="6f654-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="6f654-182">Si define los operadores `<<` y `>>`, ambos deben especificar el tipo de `Integer` para la `operandtype` de `operand2`.</span><span class="sxs-lookup"><span data-stu-id="6f654-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="6f654-183">El tipo de valor devuelto no tiene que corresponder al tipo de uno de los operandos.</span><span class="sxs-lookup"><span data-stu-id="6f654-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="6f654-184">Por ejemplo, un operador de comparación como `=` o `<>` puede devolver `Boolean` aunque no se `Boolean` ninguno de los operandos.</span><span class="sxs-lookup"><span data-stu-id="6f654-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="6f654-185">Operadores lógicos y bit a bit</span><span class="sxs-lookup"><span data-stu-id="6f654-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="6f654-186">Los operadores `And`, `Or`, `Not` y `Xor` pueden realizar operaciones lógicas o bit a bit en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6f654-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="6f654-187">Sin embargo, si define uno de estos operadores en una clase o estructura, solo puede definir su operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="6f654-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="6f654-188">No se puede definir el operador de `AndAlso` directamente con una instrucción `Operator`.</span><span class="sxs-lookup"><span data-stu-id="6f654-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="6f654-189">Sin embargo, puede usar `AndAlso` si ha cumplido las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f654-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="6f654-190">Ha definido `And` en los mismos tipos de operando que desea usar para `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="6f654-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="6f654-191">La definición de `And` devuelve el mismo tipo que la clase o estructura en la que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="6f654-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="6f654-192">Ha definido el operador de `IsFalse` en la clase o estructura en la que ha definido `And`.</span><span class="sxs-lookup"><span data-stu-id="6f654-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="6f654-193">Del mismo modo, puede utilizar `OrElse` si ha definido `Or` en los mismos operandos, con el tipo de valor devuelto de la clase o estructura, y ha definido `IsTrue` en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="6f654-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="6f654-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="6f654-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="6f654-195">Una *conversión de ampliación* siempre se realiza correctamente en tiempo de ejecución, mientras que una *conversión de restricción* puede producir un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6f654-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="6f654-196">Para obtener más información, consulta [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="6f654-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="6f654-197">Si declara un procedimiento de conversión para que se `Widening`, el código de procedimiento no debe generar ningún error.</span><span class="sxs-lookup"><span data-stu-id="6f654-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="6f654-198">Esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f654-198">This means the following:</span></span>

- <span data-ttu-id="6f654-199">Siempre debe devolver un valor válido de tipo `type`.</span><span class="sxs-lookup"><span data-stu-id="6f654-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="6f654-200">Debe administrar todas las excepciones posibles y otras condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="6f654-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="6f654-201">Debe controlar cualquier devolución de error de cualquier procedimiento al que llame.</span><span class="sxs-lookup"><span data-stu-id="6f654-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="6f654-202">Si existe la posibilidad de que un procedimiento de conversión no se lleve a cabo correctamente o de que se produzca una excepción no controlada, debe declararlo como `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="6f654-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="6f654-203">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f654-203">Example</span></span>

<span data-ttu-id="6f654-204">En el ejemplo de código siguiente se usa la instrucción `Operator` para definir el contorno de una estructura que incluye procedimientos de operador para los operadores `And`, `Or`, `IsFalse` y `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="6f654-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="6f654-205">`And` y `Or` tienen dos operandos de tipo `abc` y `abc` de tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6f654-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="6f654-206">`IsFalse` y `IsTrue` toman un único operando de tipo `abc` y devuelven `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="6f654-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="6f654-207">Estas definiciones permiten que el código de llamada use `And`, `AndAlso`, `Or` y `OrElse` con operandos de tipo `abc`.</span><span class="sxs-lookup"><span data-stu-id="6f654-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="6f654-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f654-208">See also</span></span>

- [<span data-ttu-id="6f654-209">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="6f654-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="6f654-210">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="6f654-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="6f654-211">Widening</span><span class="sxs-lookup"><span data-stu-id="6f654-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="6f654-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="6f654-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="6f654-213">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="6f654-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="6f654-214">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="6f654-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="6f654-215">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="6f654-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="6f654-216">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="6f654-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="6f654-217">Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="6f654-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="6f654-218">Utilizar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="6f654-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
