---
title: "Uso de tipos que aceptan valores NULL (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0721d9f60abc4e158135d6b050953b3e63ab8cb5
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="844cc-102">Uso de tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="844cc-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="844cc-103">Los tipos que aceptan valores NULL pueden representar todos los valores de un tipo subyacente y un valor [NULL](../../../csharp/language-reference/keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="844cc-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="844cc-104">Los tipos que aceptan valores NULL se declaran de una de las siguientes dos maneras:</span><span class="sxs-lookup"><span data-stu-id="844cc-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="844cc-105">O bien</span><span class="sxs-lookup"><span data-stu-id="844cc-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="844cc-106">`T` es el tipo subyacente del tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="844cc-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="844cc-107">`T` puede ser cualquier tipo de valor, incluido `struct`; no puede ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="844cc-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="844cc-108">Para tener un ejemplo de cuándo conviene usar un tipo que acepta valores NULL, piense en cómo una variable booleana común puede tener dos valores: true y false.</span><span class="sxs-lookup"><span data-stu-id="844cc-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="844cc-109">No hay ningún valor que signifique "indefinido".</span><span class="sxs-lookup"><span data-stu-id="844cc-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="844cc-110">En muchas aplicaciones de programación, especialmente en las interacciones de bases de datos, puede haber variables con un estado indefinido.</span><span class="sxs-lookup"><span data-stu-id="844cc-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="844cc-111">Por ejemplo, un campo de una base de datos puede contener los valores true o false, pero también puede no contener ningún valor.</span><span class="sxs-lookup"><span data-stu-id="844cc-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="844cc-112">De igual modo, los tipos de referencia se pueden establecer en `null` para indicar que no se inicializan.</span><span class="sxs-lookup"><span data-stu-id="844cc-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="844cc-113">Esta disparidad puede conllevar un esfuerzo extra de programación, con variables adicionales que sirven para almacenar información de estado, el uso de valores especiales, etc.</span><span class="sxs-lookup"><span data-stu-id="844cc-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="844cc-114">El modificador de tipos que aceptan valores NULL permite a C# crear variables de tipo de valor que indican un valor indefinido.</span><span class="sxs-lookup"><span data-stu-id="844cc-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="844cc-115">Ejemplos de tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="844cc-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="844cc-116">Cualquier tipo de valor puede servir de base de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="844cc-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="844cc-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="844cc-117">For example:</span></span>  
  
 <span data-ttu-id="844cc-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span></span>  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="844cc-119">Miembros de los tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="844cc-119">The Members of Nullable Types</span></span>  
 <span data-ttu-id="844cc-120">Cada instancia de un tipo que acepta valores NULL tiene dos propiedades públicas de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="844cc-120">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="844cc-121">`HasValue` es de tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="844cc-121">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="844cc-122">Se establece en `true` cuando la variable contiene un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="844cc-122">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="844cc-123">`Value` es del mismo tipo que el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="844cc-123">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="844cc-124">Si `HasValue` es `true`, `Value` contiene un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="844cc-124">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="844cc-125">Si `HasValue` es `false`, al acceder a `Value` se generará <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="844cc-125">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="844cc-126">En este ejemplo, el miembro `HasValue` se usa para probar si la variable contiene un valor antes de que intente mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="844cc-126">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 <span data-ttu-id="844cc-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span></span>  
  
 <span data-ttu-id="844cc-128">La comprobación de un valor también se puede realizar como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="844cc-128">Testing for a value can also be done as in the following example:</span></span>  
  
 <span data-ttu-id="844cc-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span></span>  
  
## <a name="explicit-conversions"></a><span data-ttu-id="844cc-130">Conversiones explícitas</span><span class="sxs-lookup"><span data-stu-id="844cc-130">Explicit Conversions</span></span>  
 <span data-ttu-id="844cc-131">Un tipo que acepta valores NULL se puede convertir a un tipo regular, ya sea expresamente con una conversión o por medio de la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="844cc-131">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="844cc-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="844cc-132">For example:</span></span>  
  
 <span data-ttu-id="844cc-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span></span>  
  
 <span data-ttu-id="844cc-134">Si se establece una conversión definida por el usuario entre dos tipos de datos, esa misma conversión también se puede usar con las versiones que aceptan valores NULL de dichos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="844cc-134">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="844cc-135">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="844cc-135">Implicit Conversions</span></span>  
 <span data-ttu-id="844cc-136">Una variable de tipo que acepta valores NULL se puede establecer como NULL con la palabra clave `null`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="844cc-136">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="844cc-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span></span>  
  
 <span data-ttu-id="844cc-138">La conversión de un tipo ordinario a un tipo que acepta valores NULL es implícita.</span><span class="sxs-lookup"><span data-stu-id="844cc-138">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 <span data-ttu-id="844cc-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span></span>  
  
## <a name="operators"></a><span data-ttu-id="844cc-140">Operadores</span><span class="sxs-lookup"><span data-stu-id="844cc-140">Operators</span></span>  
 <span data-ttu-id="844cc-141">Los tipos que aceptan valores NULL también pueden hacer uso de los operadores predefinidos unario y binario, así como de cualquier operador definido por el usuario que exista para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="844cc-141">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="844cc-142">Estos operadores generan un valor NULL si los operandos son NULL; si no, el operador usará el valor contenido para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="844cc-142">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="844cc-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="844cc-143">For example:</span></span>  
  
 <span data-ttu-id="844cc-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span></span>  
  
 <span data-ttu-id="844cc-145">Cuando realice comparaciones con tipos que aceptan valores NULL, si el valor de uno de los tipos que aceptan valores NULL es NULL y el otro no lo es, todas las comparaciones se evalúan como `false` excepto `!=` (no igual a).</span><span class="sxs-lookup"><span data-stu-id="844cc-145">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="844cc-146">Es importante no dar por supuesto que, como una determinada comparación devuelve `false`, el caso contrario devolverá `true`.</span><span class="sxs-lookup"><span data-stu-id="844cc-146">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="844cc-147">En el siguiente ejemplo, 10 no es mayor, menor ni igual que NULL.</span><span class="sxs-lookup"><span data-stu-id="844cc-147">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="844cc-148">Solo `num1 != num2` evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="844cc-148">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 <span data-ttu-id="844cc-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span></span>  
  
 <span data-ttu-id="844cc-150">Una comparación de igualdad entre dos tipos que aceptan valores NULL donde ambos son NULL se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="844cc-150">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="844cc-151">Operador</span><span class="sxs-lookup"><span data-stu-id="844cc-151">The ??</span></span> <span data-ttu-id="844cc-152">"??"</span><span class="sxs-lookup"><span data-stu-id="844cc-152">Operator</span></span>  
 <span data-ttu-id="844cc-153">El operador `??` define un valor predeterminado que se devuelve cuando un tipo que acepta valores NULL se asigna a un tipo distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="844cc-153">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 <span data-ttu-id="844cc-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span></span>  
  
 <span data-ttu-id="844cc-155">Este operador se puede usar también con varios tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="844cc-155">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="844cc-156">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="844cc-156">For example:</span></span>  
  
 <span data-ttu-id="844cc-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="844cc-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span></span>  
  
## <a name="the-bool-type"></a><span data-ttu-id="844cc-158">Tipo bool?</span><span class="sxs-lookup"><span data-stu-id="844cc-158">The bool? type</span></span>  
 <span data-ttu-id="844cc-159">El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) y [NULL](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="844cc-159">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="844cc-160">Para obtener más información sobre cómo convertir un tipo bool? a un tipo bool, vea [Cómo: Convertir con seguridad de bool? a bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="844cc-160">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="844cc-161">Los valores booleanos que aceptan valores NULL son como el tipo de variable booleano que se usa en SQL.</span><span class="sxs-lookup"><span data-stu-id="844cc-161">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="844cc-162">Para asegurarse de que los resultados generados por los operadores `&` y `|` sean coherentes con el tipo booleano de tres valores en SQL, se proporcionan los siguientes operadores predefinidos:</span><span class="sxs-lookup"><span data-stu-id="844cc-162">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="844cc-163">Los resultados de estos operadores se muestran en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="844cc-163">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="844cc-164">X</span><span class="sxs-lookup"><span data-stu-id="844cc-164">X</span></span>|<span data-ttu-id="844cc-165">y</span><span class="sxs-lookup"><span data-stu-id="844cc-165">y</span></span>|<span data-ttu-id="844cc-166">x e y</span><span class="sxs-lookup"><span data-stu-id="844cc-166">x&y</span></span>|<span data-ttu-id="844cc-167">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="844cc-167">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="844cc-168">true</span><span class="sxs-lookup"><span data-stu-id="844cc-168">true</span></span>|<span data-ttu-id="844cc-169">true</span><span class="sxs-lookup"><span data-stu-id="844cc-169">true</span></span>|<span data-ttu-id="844cc-170">true</span><span class="sxs-lookup"><span data-stu-id="844cc-170">true</span></span>|<span data-ttu-id="844cc-171">true</span><span class="sxs-lookup"><span data-stu-id="844cc-171">true</span></span>|  
|<span data-ttu-id="844cc-172">true</span><span class="sxs-lookup"><span data-stu-id="844cc-172">true</span></span>|<span data-ttu-id="844cc-173">false</span><span class="sxs-lookup"><span data-stu-id="844cc-173">false</span></span>|<span data-ttu-id="844cc-174">false</span><span class="sxs-lookup"><span data-stu-id="844cc-174">false</span></span>|<span data-ttu-id="844cc-175">true</span><span class="sxs-lookup"><span data-stu-id="844cc-175">true</span></span>|  
|<span data-ttu-id="844cc-176">true</span><span class="sxs-lookup"><span data-stu-id="844cc-176">true</span></span>|<span data-ttu-id="844cc-177">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-177">null</span></span>|<span data-ttu-id="844cc-178">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-178">null</span></span>|<span data-ttu-id="844cc-179">true</span><span class="sxs-lookup"><span data-stu-id="844cc-179">true</span></span>|  
|<span data-ttu-id="844cc-180">false</span><span class="sxs-lookup"><span data-stu-id="844cc-180">false</span></span>|<span data-ttu-id="844cc-181">true</span><span class="sxs-lookup"><span data-stu-id="844cc-181">true</span></span>|<span data-ttu-id="844cc-182">false</span><span class="sxs-lookup"><span data-stu-id="844cc-182">false</span></span>|<span data-ttu-id="844cc-183">true</span><span class="sxs-lookup"><span data-stu-id="844cc-183">true</span></span>|  
|<span data-ttu-id="844cc-184">false</span><span class="sxs-lookup"><span data-stu-id="844cc-184">false</span></span>|<span data-ttu-id="844cc-185">false</span><span class="sxs-lookup"><span data-stu-id="844cc-185">false</span></span>|<span data-ttu-id="844cc-186">false</span><span class="sxs-lookup"><span data-stu-id="844cc-186">false</span></span>|<span data-ttu-id="844cc-187">false</span><span class="sxs-lookup"><span data-stu-id="844cc-187">false</span></span>|  
|<span data-ttu-id="844cc-188">false</span><span class="sxs-lookup"><span data-stu-id="844cc-188">false</span></span>|<span data-ttu-id="844cc-189">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-189">null</span></span>|<span data-ttu-id="844cc-190">false</span><span class="sxs-lookup"><span data-stu-id="844cc-190">false</span></span>|<span data-ttu-id="844cc-191">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-191">null</span></span>|  
|<span data-ttu-id="844cc-192">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-192">null</span></span>|<span data-ttu-id="844cc-193">true</span><span class="sxs-lookup"><span data-stu-id="844cc-193">true</span></span>|<span data-ttu-id="844cc-194">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-194">null</span></span>|<span data-ttu-id="844cc-195">true</span><span class="sxs-lookup"><span data-stu-id="844cc-195">true</span></span>|  
|<span data-ttu-id="844cc-196">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-196">null</span></span>|<span data-ttu-id="844cc-197">false</span><span class="sxs-lookup"><span data-stu-id="844cc-197">false</span></span>|<span data-ttu-id="844cc-198">false</span><span class="sxs-lookup"><span data-stu-id="844cc-198">false</span></span>|<span data-ttu-id="844cc-199">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-199">null</span></span>|  
|<span data-ttu-id="844cc-200">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-200">null</span></span>|<span data-ttu-id="844cc-201">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-201">null</span></span>|<span data-ttu-id="844cc-202">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-202">null</span></span>|<span data-ttu-id="844cc-203">nulo</span><span class="sxs-lookup"><span data-stu-id="844cc-203">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="844cc-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="844cc-204">See Also</span></span>  
 <span data-ttu-id="844cc-205">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="844cc-205">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="844cc-206">[Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="844cc-206">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="844cc-207">[Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="844cc-207">[Boxing Nullable Types](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span></span>  
 [<span data-ttu-id="844cc-208">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="844cc-208">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

