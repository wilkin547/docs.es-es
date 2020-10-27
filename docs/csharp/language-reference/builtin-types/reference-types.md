---
title: Tipos de referencia integrados - referencia de C#
description: Obtenga información sobre los tipos de referencia que tienen palabras clave de C# que puede usar para declararlas.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: c2c03f47babd9ccf87eb60d33b9d65d1a9c82e2e
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223515"
---
# <a name="built-in-reference-types-c-reference"></a><span data-ttu-id="35092-103">Tipos de referencia integrados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="35092-103">Built-in reference types (C# reference)</span></span>

<span data-ttu-id="35092-104">C# tiene un número de tipos de referencia integrados.</span><span class="sxs-lookup"><span data-stu-id="35092-104">C# has a number of built-in reference types.</span></span> <span data-ttu-id="35092-105">Tienen palabras clave u operadores que son sinónimos para un tipo en la biblioteca de .NET.</span><span class="sxs-lookup"><span data-stu-id="35092-105">They have keywords or operators that are synonyms for a type in the .NET library.</span></span>

## <a name="the-object-type"></a><span data-ttu-id="35092-106">El tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="35092-106">The object type</span></span>

<span data-ttu-id="35092-107">El tipo `object` es un alias de <xref:System.Object?displayProperty=nameWithType> en .NET.</span><span class="sxs-lookup"><span data-stu-id="35092-107">The `object` type is an alias for <xref:System.Object?displayProperty=nameWithType> in .NET.</span></span> <span data-ttu-id="35092-108">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="35092-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="35092-109">Puede asignar valores de cualquier tipo a las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="35092-109">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="35092-110">Cualquier variable `object` puede asignarse a su valor predeterminado con el literal `null`.</span><span class="sxs-lookup"><span data-stu-id="35092-110">Any `object` variable can be assigned to its default value using the literal `null`.</span></span> <span data-ttu-id="35092-111">Cuando una variable de un tipo de valor se convierte en objeto, se dice que se aplica la *conversión boxing* .</span><span class="sxs-lookup"><span data-stu-id="35092-111">When a variable of a value type is converted to object, it is said to be *boxed* .</span></span> <span data-ttu-id="35092-112">Cuando una variable de tipo `object` se convierte en un tipo de valor, se dice que se *aplica la conversión unboxing* .</span><span class="sxs-lookup"><span data-stu-id="35092-112">When a variable of type `object` is converted to a value type, it is said to be *unboxed* .</span></span> <span data-ttu-id="35092-113">Para obtener más información, vea [Conversión boxing y unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="35092-113">For more information, see [Boxing and Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span></span>

## <a name="the-string-type"></a><span data-ttu-id="35092-114">Tipo string</span><span class="sxs-lookup"><span data-stu-id="35092-114">The string type</span></span>

<span data-ttu-id="35092-115">El tipo `string` representa una secuencia de cero o más caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="35092-115">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="35092-116">`string` es un alias de <xref:System.String?displayProperty=nameWithType> en .NET.</span><span class="sxs-lookup"><span data-stu-id="35092-116">`string` is an alias for <xref:System.String?displayProperty=nameWithType> in .NET.</span></span>

<span data-ttu-id="35092-117">Aunque `string` es un tipo de referencia, se definen los [operadores de igualdad `==` y `!=`](../operators/equality-operators.md#string-equality) para comparar los valores de los objetos `string`, no las referencias.</span><span class="sxs-lookup"><span data-stu-id="35092-117">Although `string` is a reference type, the [equality operators `==` and `!=`](../operators/equality-operators.md#string-equality) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="35092-118">Esto hace que las pruebas de igualdad entre cadenas sean más intuitivas.</span><span class="sxs-lookup"><span data-stu-id="35092-118">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="35092-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="35092-119">For example:</span></span>

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

<span data-ttu-id="35092-120">Se muestra "True" y luego "False" porque el contenido de las cadenas es equivalente, pero `a` y `b` no hacen referencia a la misma instancia de cadena.</span><span class="sxs-lookup"><span data-stu-id="35092-120">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="35092-121">El [operador +](../operators/addition-operator.md#string-concatenation) concatena cadenas:</span><span class="sxs-lookup"><span data-stu-id="35092-121">The [+ operator](../operators/addition-operator.md#string-concatenation) concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="35092-122">Crea un objeto de cadena que contiene "good morning".</span><span class="sxs-lookup"><span data-stu-id="35092-122">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="35092-123">Las cadenas son *inmutables* : el contenido de un objeto de cadena no se puede modificar una vez creado el objeto, aunque la sintaxis parezca indicar que se puede hacer.</span><span class="sxs-lookup"><span data-stu-id="35092-123">Strings are *immutable* --the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="35092-124">Por ejemplo, al escribir este código, el compilador crea en realidad otro objeto de cadena para almacenar la nueva secuencia de caracteres, y este nuevo objeto se asigna a `b`.</span><span class="sxs-lookup"><span data-stu-id="35092-124">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to `b`.</span></span> <span data-ttu-id="35092-125">La memoria que se había asignado para `b` (cuando contiene la cadena "h") es entonces apto para la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="35092-125">The memory that had been allocated for `b` (when it contained the string "h") is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="35092-126">El  [operador](../operators/member-access-operators.md#indexer-operator-)`[]` puede usarse para el acceso de solo lectura a determinados caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="35092-126">The `[]` [operator](../operators/member-access-operators.md#indexer-operator-) can be used for readonly access to individual characters of a string.</span></span> <span data-ttu-id="35092-127">Los valores válidos comienzan por `0` y deben ser menores que la longitud de la cadena:</span><span class="sxs-lookup"><span data-stu-id="35092-127">Valid index values start at `0` and must be less than the length of the string:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="35092-128">De igual manera, el operador `[]` también puede usarse para recorrer en iteración cada carácter en una cadena:</span><span class="sxs-lookup"><span data-stu-id="35092-128">In similar fashion, the `[]` operator can also be used for iterating over each character in a string:</span></span>

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
```

<span data-ttu-id="35092-129">Los literales de cadena son del tipo `string` y se pueden escribir de dos formas, entre comillas y entre `@`.</span><span class="sxs-lookup"><span data-stu-id="35092-129">String literals are of type `string` and can be written in two forms, quoted and `@`-quoted.</span></span> <span data-ttu-id="35092-130">Los literales de cadena se incluyen entre comillas dobles ("):</span><span class="sxs-lookup"><span data-stu-id="35092-130">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="35092-131">Los literales de cadena pueden contener cualquier literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="35092-131">String literals can contain any character literal.</span></span> <span data-ttu-id="35092-132">Se incluyen secuencias de escape.</span><span class="sxs-lookup"><span data-stu-id="35092-132">Escape sequences are included.</span></span> <span data-ttu-id="35092-133">En el ejemplo siguiente se usa una secuencia de escape `\\` para la barra diagonal inversa, `\u0066` para la letra f y `\n` para la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="35092-133">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
// Output:
// \f
//  F
```

> [!NOTE]
> <span data-ttu-id="35092-134">El código de escape `\udddd` (donde `dddd` es un número de cuatro dígitos) representa el carácter Unicode U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="35092-134">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="35092-135">También se reconocen los códigos de escape Unicode de 8 dígitos: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="35092-135">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="35092-136">[Los literales de cadena textual empiezan](../tokens/verbatim.md) por `@` y también se incluyen entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="35092-136">[Verbatim string literals](../tokens/verbatim.md) start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="35092-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="35092-137">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="35092-138">La ventaja de las cadenas textuales es que las secuencias de escape *no* se procesan, lo que facilita la escritura de, por ejemplo, un nombre de archivo Windows completo:</span><span class="sxs-lookup"><span data-stu-id="35092-138">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified Windows file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="35092-139">Para incluir un signo de comillas dobles en una cadena @-quoted, duplíquelo:</span><span class="sxs-lookup"><span data-stu-id="35092-139">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a><span data-ttu-id="35092-140">Tipo delegate</span><span class="sxs-lookup"><span data-stu-id="35092-140">The delegate type</span></span>

<span data-ttu-id="35092-141">La declaración de un tipo delegado es similar a una firma de método.</span><span class="sxs-lookup"><span data-stu-id="35092-141">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="35092-142">Tiene un valor devuelto y un número cualquiera de parámetros de cualquier tipo:</span><span class="sxs-lookup"><span data-stu-id="35092-142">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

<span data-ttu-id="35092-143">En. NET, los tipos `System.Action` y `System.Func` proporcionan definiciones genéricas para muchos delegados comunes.</span><span class="sxs-lookup"><span data-stu-id="35092-143">In .NET, `System.Action` and `System.Func` types provide generic definitions for many common delegates.</span></span> <span data-ttu-id="35092-144">Es probable que no sea necesario definir nuevos tipos delegados personalizados.</span><span class="sxs-lookup"><span data-stu-id="35092-144">You likely don't need to define new custom delegate types.</span></span> <span data-ttu-id="35092-145">En su lugar, puede crear instancias de los tipos genéricos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="35092-145">Instead, you can create instantiations of the provided generic types.</span></span>

<span data-ttu-id="35092-146">Un `delegate` es un tipo de referencia que puede usarse para encapsular un método con nombre o anónimo.</span><span class="sxs-lookup"><span data-stu-id="35092-146">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="35092-147">Los delegados son similares a los punteros de función en C++; pero son más seguros y proporcionan mayor seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="35092-147">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="35092-148">Para las aplicaciones de delegados, vea [Delegados](../../programming-guide/delegates/index.md) y [Delegados genéricos](../../programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="35092-148">For applications of delegates, see [Delegates](../../programming-guide/delegates/index.md) and [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span> <span data-ttu-id="35092-149">Los delegados son la base de los [eventos](../../programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="35092-149">Delegates are the basis for [Events](../../programming-guide/events/index.md).</span></span> <span data-ttu-id="35092-150">Se pueden crear instancias de un delegado asociándolo a un método con nombre o anónimo.</span><span class="sxs-lookup"><span data-stu-id="35092-150">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span>

<span data-ttu-id="35092-151">Para crear instancias del delegado debe usarse un método o una expresión lambda que tenga un tipo de valor devuelto y parámetros de entrada compatibles.</span><span class="sxs-lookup"><span data-stu-id="35092-151">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="35092-152">Para obtener más información sobre el grado de variación permitida en la firma de método, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="35092-152">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="35092-153">Para el uso con métodos anónimos, el delegado y el código que se van a asociar se declaran juntos.</span><span class="sxs-lookup"><span data-stu-id="35092-153">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span>

## <a name="the-dynamic-type"></a><span data-ttu-id="35092-154">Tipo dynamic</span><span class="sxs-lookup"><span data-stu-id="35092-154">The dynamic type</span></span>

<span data-ttu-id="35092-155">El tipo `dynamic` indica el uso de la variable y las referencias a su comprobación de tipos en el tiempo de compilación de omisión de miembros.</span><span class="sxs-lookup"><span data-stu-id="35092-155">The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking.</span></span> <span data-ttu-id="35092-156">En su lugar, se resuelven estas operaciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35092-156">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="35092-157">El tipo `dynamic` simplifica el acceso a las API de COM como las API de automatización de Office, a API dinámicas como las bibliotecas de IronPython, y a Document Object Model (DOM) HTML.</span><span class="sxs-lookup"><span data-stu-id="35092-157">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="35092-158">El tipo `dynamic` se comporta como el tipo `object` en la mayoría de las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="35092-158">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="35092-159">En concreto, se puede convertir cualquier expresión no NULL para el tipo `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="35092-159">In particular, any non-null expression can be converted to the `dynamic` type.</span></span> <span data-ttu-id="35092-160">El tipo `dynamic` se diferencia de `object` en que el compilador no resuelve o no comprueba el tipo de las operaciones que contienen expresiones de tipo `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="35092-160">The `dynamic` type differs from `object` in that operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="35092-161">El compilador empaqueta información sobre la operación y esa información se usa después para evaluar la operación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35092-161">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="35092-162">Como parte del proceso, las variables de tipo `dynamic` están compiladas en las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="35092-162">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="35092-163">Por consiguiente, el tipo `dynamic` solo existe en tiempo de compilación, no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35092-163">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="35092-164">En el siguiente ejemplo se contrasta una variable de tipo `dynamic` con una variable de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="35092-164">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="35092-165">Para comprobar el tipo de cada variable en tiempo de compilación, coloque el puntero del mouse sobre `dyn` u `obj` en las instrucciones `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="35092-165">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="35092-166">Copie el código siguiente en un editor donde IntelliSense esté disponible.</span><span class="sxs-lookup"><span data-stu-id="35092-166">Copy the following code into an editor where IntelliSense is available.</span></span> <span data-ttu-id="35092-167">IntelliSense muestra **dynamic** para `dyn` y **object** para `obj`.</span><span class="sxs-lookup"><span data-stu-id="35092-167">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="35092-168">Las instrucciones <xref:System.Console.WriteLine%2A> muestran los tipos en tiempo de ejecución de `dyn` y `obj`.</span><span class="sxs-lookup"><span data-stu-id="35092-168">The <xref:System.Console.WriteLine%2A> statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="35092-169">En ese punto, ambos tienen el mismo tipo, entero.</span><span class="sxs-lookup"><span data-stu-id="35092-169">At that point, both have the same type, integer.</span></span> <span data-ttu-id="35092-170">Se produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="35092-170">The following output is produced:</span></span>

```console
System.Int32
System.Int32
```

<span data-ttu-id="35092-171">Para ver la diferencia entre `dyn` y `obj` en tiempo de compilación, agregue las dos líneas siguientes entre las declaraciones y las instrucciones `WriteLine` en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="35092-171">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="35092-172">Un error del compilador se notifica para el intento de suma de un entero y un objeto en la expresión `obj + 3`.</span><span class="sxs-lookup"><span data-stu-id="35092-172">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="35092-173">En cambio, no se notifica ningún error para `dyn + 3`.</span><span class="sxs-lookup"><span data-stu-id="35092-173">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="35092-174">En tiempo de compilación no se comprueba la expresión que contiene `dyn` porque el tipo de `dyn` es `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="35092-174">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

<span data-ttu-id="35092-175">El ejemplo siguiente usa `dynamic` en varias declaraciones.</span><span class="sxs-lookup"><span data-stu-id="35092-175">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="35092-176">El método `Main` también contrasta la comprobación de tipo en tiempo de compilación con la comprobación de tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35092-176">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a><span data-ttu-id="35092-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="35092-177">See also</span></span>

- [<span data-ttu-id="35092-178">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="35092-178">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35092-179">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="35092-179">C# Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="35092-180">Eventos</span><span class="sxs-lookup"><span data-stu-id="35092-180">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="35092-181">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="35092-181">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="35092-182">Procedimientos recomendados para el uso de cadenas</span><span class="sxs-lookup"><span data-stu-id="35092-182">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="35092-183">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="35092-183">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="35092-184">Creación de cadenas</span><span class="sxs-lookup"><span data-stu-id="35092-184">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="35092-185">Operadores de conversión y prueba de tipos</span><span class="sxs-lookup"><span data-stu-id="35092-185">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
- [<span data-ttu-id="35092-186">Procedimiento para convertir de forma segura mediante la coincidencia de patrones y los operadores is y as</span><span class="sxs-lookup"><span data-stu-id="35092-186">How to safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="35092-187">Tutorial: Crear y usar objetos dinámicos (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35092-187">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
