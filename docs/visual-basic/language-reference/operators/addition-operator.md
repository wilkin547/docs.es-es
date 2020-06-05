---
title: + Operador
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
ms.openlocfilehash: 6ae3feae6ecb63b82426f2aa69359625bbffcec8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372121"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="187f2-102">+ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="187f2-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="187f2-103">Suma dos números o devuelve el valor positivo de una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="187f2-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="187f2-104">También se puede utilizar para concatenar dos expresiones de cadena.</span><span class="sxs-lookup"><span data-stu-id="187f2-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="187f2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="187f2-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="187f2-106">o</span><span class="sxs-lookup"><span data-stu-id="187f2-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="187f2-107">Partes</span><span class="sxs-lookup"><span data-stu-id="187f2-107">Parts</span></span>  
  
|<span data-ttu-id="187f2-108">Término</span><span class="sxs-lookup"><span data-stu-id="187f2-108">Term</span></span>|<span data-ttu-id="187f2-109">Definición</span><span class="sxs-lookup"><span data-stu-id="187f2-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="187f2-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="187f2-110">Required.</span></span> <span data-ttu-id="187f2-111">Cualquier expresión numérica o de cadena.</span><span class="sxs-lookup"><span data-stu-id="187f2-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="187f2-112">Obligatorio a menos que el `+` operador calcule un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="187f2-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="187f2-113">Cualquier expresión numérica o de cadena.</span><span class="sxs-lookup"><span data-stu-id="187f2-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="187f2-114">Resultado</span><span class="sxs-lookup"><span data-stu-id="187f2-114">Result</span></span>  
 <span data-ttu-id="187f2-115">Si `expression1` y `expression2` son ambos numéricos, el resultado es su suma aritmética.</span><span class="sxs-lookup"><span data-stu-id="187f2-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="187f2-116">Si `expression2` no está presente, el `+` operador es el operador *unario* de identidad para el valor sin modificar de una expresión.</span><span class="sxs-lookup"><span data-stu-id="187f2-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="187f2-117">En este sentido, la operación consiste en conservar el signo de `expression1` , por lo que el resultado es negativo si `expression1` es negativo.</span><span class="sxs-lookup"><span data-stu-id="187f2-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="187f2-118">Si `expression1` y `expression2` son ambas cadenas, el resultado es la concatenación de sus valores.</span><span class="sxs-lookup"><span data-stu-id="187f2-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="187f2-119">Si `expression1` y `expression2` son de tipos mixtos, la acción tomada depende de sus tipos, su contenido y la configuración de la [instrucción Option Strict](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="187f2-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="187f2-120">Para obtener más información, vea las tablas de "Comentarios".</span><span class="sxs-lookup"><span data-stu-id="187f2-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="187f2-121">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="187f2-121">Supported Types</span></span>  
 <span data-ttu-id="187f2-122">Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` , y `String` .</span><span class="sxs-lookup"><span data-stu-id="187f2-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="187f2-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="187f2-123">Remarks</span></span>  
 <span data-ttu-id="187f2-124">En general, `+` realiza la suma aritmética siempre que sea posible y concatena solo cuando ambas expresiones son cadenas.</span><span class="sxs-lookup"><span data-stu-id="187f2-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="187f2-125">Si ninguna `Object` de las expresiones es, Visual Basic realiza las acciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="187f2-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="187f2-126">Tipos de datos de expresiones</span><span class="sxs-lookup"><span data-stu-id="187f2-126">Data types of expressions</span></span>|<span data-ttu-id="187f2-127">Acción por el compilador</span><span class="sxs-lookup"><span data-stu-id="187f2-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="187f2-128">Ambas expresiones son tipos de datos numéricos ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` o `Double` )</span><span class="sxs-lookup"><span data-stu-id="187f2-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="187f2-129">Agregar.</span><span class="sxs-lookup"><span data-stu-id="187f2-129">Add.</span></span> <span data-ttu-id="187f2-130">El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` .</span><span class="sxs-lookup"><span data-stu-id="187f2-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="187f2-131">Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="187f2-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="187f2-132">Ambas expresiones son de tipo`String`</span><span class="sxs-lookup"><span data-stu-id="187f2-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="187f2-133">Concatenar.</span><span class="sxs-lookup"><span data-stu-id="187f2-133">Concatenate.</span></span>|  
|<span data-ttu-id="187f2-134">Una expresión es un tipo de datos numérico y la otra es una cadena</span><span class="sxs-lookup"><span data-stu-id="187f2-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="187f2-135">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="187f2-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="187f2-136">Si `Option Strict` es `Off` , convierta implícitamente el `String` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="187f2-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="187f2-137">Si `String` no se puede convertir en `Double` , inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="187f2-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="187f2-138">Una expresión es un tipo de datos numérico y la otra no es [nada](../nothing.md)</span><span class="sxs-lookup"><span data-stu-id="187f2-138">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="187f2-139">Agregue, con un `Nothing` valor igual a cero.</span><span class="sxs-lookup"><span data-stu-id="187f2-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="187f2-140">Una expresión es una cadena y la otra es`Nothing`</span><span class="sxs-lookup"><span data-stu-id="187f2-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="187f2-141">Concatenate, con el `Nothing` valor "".</span><span class="sxs-lookup"><span data-stu-id="187f2-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="187f2-142">Si una expresión es una `Object` expresión, Visual Basic realiza las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="187f2-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="187f2-143">Tipos de datos de expresiones</span><span class="sxs-lookup"><span data-stu-id="187f2-143">Data types of expressions</span></span>|<span data-ttu-id="187f2-144">Acción por el compilador</span><span class="sxs-lookup"><span data-stu-id="187f2-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="187f2-145">`Object`la expresión contiene un valor numérico y la otra es un tipo de datos numérico</span><span class="sxs-lookup"><span data-stu-id="187f2-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="187f2-146">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="187f2-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="187f2-147">Si `Option Strict` es `Off` , agregue.</span><span class="sxs-lookup"><span data-stu-id="187f2-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="187f2-148">`Object`la expresión contiene un valor numérico y el otro es de tipo`String`</span><span class="sxs-lookup"><span data-stu-id="187f2-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="187f2-149">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="187f2-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="187f2-150">Si `Option Strict` es `Off` , convierta implícitamente el `String` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="187f2-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="187f2-151">Si `String` no se puede convertir en `Double` , inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="187f2-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="187f2-152">`Object`la expresión contiene una cadena y la otra es un tipo de datos numérico</span><span class="sxs-lookup"><span data-stu-id="187f2-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="187f2-153">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="187f2-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="187f2-154">Si `Option Strict` es `Off` , convierta implícitamente la cadena `Object` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="187f2-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="187f2-155">Si la cadena `Object` no se puede convertir en `Double` , inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="187f2-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="187f2-156">`Object`la expresión contiene una cadena y la otra es de tipo`String`</span><span class="sxs-lookup"><span data-stu-id="187f2-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="187f2-157">Si `Option Strict` es `On` , genere un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="187f2-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="187f2-158">Si `Option Strict` es `Off` , convierta implícitamente `Object` en `String` y concatene.</span><span class="sxs-lookup"><span data-stu-id="187f2-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="187f2-159">Si ambas expresiones son `Object` expresiones, Visual Basic toma las siguientes acciones ( `Option Strict Off` solo).</span><span class="sxs-lookup"><span data-stu-id="187f2-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="187f2-160">Tipos de datos de expresiones</span><span class="sxs-lookup"><span data-stu-id="187f2-160">Data types of expressions</span></span>|<span data-ttu-id="187f2-161">Acción por el compilador</span><span class="sxs-lookup"><span data-stu-id="187f2-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="187f2-162">Ambas `Object` expresiones contienen valores numéricos</span><span class="sxs-lookup"><span data-stu-id="187f2-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="187f2-163">Agregar.</span><span class="sxs-lookup"><span data-stu-id="187f2-163">Add.</span></span>|  
|<span data-ttu-id="187f2-164">Ambas `Object` expresiones son de tipo`String`</span><span class="sxs-lookup"><span data-stu-id="187f2-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="187f2-165">Concatenar.</span><span class="sxs-lookup"><span data-stu-id="187f2-165">Concatenate.</span></span>|  
|<span data-ttu-id="187f2-166">Una `Object` expresión contiene un valor numérico y la otra contiene una cadena</span><span class="sxs-lookup"><span data-stu-id="187f2-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="187f2-167">Convierta implícitamente la cadena `Object` en `Double` y agregue.</span><span class="sxs-lookup"><span data-stu-id="187f2-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="187f2-168">Si la cadena `Object` no se puede convertir en un valor numérico, inicie una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="187f2-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="187f2-169">Si alguna de las `Object` expresiones se evalúa como [Nothing](../nothing.md) o <xref:System.DBNull> , el `+` operador la trata como un `String` con un valor de "".</span><span class="sxs-lookup"><span data-stu-id="187f2-169">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="187f2-170">Al utilizar el `+` operador, es posible que no pueda determinar si se producirá la concatenación de cadenas o la suma.</span><span class="sxs-lookup"><span data-stu-id="187f2-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="187f2-171">Utilice el `&` operador para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.</span><span class="sxs-lookup"><span data-stu-id="187f2-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="187f2-172">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="187f2-172">Overloading</span></span>  
 <span data-ttu-id="187f2-173">El `+` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="187f2-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="187f2-174">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="187f2-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="187f2-175">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="187f2-175">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="187f2-176">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="187f2-176">Example</span></span>  
 <span data-ttu-id="187f2-177">En el ejemplo siguiente se usa el `+` operador para agregar números.</span><span class="sxs-lookup"><span data-stu-id="187f2-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="187f2-178">Si los operandos son numéricos, Visual Basic calcula el resultado aritmético.</span><span class="sxs-lookup"><span data-stu-id="187f2-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="187f2-179">El resultado aritmético representa la suma de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="187f2-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="187f2-180">También puede usar el `+` operador para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="187f2-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="187f2-181">Si los operandos son ambas cadenas, Visual Basic las concatena.</span><span class="sxs-lookup"><span data-stu-id="187f2-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="187f2-182">El resultado de la concatenación representa una sola cadena formada por el contenido de los dos operandos uno tras otro.</span><span class="sxs-lookup"><span data-stu-id="187f2-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="187f2-183">Si los operandos son de tipos mixtos, el resultado depende de la configuración de la [instrucción Option Strict](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="187f2-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="187f2-184">En el ejemplo siguiente se muestra el resultado cuando `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="187f2-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="187f2-185">En el ejemplo siguiente se muestra el resultado cuando `Option Strict` es `Off` .</span><span class="sxs-lookup"><span data-stu-id="187f2-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="187f2-186">Para eliminar la ambigüedad, debe usar el `&` operador en lugar de `+` para la concatenación.</span><span class="sxs-lookup"><span data-stu-id="187f2-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="187f2-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="187f2-187">See also</span></span>

- [<span data-ttu-id="187f2-188">& (operador)</span><span class="sxs-lookup"><span data-stu-id="187f2-188">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="187f2-189">Operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="187f2-189">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="187f2-190">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="187f2-190">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="187f2-191">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="187f2-191">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="187f2-192">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="187f2-192">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="187f2-193">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="187f2-193">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="187f2-194">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="187f2-194">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
