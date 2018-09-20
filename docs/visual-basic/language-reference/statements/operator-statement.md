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
ms.openlocfilehash: 69dea99cf71bd1e091116e54e244abfca291ffdb
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481980"
---
# <a name="operator-statement"></a><span data-ttu-id="2b0ea-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="2b0ea-102">Operator Statement</span></span>
<span data-ttu-id="2b0ea-103">Declara el símbolo del operador, los operandos y el código que definen un procedimiento de operador en una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b0ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b0ea-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="2b0ea-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2b0ea-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="2b0ea-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-106">Optional.</span></span> <span data-ttu-id="2b0ea-107">Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="2b0ea-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-108">Required.</span></span> <span data-ttu-id="2b0ea-109">Indica que este procedimiento de operador tiene [pública](../../../visual-basic/language-reference/modifiers/public.md) acceso.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="2b0ea-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-110">Optional.</span></span> <span data-ttu-id="2b0ea-111">Consulte [sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="2b0ea-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-112">Required.</span></span> <span data-ttu-id="2b0ea-113">Indica que este procedimiento de operador es un [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="2b0ea-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-114">Optional.</span></span> <span data-ttu-id="2b0ea-115">Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="2b0ea-116">Necesario para un operador de conversión a menos que especifique `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="2b0ea-117">Indica que este procedimiento de operador define un [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversión.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="2b0ea-118">Vea "Ampliación y Narrowing Conversions" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="2b0ea-119">Necesario para un operador de conversión a menos que especifique `Widening`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="2b0ea-120">Indica que este procedimiento de operador define un [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversión.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="2b0ea-121">Vea "Ampliación y Narrowing Conversions" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="2b0ea-122">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-122">Required.</span></span> <span data-ttu-id="2b0ea-123">El símbolo o el identificador del operador que define este procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="2b0ea-124">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-124">Required.</span></span> <span data-ttu-id="2b0ea-125">El nombre y tipo de operando único de un operador unario (incluido un operador de conversión) o el operando izquierdo de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="2b0ea-126">Se requiere para los operadores binarios.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-126">Required for binary operators.</span></span> <span data-ttu-id="2b0ea-127">El nombre y tipo del operando derecho de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="2b0ea-128">`operand1` y `operand2` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b0ea-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="2b0ea-129">Parte</span><span class="sxs-lookup"><span data-stu-id="2b0ea-129">Part</span></span>|<span data-ttu-id="2b0ea-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b0ea-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="2b0ea-131">Debe ser opcional, pero el mecanismo de paso [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="2b0ea-132">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-132">Required.</span></span> <span data-ttu-id="2b0ea-133">Nombre de la variable que representa este operando.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="2b0ea-134">Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="2b0ea-135">Opcional, a menos que `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="2b0ea-136">Tipo de datos de este operando.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="2b0ea-137">Opcional, a menos que `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="2b0ea-138">Devuelve el tipo de datos del valor el procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="2b0ea-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-139">Optional.</span></span> <span data-ttu-id="2b0ea-140">Bloque de instrucciones que se ejecuta el procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="2b0ea-141">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-141">Required.</span></span> <span data-ttu-id="2b0ea-142">El valor que el procedimiento de operador devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="2b0ea-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-143">`End` `Operator`</span></span>  
 <span data-ttu-id="2b0ea-144">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-144">Required.</span></span> <span data-ttu-id="2b0ea-145">Termina la definición de este procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b0ea-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b0ea-146">Remarks</span></span>  
 <span data-ttu-id="2b0ea-147">Puede usar `Operator` solo en una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="2b0ea-148">Esto significa que el *contexto de declaración* para un operador no puede ser un archivo de código fuente, espacio de nombres, módulo, interfaz, procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="2b0ea-149">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="2b0ea-150">Todos los operadores deben ser `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="2b0ea-151">No puede especificar `ByRef`, `Optional`, o `ParamArray` para cualquiera de los operandos.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="2b0ea-152">No puede usar el símbolo del operador o el identificador para contener un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="2b0ea-153">Debe usar el `Return` instrucción y deben especificar un valor.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="2b0ea-154">Cualquier número de `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="2b0ea-155">Definición de un operador de esta manera se denomina *sobrecarga de operadores*, utilice o no el `Overloads` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="2b0ea-156">En la tabla siguiente se enumeran los operadores que se pueden definir.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="2b0ea-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="2b0ea-157">Type</span></span>|<span data-ttu-id="2b0ea-158">Operadores</span><span class="sxs-lookup"><span data-stu-id="2b0ea-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="2b0ea-159">Unario</span><span class="sxs-lookup"><span data-stu-id="2b0ea-159">Unary</span></span>|<span data-ttu-id="2b0ea-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="2b0ea-161">Binary</span><span class="sxs-lookup"><span data-stu-id="2b0ea-161">Binary</span></span>|<span data-ttu-id="2b0ea-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="2b0ea-163">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="2b0ea-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="2b0ea-164">Tenga en cuenta que el `=` operador en la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="2b0ea-165">Al definir `CType`, debe especificar `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="2b0ea-166">Pares coincidentes</span><span class="sxs-lookup"><span data-stu-id="2b0ea-166">Matched Pairs</span></span>  
 <span data-ttu-id="2b0ea-167">Debe definir ciertos operadores como pares coincidentes.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="2b0ea-168">Si define un operador de este tipo, debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="2b0ea-169">Los pares correspondientes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b0ea-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="2b0ea-170">`=` y `<>`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="2b0ea-171">`>` y `<`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="2b0ea-172">`>=` y `<=`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="2b0ea-173">`IsTrue` y `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="2b0ea-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="2b0ea-174">Restricciones de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2b0ea-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="2b0ea-175">Cada operador que define debe implicar la clase o estructura en el que se definen.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="2b0ea-176">Esto significa que la clase o estructura debe aparecer como el tipo de datos de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2b0ea-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="2b0ea-177">El operando de un operador unario.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="2b0ea-178">Al menos uno de los operandos de un operador binario.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="2b0ea-179">El operando o el tipo de valor devuelto de un operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="2b0ea-180">Ciertos operadores tienen datos adicionales que escriba las restricciones, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2b0ea-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="2b0ea-181">Si define la `IsTrue` y `IsFalse` operadores, deben devolver el `Boolean` tipo.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="2b0ea-182">Si define la `<<` y `>>` operadores, ambos deben especificar el `Integer` tipo para el `operandtype` de `operand2`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="2b0ea-183">El tipo de valor devuelto no tiene que corresponder con el tipo de uno de los operandos.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="2b0ea-184">Por ejemplo, un operador de comparación como `=` o `<>` puede devolver `Boolean` incluso si ninguno de los operandos es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="2b0ea-185">Operadores lógicos y bit a bit</span><span class="sxs-lookup"><span data-stu-id="2b0ea-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="2b0ea-186">El `And`, `Or`, `Not`, y `Xor` operadores pueden realizar operaciones bit a bit o lógicas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="2b0ea-187">Sin embargo, si define uno de estos operadores en una clase o estructura, puede definir solo su operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="2b0ea-188">No puede definir la `AndAlso` operador directamente con un `Operator` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="2b0ea-189">Sin embargo, puede usar `AndAlso` si ha cumplido las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b0ea-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="2b0ea-190">Ha definido `And` en los mismos tipos de operando que se va a utilizar para `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="2b0ea-191">La definición de `And` devuelve el mismo tipo que la clase o estructura en el que ha definido.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="2b0ea-192">Ha definido el `IsFalse` operador en la clase o estructura en el que ha definido `And`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="2b0ea-193">De forma similar, puede usar `OrElse` si ha definido `Or` en los operandos de la mismos, se ha definido con el tipo de valor devuelto de la clase o estructura y `IsTrue` en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="2b0ea-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="2b0ea-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="2b0ea-195">Un *una conversión de ampliación* siempre se realiza correctamente en tiempo de ejecución, mientras que un *conversión de restricción* puede producir un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="2b0ea-196">Para obtener más información, consulta [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="2b0ea-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="2b0ea-197">Si declara un procedimiento de conversión `Widening`, el código de procedimiento no debe generar errores.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="2b0ea-198">Esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b0ea-198">This means the following:</span></span>  
  
-   <span data-ttu-id="2b0ea-199">Siempre debe devolver un valor válido de tipo `type`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="2b0ea-200">Deben controlar todas las posibles excepciones y otras condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="2b0ea-201">Deben controlar los errores devueltos desde cualquier procedimiento al que llama.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="2b0ea-202">Si hay alguna posibilidad de que un procedimiento de conversión podría no realizarse correctamente o que TI puede provocar una excepción no controlada, debe declararla como `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b0ea-203">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b0ea-203">Example</span></span>  
 <span data-ttu-id="2b0ea-204">El siguiente ejemplo de código utiliza el `Operator` instrucción para definir el esquema de una estructura que incluye procedimientos de operador para el `And`, `Or`, `IsFalse`, y `IsTrue` operadores.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="2b0ea-205">`And` y `Or` cada toman dos operandos de tipo `abc` y tipo de valor devuelto `abc`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="2b0ea-206">`IsFalse` y `IsTrue` tomar un único operando de tipo `abc` y devolver `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="2b0ea-207">Estas definiciones de permitir que el código que realiza la llamada usar `And`, `AndAlso`, `Or`, y `OrElse` con operandos de tipo `abc`.</span><span class="sxs-lookup"><span data-stu-id="2b0ea-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2b0ea-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b0ea-208">See Also</span></span>  
 [<span data-ttu-id="2b0ea-209">IsFalse (operador)</span><span class="sxs-lookup"><span data-stu-id="2b0ea-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="2b0ea-210">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="2b0ea-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="2b0ea-211">Widening</span><span class="sxs-lookup"><span data-stu-id="2b0ea-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="2b0ea-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="2b0ea-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="2b0ea-213">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="2b0ea-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="2b0ea-214">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="2b0ea-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="2b0ea-215">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="2b0ea-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="2b0ea-216">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="2b0ea-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="2b0ea-217">Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="2b0ea-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="2b0ea-218">Utilizar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="2b0ea-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
