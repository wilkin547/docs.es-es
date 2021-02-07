---
description: 'Más información acerca de: operador + (Visual Basic)'
title: + Operator
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 9a6517847945cb2edcbd97adac6a013498dde174
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700694"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e3111-103">+ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3111-103">+ Operator (Visual Basic)</span></span>

<span data-ttu-id="e3111-104">Suma dos números o devuelve el valor positivo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e3111-104">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="e3111-105">También se puede utilizar para concatenar dos expresiones de cadena.</span><span class="sxs-lookup"><span data-stu-id="e3111-105">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3111-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3111-106">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="e3111-107">o</span><span class="sxs-lookup"><span data-stu-id="e3111-107">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="e3111-108">Partes</span><span class="sxs-lookup"><span data-stu-id="e3111-108">Parts</span></span>  
  
|<span data-ttu-id="e3111-109">Término</span><span class="sxs-lookup"><span data-stu-id="e3111-109">Term</span></span>|<span data-ttu-id="e3111-110">Definición</span><span class="sxs-lookup"><span data-stu-id="e3111-110">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="e3111-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e3111-111">Required.</span></span> <span data-ttu-id="e3111-112">Cualquier expresión numérica o de cadena.</span><span class="sxs-lookup"><span data-stu-id="e3111-112">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="e3111-113">Obligatorio a menos que el `+` operador calcule un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="e3111-113">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="e3111-114">Cualquier expresión numérica o de cadena.</span><span class="sxs-lookup"><span data-stu-id="e3111-114">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="e3111-115">Resultado</span><span class="sxs-lookup"><span data-stu-id="e3111-115">Result</span></span>  

 <span data-ttu-id="e3111-116">Si `expression1` y `expression2` son ambos numéricos, el resultado es su suma aritmética.</span><span class="sxs-lookup"><span data-stu-id="e3111-116">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="e3111-117">Si `expression2` no está presente, el `+` operador es el operador *unario* de identidad para el valor sin modificar de una expresión.</span><span class="sxs-lookup"><span data-stu-id="e3111-117">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="e3111-118">En este sentido, la operación consiste en conservar el signo de `expression1` , por lo que el resultado es negativo si `expression1` es negativo.</span><span class="sxs-lookup"><span data-stu-id="e3111-118">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="e3111-119">Si `expression1` y `expression2` son ambas cadenas, el resultado es la concatenación de sus valores.</span><span class="sxs-lookup"><span data-stu-id="e3111-119">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="e3111-120">Si `expression1` y `expression2` son de tipos mixtos, la acción tomada depende de sus tipos, su contenido y la configuración de la [instrucción Option Strict](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e3111-120">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="e3111-121">Para obtener más información, vea las tablas de "Comentarios".</span><span class="sxs-lookup"><span data-stu-id="e3111-121">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="e3111-122">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="e3111-122">Supported Types</span></span>  

 <span data-ttu-id="e3111-123">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` , y `String` .</span><span class="sxs-lookup"><span data-stu-id="e3111-123">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3111-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e3111-124">Remarks</span></span>  

 <span data-ttu-id="e3111-125">En general, `+` realiza la suma aritmética siempre que sea posible y concatena solo cuando ambas expresiones son cadenas.</span><span class="sxs-lookup"><span data-stu-id="e3111-125">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="e3111-126">Si ninguna `Object` de las expresiones es, Visual Basic realiza las acciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3111-126">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="e3111-127">Tipos de datos de expresiones</span><span class="sxs-lookup"><span data-stu-id="e3111-127">Data types of expressions</span></span>|<span data-ttu-id="e3111-128">Acción por el compilador</span><span class="sxs-lookup"><span data-stu-id="e3111-128">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="e3111-129">Ambas expresiones son tipos de datos numéricos ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` o `Double` )</span><span class="sxs-lookup"><span data-stu-id="e3111-129">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="e3111-130">Agregar.</span><span class="sxs-lookup"><span data-stu-id="e3111-130">Add.</span></span> <span data-ttu-id="e3111-131">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="e3111-131">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="e3111-132">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="e3111-132">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="e3111-133">Ambas expresiones son de tipo `String`</span><span class="sxs-lookup"><span data-stu-id="e3111-133">Both expressions are of type `String`</span></span>|<span data-ttu-id="e3111-134">Concatenar.</span><span class="sxs-lookup"><span data-stu-id="e3111-134">Concatenate.</span></span>|  
|<span data-ttu-id="e3111-135">Una expresión es un tipo de datos numérico y la otra es una cadena</span><span class="sxs-lookup"><span data-stu-id="e3111-135">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="e3111-136">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e3111-136">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e3111-137">Si `Option Strict` es `Off` , convierta implícitamente el `String` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="e3111-137">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e3111-138">Si `String` no se puede convertir en `Double` , inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="e3111-138">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="e3111-139">Una expresión es un tipo de datos numérico y la otra no es [nada](../nothing.md)</span><span class="sxs-lookup"><span data-stu-id="e3111-139">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="e3111-140">Agregue, con un `Nothing` valor igual a cero.</span><span class="sxs-lookup"><span data-stu-id="e3111-140">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="e3111-141">Una expresión es una cadena y la otra es `Nothing`</span><span class="sxs-lookup"><span data-stu-id="e3111-141">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="e3111-142">Concatenate, con el `Nothing` valor "".</span><span class="sxs-lookup"><span data-stu-id="e3111-142">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="e3111-143">Si una expresión es una `Object` expresión, Visual Basic realiza las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="e3111-143">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="e3111-144">Tipos de datos de expresiones</span><span class="sxs-lookup"><span data-stu-id="e3111-144">Data types of expressions</span></span>|<span data-ttu-id="e3111-145">Acción por el compilador</span><span class="sxs-lookup"><span data-stu-id="e3111-145">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="e3111-146">`Object` la expresión contiene un valor numérico y la otra es un tipo de datos numérico</span><span class="sxs-lookup"><span data-stu-id="e3111-146">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="e3111-147">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e3111-147">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e3111-148">Si `Option Strict` es `Off` , agregue.</span><span class="sxs-lookup"><span data-stu-id="e3111-148">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="e3111-149">`Object` la expresión contiene un valor numérico y el otro es de tipo `String`</span><span class="sxs-lookup"><span data-stu-id="e3111-149">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="e3111-150">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e3111-150">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e3111-151">Si `Option Strict` es `Off` , convierta implícitamente el `String` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="e3111-151">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e3111-152">Si `String` no se puede convertir en `Double` , inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="e3111-152">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="e3111-153">`Object` la expresión contiene una cadena y la otra es un tipo de datos numérico</span><span class="sxs-lookup"><span data-stu-id="e3111-153">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="e3111-154">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e3111-154">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e3111-155">Si `Option Strict` es `Off` , convierta implícitamente la cadena `Object` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="e3111-155">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e3111-156">Si la cadena `Object` no se puede convertir en `Double` , inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="e3111-156">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="e3111-157">`Object` la expresión contiene una cadena y la otra es de tipo `String`</span><span class="sxs-lookup"><span data-stu-id="e3111-157">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="e3111-158">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e3111-158">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="e3111-159">Si `Option Strict` es `Off` , convierta implícitamente `Object` en `String` y concatene.</span><span class="sxs-lookup"><span data-stu-id="e3111-159">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="e3111-160">Si ambas expresiones son `Object` expresiones, Visual Basic toma las siguientes acciones ( `Option Strict Off` solo).</span><span class="sxs-lookup"><span data-stu-id="e3111-160">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="e3111-161">Tipos de datos de expresiones</span><span class="sxs-lookup"><span data-stu-id="e3111-161">Data types of expressions</span></span>|<span data-ttu-id="e3111-162">Acción por el compilador</span><span class="sxs-lookup"><span data-stu-id="e3111-162">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="e3111-163">Ambas `Object` expresiones contienen valores numéricos</span><span class="sxs-lookup"><span data-stu-id="e3111-163">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="e3111-164">Agregar.</span><span class="sxs-lookup"><span data-stu-id="e3111-164">Add.</span></span>|  
|<span data-ttu-id="e3111-165">Ambas `Object` expresiones son de tipo `String`</span><span class="sxs-lookup"><span data-stu-id="e3111-165">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="e3111-166">Concatenar.</span><span class="sxs-lookup"><span data-stu-id="e3111-166">Concatenate.</span></span>|  
|<span data-ttu-id="e3111-167">Una `Object` expresión contiene un valor numérico y la otra contiene una cadena</span><span class="sxs-lookup"><span data-stu-id="e3111-167">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="e3111-168">Convierta implícitamente la cadena `Object` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="e3111-168">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="e3111-169">Si la cadena `Object` no se puede convertir en un valor numérico, inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="e3111-169">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="e3111-170">Si alguna de las `Object` expresiones se evalúa como [Nothing](../nothing.md) o <xref:System.DBNull> , el `+` operador la trata como un `String` con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="e3111-170">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3111-171">Al utilizar el `+` operador, es posible que no pueda determinar si se producirá la concatenación de cadenas o la suma.</span><span class="sxs-lookup"><span data-stu-id="e3111-171">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="e3111-172">Utilice el `&` operador para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.</span><span class="sxs-lookup"><span data-stu-id="e3111-172">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e3111-173">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="e3111-173">Overloading</span></span>  

 <span data-ttu-id="e3111-174">El `+` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e3111-174">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e3111-175">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e3111-175">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e3111-176">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e3111-176">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3111-177">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3111-177">Example</span></span>  

 <span data-ttu-id="e3111-178">En el ejemplo siguiente se usa el `+` operador para agregar números.</span><span class="sxs-lookup"><span data-stu-id="e3111-178">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="e3111-179">Si los operandos son numéricos, Visual Basic calcula el resultado aritmético.</span><span class="sxs-lookup"><span data-stu-id="e3111-179">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="e3111-180">El resultado aritmético representa la suma de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="e3111-180">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="e3111-181">También puede usar el `+` operador para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="e3111-181">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="e3111-182">Si los operandos son ambas cadenas, Visual Basic las concatena.</span><span class="sxs-lookup"><span data-stu-id="e3111-182">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="e3111-183">El resultado de la concatenación representa una sola cadena formada por el contenido de los dos operandos uno tras otro.</span><span class="sxs-lookup"><span data-stu-id="e3111-183">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="e3111-184">Si los operandos son de tipos mixtos, el resultado depende de la configuración de la [instrucción Option Strict](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e3111-184">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="e3111-185">En el ejemplo siguiente se muestra el resultado cuando `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="e3111-185">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="e3111-186">En el ejemplo siguiente se muestra el resultado cuando `Option Strict` es `Off` .</span><span class="sxs-lookup"><span data-stu-id="e3111-186">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="e3111-187">Para eliminar la ambigüedad, debe usar el `&` operador en lugar de `+` para la concatenación.</span><span class="sxs-lookup"><span data-stu-id="e3111-187">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3111-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3111-188">See also</span></span>

- [<span data-ttu-id="e3111-189">& (operador)</span><span class="sxs-lookup"><span data-stu-id="e3111-189">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="e3111-190">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="e3111-190">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="e3111-191">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="e3111-191">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e3111-192">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e3111-192">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e3111-193">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3111-193">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e3111-194">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3111-194">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="e3111-195">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e3111-195">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
