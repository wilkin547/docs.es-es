---
description: 'Más información acerca de: instrucción Operator'
title: Operator Statement
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
ms.openlocfilehash: f6a8ae2ac51e8bc8fe1be0de3549004b9dda4ef4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768823"
---
# <a name="operator-statement"></a><span data-ttu-id="334ff-103">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="334ff-103">Operator Statement</span></span>

<span data-ttu-id="334ff-104">Declara el símbolo del operador, los operandos y el código que definen un procedimiento de operador en una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="334ff-104">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="334ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="334ff-105">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="334ff-106">Partes</span><span class="sxs-lookup"><span data-stu-id="334ff-106">Parts</span></span>

`attrlist`  
<span data-ttu-id="334ff-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="334ff-107">Optional.</span></span> <span data-ttu-id="334ff-108">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="334ff-108">See [Attribute List](attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="334ff-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-109">Required.</span></span> <span data-ttu-id="334ff-110">Indica que este procedimiento de operador tiene acceso [público](../modifiers/public.md) .</span><span class="sxs-lookup"><span data-stu-id="334ff-110">Indicates that this operator procedure has [Public](../modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="334ff-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="334ff-111">Optional.</span></span> <span data-ttu-id="334ff-112">Vea [sobrecargas](../modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="334ff-112">See [Overloads](../modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="334ff-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-113">Required.</span></span> <span data-ttu-id="334ff-114">Indica que este procedimiento de operador es un procedimiento [compartido](../modifiers/shared.md) .</span><span class="sxs-lookup"><span data-stu-id="334ff-114">Indicates that this operator procedure is a [Shared](../modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="334ff-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="334ff-115">Optional.</span></span> <span data-ttu-id="334ff-116">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="334ff-116">See [Shadows](../modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="334ff-117">Obligatorio para un operador de conversión a menos que especifique `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="334ff-117">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="334ff-118">Indica que este procedimiento de operador define una conversión de [ampliación](../modifiers/widening.md) .</span><span class="sxs-lookup"><span data-stu-id="334ff-118">Indicates that this operator procedure defines a [Widening](../modifiers/widening.md) conversion.</span></span> <span data-ttu-id="334ff-119">Vea "conversiones de ampliación y de restricción" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="334ff-119">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="334ff-120">Obligatorio para un operador de conversión a menos que especifique `Widening` .</span><span class="sxs-lookup"><span data-stu-id="334ff-120">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="334ff-121">Indica que este procedimiento de operador define una conversión de [restricción](../modifiers/narrowing.md) .</span><span class="sxs-lookup"><span data-stu-id="334ff-121">Indicates that this operator procedure defines a [Narrowing](../modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="334ff-122">Vea "conversiones de ampliación y de restricción" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="334ff-122">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="334ff-123">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-123">Required.</span></span> <span data-ttu-id="334ff-124">Símbolo o identificador del operador que define este procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="334ff-124">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="334ff-125">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-125">Required.</span></span> <span data-ttu-id="334ff-126">El nombre y el tipo del operando único de un operador unario (incluido un operador de conversión) o el operando izquierdo de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="334ff-126">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="334ff-127">Requerido para los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="334ff-127">Required for binary operators.</span></span> <span data-ttu-id="334ff-128">Nombre y tipo del operando derecho de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="334ff-128">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="334ff-129">`operand1` y `operand2` tienen la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="334ff-129">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="334ff-130">Parte</span><span class="sxs-lookup"><span data-stu-id="334ff-130">Part</span></span>|<span data-ttu-id="334ff-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="334ff-131">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="334ff-132">Opcional, pero el mecanismo de paso debe ser [ByVal](../modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="334ff-132">Optional, but the passing mechanism must be [ByVal](../modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="334ff-133">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-133">Required.</span></span> <span data-ttu-id="334ff-134">Nombre de la variable que representa este operando.</span><span class="sxs-lookup"><span data-stu-id="334ff-134">Name of the variable representing this operand.</span></span> <span data-ttu-id="334ff-135">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="334ff-135">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="334ff-136">Opcional a menos que `Option Strict` sea `On` .</span><span class="sxs-lookup"><span data-stu-id="334ff-136">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="334ff-137">Tipo de datos de este operando.</span><span class="sxs-lookup"><span data-stu-id="334ff-137">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="334ff-138">Opcional a menos que `Option Strict` sea `On` .</span><span class="sxs-lookup"><span data-stu-id="334ff-138">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="334ff-139">Tipo de datos del valor que el procedimiento del operador devuelve.</span><span class="sxs-lookup"><span data-stu-id="334ff-139">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="334ff-140">Opcional.</span><span class="sxs-lookup"><span data-stu-id="334ff-140">Optional.</span></span> <span data-ttu-id="334ff-141">Bloque de instrucciones que ejecuta el procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="334ff-141">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="334ff-142">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-142">Required.</span></span> <span data-ttu-id="334ff-143">Valor que el procedimiento del operador devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="334ff-143">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="334ff-144">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="334ff-144">`End` `Operator`</span></span>  
<span data-ttu-id="334ff-145">Necesario.</span><span class="sxs-lookup"><span data-stu-id="334ff-145">Required.</span></span> <span data-ttu-id="334ff-146">Finaliza la definición de este procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="334ff-146">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="334ff-147">Observaciones</span><span class="sxs-lookup"><span data-stu-id="334ff-147">Remarks</span></span>

<span data-ttu-id="334ff-148">Solo se puede usar `Operator` en una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="334ff-148">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="334ff-149">Esto significa que el contexto de la *declaración* de un operador no puede ser un archivo de código fuente, un espacio de nombres, un módulo, una interfaz, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="334ff-149">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="334ff-150">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="334ff-150">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="334ff-151">Todos los operadores deben ser `Public Shared` .</span><span class="sxs-lookup"><span data-stu-id="334ff-151">All operators must be `Public Shared`.</span></span> <span data-ttu-id="334ff-152">No se puede especificar `ByRef` , `Optional` ni `ParamArray` para ninguno de los operandos.</span><span class="sxs-lookup"><span data-stu-id="334ff-152">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="334ff-153">No se puede utilizar el símbolo de operador o el identificador para contener un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="334ff-153">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="334ff-154">Debe utilizar la `Return` instrucción y debe especificar un valor.</span><span class="sxs-lookup"><span data-stu-id="334ff-154">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="334ff-155">Cualquier número de `Return` instrucciones puede aparecer en cualquier parte del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="334ff-155">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="334ff-156">La definición de un operador de este modo se denomina *sobrecarga de operadores*, tanto si se usa la `Overloads` palabra clave como si no.</span><span class="sxs-lookup"><span data-stu-id="334ff-156">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="334ff-157">En la tabla siguiente se enumeran los operadores que se pueden definir.</span><span class="sxs-lookup"><span data-stu-id="334ff-157">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="334ff-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="334ff-158">Type</span></span>|<span data-ttu-id="334ff-159">Operadores</span><span class="sxs-lookup"><span data-stu-id="334ff-159">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="334ff-160">Unario</span><span class="sxs-lookup"><span data-stu-id="334ff-160">Unary</span></span>|<span data-ttu-id="334ff-161">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="334ff-161">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="334ff-162">Binary</span><span class="sxs-lookup"><span data-stu-id="334ff-162">Binary</span></span>|<span data-ttu-id="334ff-163">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="334ff-163">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="334ff-164">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="334ff-164">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="334ff-165">Tenga en cuenta que el `=` operador de la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="334ff-165">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="334ff-166">Al definir `CType` , debe especificar `Widening` o `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="334ff-166">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="334ff-167">Pares coincidentes</span><span class="sxs-lookup"><span data-stu-id="334ff-167">Matched Pairs</span></span>

<span data-ttu-id="334ff-168">Debe definir ciertos operadores como pares coincidentes.</span><span class="sxs-lookup"><span data-stu-id="334ff-168">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="334ff-169">Si define un operador de este tipo, debe definir también el otro.</span><span class="sxs-lookup"><span data-stu-id="334ff-169">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="334ff-170">Los pares coincidentes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="334ff-170">The matched pairs are the following:</span></span>

- <span data-ttu-id="334ff-171">`=` y `<>`</span><span class="sxs-lookup"><span data-stu-id="334ff-171">`=` and `<>`</span></span>

- <span data-ttu-id="334ff-172">`>` y `<`</span><span class="sxs-lookup"><span data-stu-id="334ff-172">`>` and `<`</span></span>

- <span data-ttu-id="334ff-173">`>=` y `<=`</span><span class="sxs-lookup"><span data-stu-id="334ff-173">`>=` and `<=`</span></span>

- <span data-ttu-id="334ff-174">`IsTrue` y `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="334ff-174">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="334ff-175">Restricciones de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="334ff-175">Data Type Restrictions</span></span>

<span data-ttu-id="334ff-176">Cada operador que defina debe incluir la clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="334ff-176">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="334ff-177">Esto significa que la clase o estructura debe aparecer como el tipo de datos de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="334ff-177">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="334ff-178">Operando de un operador unario.</span><span class="sxs-lookup"><span data-stu-id="334ff-178">The operand of a unary operator.</span></span>

- <span data-ttu-id="334ff-179">Al menos uno de los operandos de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="334ff-179">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="334ff-180">El operando o el tipo de valor devuelto de un operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="334ff-180">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="334ff-181">Ciertos operadores tienen restricciones de tipo de datos adicionales, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="334ff-181">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="334ff-182">Si define los `IsTrue` operadores y `IsFalse` , ambos deben devolver el `Boolean` tipo.</span><span class="sxs-lookup"><span data-stu-id="334ff-182">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="334ff-183">Si define los `<<` operadores y `>>` , ambos deben especificar el `Integer` tipo para el `operandtype` de `operand2` .</span><span class="sxs-lookup"><span data-stu-id="334ff-183">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="334ff-184">El tipo de valor devuelto no tiene que corresponder al tipo de uno de los operandos.</span><span class="sxs-lookup"><span data-stu-id="334ff-184">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="334ff-185">Por ejemplo, un operador de comparación como `=` o `<>` puede devolver `Boolean` aunque ninguno de los operandos sea `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="334ff-185">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="334ff-186">Operadores lógicos y bit a bit</span><span class="sxs-lookup"><span data-stu-id="334ff-186">Logical and Bitwise Operators</span></span>

<span data-ttu-id="334ff-187">Los `And` `Or` operadores,, `Not` y `Xor` pueden realizar operaciones lógicas o bit a bit en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="334ff-187">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="334ff-188">Sin embargo, si define uno de estos operadores en una clase o estructura, solo puede definir su operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="334ff-188">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="334ff-189">No se puede definir el `AndAlso` operador directamente con una `Operator` instrucción.</span><span class="sxs-lookup"><span data-stu-id="334ff-189">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="334ff-190">Sin embargo, puede usar `AndAlso` si ha cumplido las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="334ff-190">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="334ff-191">Ha definido `And` en los mismos tipos de operando que desea usar para `AndAlso` .</span><span class="sxs-lookup"><span data-stu-id="334ff-191">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="334ff-192">La definición de `And` devuelve el mismo tipo que la clase o estructura en la que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="334ff-192">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="334ff-193">Ha definido el `IsFalse` operador en la clase o estructura en la que ha definido `And` .</span><span class="sxs-lookup"><span data-stu-id="334ff-193">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="334ff-194">Del mismo modo, puede utilizar `OrElse` si ha definido `Or` en los mismos operandos, con el tipo de valor devuelto de la clase o la estructura, y ha definido `IsTrue` en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="334ff-194">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="334ff-195">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="334ff-195">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="334ff-196">Una *conversión de ampliación* siempre se realiza correctamente en tiempo de ejecución, mientras que una *conversión de restricción* puede producir un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="334ff-196">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="334ff-197">Para obtener más información, consulta [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="334ff-197">For more information, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="334ff-198">Si declara que un procedimiento de conversión es `Widening` , el código de procedimiento no debe generar ningún error.</span><span class="sxs-lookup"><span data-stu-id="334ff-198">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="334ff-199">Esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="334ff-199">This means the following:</span></span>

- <span data-ttu-id="334ff-200">Siempre debe devolver un valor válido de tipo `type` .</span><span class="sxs-lookup"><span data-stu-id="334ff-200">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="334ff-201">Debe administrar todas las excepciones posibles y otras condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="334ff-201">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="334ff-202">Debe controlar cualquier devolución de error de cualquier procedimiento al que llame.</span><span class="sxs-lookup"><span data-stu-id="334ff-202">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="334ff-203">Si existe la posibilidad de que un procedimiento de conversión no se lleve a cabo correctamente o de que pueda provocar una excepción no controlada, debe declararlo como `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="334ff-203">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="334ff-204">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="334ff-204">Example</span></span>

<span data-ttu-id="334ff-205">En el ejemplo de código siguiente `Operator` se usa la instrucción para definir el contorno de una estructura que incluye procedimientos de operador para los `And` `Or` operadores,, `IsFalse` y `IsTrue` .</span><span class="sxs-lookup"><span data-stu-id="334ff-205">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="334ff-206">`And` y `Or` cada uno de ellos toman dos operandos de tipo `abc` y tipo de valor devuelto `abc` .</span><span class="sxs-lookup"><span data-stu-id="334ff-206">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="334ff-207">`IsFalse` y `IsTrue` cada toman un solo operando de tipo `abc` y devuelven `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="334ff-207">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="334ff-208">Estas definiciones permiten que el código de llamada use `And` ,, `AndAlso` `Or` y `OrElse` con operandos de tipo `abc` .</span><span class="sxs-lookup"><span data-stu-id="334ff-208">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="334ff-209">Vea también</span><span class="sxs-lookup"><span data-stu-id="334ff-209">See also</span></span>

- [<span data-ttu-id="334ff-210">Operador IsFalse</span><span class="sxs-lookup"><span data-stu-id="334ff-210">IsFalse Operator</span></span>](../operators/isfalse-operator.md)
- [<span data-ttu-id="334ff-211">Operador IsTrue</span><span class="sxs-lookup"><span data-stu-id="334ff-211">IsTrue Operator</span></span>](../operators/istrue-operator.md)
- [<span data-ttu-id="334ff-212">Widening</span><span class="sxs-lookup"><span data-stu-id="334ff-212">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="334ff-213">Narrowing</span><span class="sxs-lookup"><span data-stu-id="334ff-213">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="334ff-214">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="334ff-214">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="334ff-215">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="334ff-215">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="334ff-216">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="334ff-216">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="334ff-217">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="334ff-217">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="334ff-218">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="334ff-218">How to: Call an Operator Procedure</span></span>](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="334ff-219">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="334ff-219">How to: Use a Class that Defines Operators</span></span>](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
