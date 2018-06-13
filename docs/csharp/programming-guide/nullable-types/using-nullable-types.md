---
title: Uso de tipos que aceptan valores NULL (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336926"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="533d2-102">Uso de tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="533d2-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="533d2-103">Los tipos que aceptan valores NULL pueden representar todos los valores de un tipo subyacente y un valor [NULL](../../../csharp/language-reference/keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="533d2-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="533d2-104">Los tipos que aceptan valores NULL se declaran de una de las siguientes dos maneras:</span><span class="sxs-lookup"><span data-stu-id="533d2-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="533d2-105">O bien</span><span class="sxs-lookup"><span data-stu-id="533d2-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="533d2-106">`T` es el tipo subyacente del tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="533d2-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="533d2-107">`T` puede ser cualquier tipo de valor, incluido `struct`; no puede ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="533d2-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="533d2-108">Para tener un ejemplo de cuándo conviene usar un tipo que acepta valores NULL, piense en cómo una variable booleana común puede tener dos valores: true y false.</span><span class="sxs-lookup"><span data-stu-id="533d2-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="533d2-109">No hay ningún valor que signifique "indefinido".</span><span class="sxs-lookup"><span data-stu-id="533d2-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="533d2-110">En muchas aplicaciones de programación, especialmente en las interacciones de bases de datos, puede haber variables con un estado indefinido.</span><span class="sxs-lookup"><span data-stu-id="533d2-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="533d2-111">Por ejemplo, un campo de una base de datos puede contener los valores true o false, pero también puede no contener ningún valor.</span><span class="sxs-lookup"><span data-stu-id="533d2-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="533d2-112">De igual modo, los tipos de referencia se pueden establecer en `null` para indicar que no se inicializan.</span><span class="sxs-lookup"><span data-stu-id="533d2-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="533d2-113">Esta disparidad puede conllevar un esfuerzo extra de programación, con variables adicionales que sirven para almacenar información de estado, el uso de valores especiales, etc.</span><span class="sxs-lookup"><span data-stu-id="533d2-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="533d2-114">El modificador de tipos que aceptan valores NULL permite a C# crear variables de tipo de valor que indican un valor indefinido.</span><span class="sxs-lookup"><span data-stu-id="533d2-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="533d2-115">Ejemplos de tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="533d2-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="533d2-116">Cualquier tipo de valor puede servir de base de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="533d2-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="533d2-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="533d2-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="533d2-118">Miembros de los tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="533d2-118">The Members of Nullable Types</span></span>  
 <span data-ttu-id="533d2-119">Cada instancia de un tipo que acepta valores NULL tiene dos propiedades públicas de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="533d2-119">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="533d2-120">`HasValue` es de tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="533d2-120">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="533d2-121">Se establece en `true` cuando la variable contiene un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="533d2-121">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="533d2-122">`Value` es del mismo tipo que el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="533d2-122">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="533d2-123">Si `HasValue` es `true`, `Value` contiene un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="533d2-123">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="533d2-124">Si `HasValue` es `false`, al acceder a `Value` se generará <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="533d2-124">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="533d2-125">En este ejemplo, el miembro `HasValue` se usa para probar si la variable contiene un valor antes de que intente mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="533d2-125">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 <span data-ttu-id="533d2-126">La comprobación de un valor también se puede realizar como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="533d2-126">Testing for a value can also be done as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a><span data-ttu-id="533d2-127">Conversiones explícitas</span><span class="sxs-lookup"><span data-stu-id="533d2-127">Explicit Conversions</span></span>  
 <span data-ttu-id="533d2-128">Un tipo que acepta valores NULL se puede convertir a un tipo regular, ya sea expresamente con una conversión o por medio de la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="533d2-128">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="533d2-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="533d2-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 <span data-ttu-id="533d2-130">Si se establece una conversión definida por el usuario entre dos tipos de datos, esa misma conversión también se puede usar con las versiones que aceptan valores NULL de dichos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="533d2-130">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="533d2-131">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="533d2-131">Implicit Conversions</span></span>  
 <span data-ttu-id="533d2-132">Una variable de tipo que acepta valores NULL se puede establecer como NULL con la palabra clave `null`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="533d2-132">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 <span data-ttu-id="533d2-133">La conversión de un tipo ordinario a un tipo que acepta valores NULL es implícita.</span><span class="sxs-lookup"><span data-stu-id="533d2-133">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a><span data-ttu-id="533d2-134">Operadores</span><span class="sxs-lookup"><span data-stu-id="533d2-134">Operators</span></span>  
 <span data-ttu-id="533d2-135">Los tipos que aceptan valores NULL también pueden hacer uso de los operadores predefinidos unario y binario, así como de cualquier operador definido por el usuario que exista para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="533d2-135">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="533d2-136">Estos operadores generan un valor NULL si los operandos son NULL; si no, el operador usará el valor contenido para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="533d2-136">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="533d2-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="533d2-137">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 <span data-ttu-id="533d2-138">Cuando realice comparaciones con tipos que aceptan valores NULL, si el valor de uno de los tipos que aceptan valores NULL es NULL y el otro no lo es, todas las comparaciones se evalúan como `false` excepto `!=` (no igual a).</span><span class="sxs-lookup"><span data-stu-id="533d2-138">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="533d2-139">Es importante no dar por supuesto que, como una determinada comparación devuelve `false`, el caso contrario devolverá `true`.</span><span class="sxs-lookup"><span data-stu-id="533d2-139">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="533d2-140">En el siguiente ejemplo, 10 no es mayor, menor ni igual que NULL.</span><span class="sxs-lookup"><span data-stu-id="533d2-140">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="533d2-141">Solo `num1 != num2` evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="533d2-141">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 <span data-ttu-id="533d2-142">Una comparación de igualdad entre dos tipos que aceptan valores NULL donde ambos son NULL se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="533d2-142">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="533d2-143">Operador</span><span class="sxs-lookup"><span data-stu-id="533d2-143">The ??</span></span> <span data-ttu-id="533d2-144">"??"</span><span class="sxs-lookup"><span data-stu-id="533d2-144">Operator</span></span>  
 <span data-ttu-id="533d2-145">El operador `??` define un valor predeterminado que se devuelve cuando un tipo que acepta valores NULL se asigna a un tipo distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="533d2-145">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 <span data-ttu-id="533d2-146">Este operador se puede usar también con varios tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="533d2-146">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="533d2-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="533d2-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a><span data-ttu-id="533d2-148">Tipo bool?</span><span class="sxs-lookup"><span data-stu-id="533d2-148">The bool? type</span></span>  
 <span data-ttu-id="533d2-149">El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) y [NULL](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="533d2-149">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="533d2-150">Para obtener más información sobre cómo convertir un tipo bool? a un tipo bool, vea [Cómo: Convertir con seguridad de bool? a bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="533d2-150">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="533d2-151">Los valores booleanos que aceptan valores NULL son como el tipo de variable booleano que se usa en SQL.</span><span class="sxs-lookup"><span data-stu-id="533d2-151">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="533d2-152">Para asegurarse de que los resultados generados por los operadores `&` y `|` sean coherentes con el tipo booleano de tres valores en SQL, se proporcionan los siguientes operadores predefinidos:</span><span class="sxs-lookup"><span data-stu-id="533d2-152">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="533d2-153">Los resultados de estos operadores se muestran en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="533d2-153">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="533d2-154">X</span><span class="sxs-lookup"><span data-stu-id="533d2-154">X</span></span>|<span data-ttu-id="533d2-155">y</span><span class="sxs-lookup"><span data-stu-id="533d2-155">y</span></span>|<span data-ttu-id="533d2-156">x e y</span><span class="sxs-lookup"><span data-stu-id="533d2-156">x&y</span></span>|<span data-ttu-id="533d2-157">x | y</span><span class="sxs-lookup"><span data-stu-id="533d2-157">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="533d2-158">true</span><span class="sxs-lookup"><span data-stu-id="533d2-158">true</span></span>|<span data-ttu-id="533d2-159">true</span><span class="sxs-lookup"><span data-stu-id="533d2-159">true</span></span>|<span data-ttu-id="533d2-160">true</span><span class="sxs-lookup"><span data-stu-id="533d2-160">true</span></span>|<span data-ttu-id="533d2-161">true</span><span class="sxs-lookup"><span data-stu-id="533d2-161">true</span></span>|  
|<span data-ttu-id="533d2-162">true</span><span class="sxs-lookup"><span data-stu-id="533d2-162">true</span></span>|<span data-ttu-id="533d2-163">False</span><span class="sxs-lookup"><span data-stu-id="533d2-163">false</span></span>|<span data-ttu-id="533d2-164">false</span><span class="sxs-lookup"><span data-stu-id="533d2-164">false</span></span>|<span data-ttu-id="533d2-165">true</span><span class="sxs-lookup"><span data-stu-id="533d2-165">true</span></span>|  
|<span data-ttu-id="533d2-166">true</span><span class="sxs-lookup"><span data-stu-id="533d2-166">true</span></span>|<span data-ttu-id="533d2-167">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-167">null</span></span>|<span data-ttu-id="533d2-168">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-168">null</span></span>|<span data-ttu-id="533d2-169">true</span><span class="sxs-lookup"><span data-stu-id="533d2-169">true</span></span>|  
|<span data-ttu-id="533d2-170">False</span><span class="sxs-lookup"><span data-stu-id="533d2-170">false</span></span>|<span data-ttu-id="533d2-171">true</span><span class="sxs-lookup"><span data-stu-id="533d2-171">true</span></span>|<span data-ttu-id="533d2-172">False</span><span class="sxs-lookup"><span data-stu-id="533d2-172">false</span></span>|<span data-ttu-id="533d2-173">true</span><span class="sxs-lookup"><span data-stu-id="533d2-173">true</span></span>|  
|<span data-ttu-id="533d2-174">False</span><span class="sxs-lookup"><span data-stu-id="533d2-174">false</span></span>|<span data-ttu-id="533d2-175">False</span><span class="sxs-lookup"><span data-stu-id="533d2-175">false</span></span>|<span data-ttu-id="533d2-176">False</span><span class="sxs-lookup"><span data-stu-id="533d2-176">false</span></span>|<span data-ttu-id="533d2-177">False</span><span class="sxs-lookup"><span data-stu-id="533d2-177">false</span></span>|  
|<span data-ttu-id="533d2-178">False</span><span class="sxs-lookup"><span data-stu-id="533d2-178">false</span></span>|<span data-ttu-id="533d2-179">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-179">null</span></span>|<span data-ttu-id="533d2-180">False</span><span class="sxs-lookup"><span data-stu-id="533d2-180">false</span></span>|<span data-ttu-id="533d2-181">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-181">null</span></span>|  
|<span data-ttu-id="533d2-182">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-182">null</span></span>|<span data-ttu-id="533d2-183">true</span><span class="sxs-lookup"><span data-stu-id="533d2-183">true</span></span>|<span data-ttu-id="533d2-184">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-184">null</span></span>|<span data-ttu-id="533d2-185">true</span><span class="sxs-lookup"><span data-stu-id="533d2-185">true</span></span>|  
|<span data-ttu-id="533d2-186">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-186">null</span></span>|<span data-ttu-id="533d2-187">False</span><span class="sxs-lookup"><span data-stu-id="533d2-187">false</span></span>|<span data-ttu-id="533d2-188">False</span><span class="sxs-lookup"><span data-stu-id="533d2-188">false</span></span>|<span data-ttu-id="533d2-189">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-189">null</span></span>|  
|<span data-ttu-id="533d2-190">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-190">null</span></span>|<span data-ttu-id="533d2-191">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-191">null</span></span>|<span data-ttu-id="533d2-192">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-192">null</span></span>|<span data-ttu-id="533d2-193">nulo</span><span class="sxs-lookup"><span data-stu-id="533d2-193">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="533d2-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="533d2-194">See Also</span></span>  
 [<span data-ttu-id="533d2-195">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="533d2-195">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="533d2-196">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="533d2-196">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="533d2-197">Aplicar la conversión boxing a tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="533d2-197">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [<span data-ttu-id="533d2-198">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="533d2-198">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
