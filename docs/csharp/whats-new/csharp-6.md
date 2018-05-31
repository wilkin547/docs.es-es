---
title: Novedades de C# 6 - Guía de C#
description: Obtenga información sobre las nuevas características de la versión 6 de C#
ms.date: 09/22/2016
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: c23d4f45441451fbf8a2ad2f939bdb1ed6144154
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
ms.locfileid: "34483494"
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="5d8c6-103">Novedades de C# 6</span><span class="sxs-lookup"><span data-stu-id="5d8c6-103">What's New in C# 6</span></span>

<span data-ttu-id="5d8c6-104">La versión 6.0 de C# incluye muchas características que mejoran la productividad para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-104">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="5d8c6-105">Estas son algunas de las características de esta versión:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-105">Features in this release include:</span></span>

* <span data-ttu-id="5d8c6-106">[Propiedades automáticas de solo lectura](#read-only-auto-properties):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-106">[Read-only Auto-properties](#read-only-auto-properties):</span></span>
    - <span data-ttu-id="5d8c6-107">Se pueden crear propiedades automáticas de solo lectura que solo se puedan establecer en los constructores.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-107">You can create read-only auto-properties that can be set only in constructors.</span></span>
* <span data-ttu-id="5d8c6-108">[Inicializadores de propiedades automáticas](#auto-property-initializers):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-108">[Auto-Property Initializers](#auto-property-initializers):</span></span>
    - <span data-ttu-id="5d8c6-109">Se pueden escribir expresiones de inicialización para establecer el valor inicial de una propiedad automática.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-109">You can write initialization expressions to set the initial value of an auto-property.</span></span>
* <span data-ttu-id="5d8c6-110">[Miembros de función con cuerpos de expresión](#expression-bodied-function-members):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-110">[Expression-bodied function members](#expression-bodied-function-members):</span></span>
    - <span data-ttu-id="5d8c6-111">Se pueden crear métodos de una línea mediante expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-111">You can author one-line methods using lambda expressions.</span></span>
* <span data-ttu-id="5d8c6-112">[using static](#using-static):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-112">[using static](#using-static):</span></span>
    - <span data-ttu-id="5d8c6-113">Se pueden importar todos los métodos de una clase única al espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-113">You can import all the methods of a single class into the current namespace.</span></span>
* <span data-ttu-id="5d8c6-114">[Null: operadores condicionales](#null-conditional-operators):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-114">[Null - conditional operators](#null-conditional-operators):</span></span>
    - <span data-ttu-id="5d8c6-115">Se puede obtener acceso de forma concisa y segura a los miembros de un objeto mientras continúa la comprobación de NULL con el operador condicional NULL.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-115">You can concisely and safely access members of an object while still checking for null with the null conditional operator.</span></span>
* <span data-ttu-id="5d8c6-116">[Interpolación de cadenas](#string-interpolation):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-116">[String Interpolation](#string-interpolation):</span></span>
    - <span data-ttu-id="5d8c6-117">Se pueden escribir expresiones de formato de cadena mediante expresiones insertadas en lugar de argumentos posicionales.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-117">You can write string formatting expressions using inline expressions instead of positional arguments.</span></span>
* <span data-ttu-id="5d8c6-118">[Filtros de excepciones](#exception-filters):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-118">[Exception filters](#exception-filters):</span></span>
    - <span data-ttu-id="5d8c6-119">Se pueden detectar expresiones basadas en propiedades de la excepción o en otro estado del programa.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-119">You can catch expressions based on properties of the exception or other program state.</span></span> 
* <span data-ttu-id="5d8c6-120">[Expresiones nameof](#nameof-expressions):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-120">[nameof Expressions](#nameof-expressions):</span></span>
    - <span data-ttu-id="5d8c6-121">Se puede permitir que el compilador genere las representaciones de cadena de símbolos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-121">You can let the compiler generate string representations of symbols.</span></span>
* <span data-ttu-id="5d8c6-122">[await en bloques catch y finally](#await-in-catch-and-finally-blocks):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-122">[await in catch and finally blocks](#await-in-catch-and-finally-blocks):</span></span>
    - <span data-ttu-id="5d8c6-123">Se pueden usar expresiones `await` en ubicaciones que previamente no las permitían.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-123">You can use `await` expressions in locations that previously disallowed them.</span></span>
* <span data-ttu-id="5d8c6-124">[Inicializadores de índice](#index-initializers):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-124">[index initializers](#index-initializers):</span></span>
    - <span data-ttu-id="5d8c6-125">Se pueden crear expresiones de inicialización para contenedores asociativos y también para contenedores de secuencias.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-125">You can author initialization expressions for associative containers as well as sequence containers.</span></span>
* <span data-ttu-id="5d8c6-126">[Métodos de extensión para inicializadores de colección](#extension-add-methods-in-collection-initializers):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-126">[Extension methods for collection initializers](#extension-add-methods-in-collection-initializers):</span></span>
    - <span data-ttu-id="5d8c6-127">Los inicializadores de colección pueden basarse en métodos de extensión accesibles, además de métodos miembro.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-127">Collection initializers can rely on accessible extension methods, in addition to member methods.</span></span>
* <span data-ttu-id="5d8c6-128">[Mejoras en la resolución de sobrecarga](#improved-overload-resolution):</span><span class="sxs-lookup"><span data-stu-id="5d8c6-128">[Improved overload resolution](#improved-overload-resolution):</span></span>
    - <span data-ttu-id="5d8c6-129">Algunas construcciones que previamente generaban llamadas de método ambiguas ahora se resuelven correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-129">Some constructs that previously generated ambiguous method calls now resolve correctly.</span></span>

<span data-ttu-id="5d8c6-130">El efecto general de estas características es que se escribe código más conciso y legible.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-130">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="5d8c6-131">La sintaxis contiene menos complejidad para muchas de las prácticas habituales.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-131">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="5d8c6-132">Es más fácil ver la intención del diseño con menos complejidad.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-132">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="5d8c6-133">Aprender bien estas características le permitirá ser más productivo, escribir código más legible y concentrarse más en las características principales que en las construcciones del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-133">Learn these features well, and you'll be more productive, write more readable code, and concentrate more on your core features than on the constructs of the language.</span></span>

<span data-ttu-id="5d8c6-134">En el resto de este tema se proporcionan detalles sobre cada una de estas características.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-134">The remainder of this topic provides details on each of these features.</span></span>

## <a name="auto-property-enhancements"></a><span data-ttu-id="5d8c6-135">Mejoras de propiedades automáticas</span><span class="sxs-lookup"><span data-stu-id="5d8c6-135">Auto-Property enhancements</span></span> 

<span data-ttu-id="5d8c6-136">La sintaxis de las propiedades implementadas automáticamente (normalmente denominadas "propiedades automáticas") facilitó la creación de propiedades que tenían descriptores de acceso get y set sencillos:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-136">The syntax for automatically implemented properties (usually referred to as 'auto-properties') made it very easy to create properties that had simple get and set accessors:</span></span>

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

<span data-ttu-id="5d8c6-137">Pero esta sintaxis simple limitaba los tipos de diseños que se podían admitir mediante las propiedades automáticas.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-137">However, this simple syntax limited the kinds of designs you could support using auto-properties.</span></span> <span data-ttu-id="5d8c6-138">C# 6 mejora las capacidades de las propiedades automáticas para que se puedan usar en más escenarios.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-138">C# 6 improves the auto-properties capabilities so that you can use them in more scenarios.</span></span> <span data-ttu-id="5d8c6-139">No será necesario recurrir con tanta frecuencia a la sintaxis más detallada de la declaración y manipulación del campo de respaldo a mano.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-139">You won't need to fall back on the more verbose syntax of declaring and manipulating the backing field by hand so often.</span></span>

<span data-ttu-id="5d8c6-140">La nueva sintaxis está dirigida a escenarios para propiedades de solo lectura y a la inicialización del almacenamiento de variables detrás de una propiedad automática.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-140">The new syntax addresses scenarios for read-only properties, and for initializing the variable storage behind an auto-property.</span></span>

### <a name="read-only-auto-properties"></a><span data-ttu-id="5d8c6-141">Propiedades automáticas de solo lectura</span><span class="sxs-lookup"><span data-stu-id="5d8c6-141">Read-only auto-properties</span></span>

<span data-ttu-id="5d8c6-142">*Las propiedades automáticas de solo lectura* proporcionan una sintaxis más concisa para crear tipos inmutables.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-142">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="5d8c6-143">Lo más cerca que se podía llegar a los tipos inmutables en versiones anteriores de C# era declarar establecedores privados:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-143">The closest you could get to immutable types in earlier versions of C# was to declare private setters:</span></span>

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
<span data-ttu-id="5d8c6-144">Con esta sintaxis, el compilador no garantiza que el tipo sea realmente inmutable.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-144">Using this syntax, the compiler doesn't ensure that the type really is immutable.</span></span> <span data-ttu-id="5d8c6-145">Solo exige que las propiedades `FirstName` y `LastName` no se modifiquen desde ningún código fuera de la clase.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-145">It only enforces that the `FirstName` and `LastName` properties are not modified from any code outside the class.</span></span>

<span data-ttu-id="5d8c6-146">Las propiedades automáticas de solo lectura habilitan el comportamiento real de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-146">Read-only auto-properties enable true read-only behavior.</span></span> <span data-ttu-id="5d8c6-147">La propiedad automática se declara solo con un descriptor de acceso get:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-147">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="5d8c6-148">Las propiedades `FirstName` y `LastName` solo se pueden establecer en el cuerpo de un constructor:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-148">The `FirstName` and `LastName` properties can be set only in the body of a constructor:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="5d8c6-149">Intentar establecer `LastName` en otro método genera un error de compilación `CS0200`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-149">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

<span data-ttu-id="5d8c6-150">Esta característica habilita la compatibilidad del lenguaje real para crear tipos inmutables y usar la sintaxis de propiedades automáticas más concisa y cómoda.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-150">This feature enables true language support for creating immutable types and using the more concise and convenient auto-property syntax.</span></span>

### <a name="auto-property-initializers"></a><span data-ttu-id="5d8c6-151">Inicializadores de propiedades automáticas</span><span class="sxs-lookup"><span data-stu-id="5d8c6-151">Auto-Property Initializers</span></span>

<span data-ttu-id="5d8c6-152">Los *inicializadores de propiedades automáticas* permiten declarar el valor inicial de una propiedad automática como parte de la declaración de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-152">*Auto-Property Initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>  <span data-ttu-id="5d8c6-153">En versiones anteriores, estas propiedades debían tener establecedores y era necesario usar ese establecedor para inicializar el almacenamiento de datos usado por el campo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-153">In earlier versions, these properties would need to have setters and you would need to use that setter to initialize the data storage used by the backing field.</span></span> <span data-ttu-id="5d8c6-154">Considere esta clase para un alumno que contiene el nombre y una lista de las notas del alumno:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-154">Consider this class for a student that contains the name and a list of the student's grades:</span></span>

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
<span data-ttu-id="5d8c6-155">A medida que esta clase crece, se pueden incluir otros constructores.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-155">As this class grows, you may include other constructors.</span></span> <span data-ttu-id="5d8c6-156">Cada constructor debe inicializar este campo o se producirán errores.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-156">Each constructor needs to initialize this field, or you'll introduce errors.</span></span>

<span data-ttu-id="5d8c6-157">C# 6 le permite asignar un valor inicial para el almacenamiento usado por una propiedad automática en la declaración de la propiedad automática:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-157">C# 6 enables you to assign an initial value for the storage used by an auto-property in the auto-property declaration:</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="5d8c6-158">El miembro `Grades` se inicializa cuando se declara.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-158">The `Grades` member is initialized where it is declared.</span></span> <span data-ttu-id="5d8c6-159">Eso hace que sea más fácil realizar la inicialización exactamente una sola vez.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-159">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="5d8c6-160">La inicialización es parte de la declaración de la propiedad, lo que facilita igualar la asignación de almacenamiento con la interfaz pública para objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-160">The initialization is part of the property declaration, making it easier to equate the storage allocation with public interface for `Student` objects.</span></span>

<span data-ttu-id="5d8c6-161">Los inicializadores de propiedad se pueden usar con propiedades de lectura y escritura, y también con propiedades de solo lectura, como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-161">Property Initializers can be used with read/write properties as well as read-only properties, as shown here.</span></span>

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a><span data-ttu-id="5d8c6-162">Miembros de función con cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="5d8c6-162">Expression-bodied function members</span></span>

<span data-ttu-id="5d8c6-163">El cuerpo de muchos miembros que se escriben consta de una sola instrucción que se puede representar como una expresión.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-163">The body of a lot of members that we write consist of only one statement that can be represented as an expression.</span></span> <span data-ttu-id="5d8c6-164">Se puede reducir esa sintaxis escribiendo en su lugar un miembro con cuerpo de expresión.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-164">You can reduce that syntax by writing an expression-bodied member instead.</span></span> <span data-ttu-id="5d8c6-165">Funciona para métodos y propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-165">It works for methods and read-only properties.</span></span> <span data-ttu-id="5d8c6-166">Por ejemplo, un reemplazo de `ToString()` suele ser un excelente candidato:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-166">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="5d8c6-167">También se pueden usar miembros con cuerpo de expresión en propiedades de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-167">You can also use expression-bodied members in read-only properties as well:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a><span data-ttu-id="5d8c6-168">uso de versión estática</span><span class="sxs-lookup"><span data-stu-id="5d8c6-168">using static</span></span>

<span data-ttu-id="5d8c6-169">La mejora *using static* permite importar los métodos estáticos de una sola clase.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-169">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="5d8c6-170">Anteriormente, la instrucción `using` importaba todos los tipos en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-170">Previously, the `using` statement imported all types in a namespace.</span></span> 

<span data-ttu-id="5d8c6-171">A menudo, se usan los métodos estáticos de una clase a lo largo del código.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-171">Often we use a class' static methods throughout our code.</span></span> <span data-ttu-id="5d8c6-172">Escribir repetidamente el nombre de clase puede oscurecer el significado del código.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-172">Repeatedly typing the class name can obscure the meaning of your code.</span></span> <span data-ttu-id="5d8c6-173">Un ejemplo común es cuando se escriben clases que realizan muchos cálculos numéricos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-173">A common example is when you write classes that perform many numeric calculations.</span></span>
<span data-ttu-id="5d8c6-174">El código se llenará de <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> y otras llamadas a métodos diferentes en la clase <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-174">Your code will be littered with <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> and other calls to different methods in the <xref:System.Math> class.</span></span> <span data-ttu-id="5d8c6-175">La nueva sintaxis `using static` puede hacer que estas clases sean mucho más fáciles de leer.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-175">The new `using static` syntax can make these classes much cleaner to read.</span></span> <span data-ttu-id="5d8c6-176">Se especifica la clase que se está usando:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-176">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="5d8c6-177">Y ahora, se puede usar cualquier método estático de la clase <xref:System.Math> sin calificar la clase <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-177">And now, you can use any static method in the <xref:System.Math> class without qualifying the <xref:System.Math> class.</span></span> <span data-ttu-id="5d8c6-178">La clase <xref:System.Math> es un excelente caso de uso para esta característica porque no contiene ningún método de instancia.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-178">The <xref:System.Math> class is a great use case for this feature because it does not contain any instance methods.</span></span> <span data-ttu-id="5d8c6-179">También se puede usar `using static` para importar los métodos estáticos de una clase para una clase que tiene métodos estáticos y de instancia.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-179">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="5d8c6-180">Uno de los ejemplos más útiles es <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-180">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="5d8c6-181">Se debe usar el nombre de clase completo, `System.String`, en una instrucción static using.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-181">You must use the fully qualified class name, `System.String` in a static using statement.</span></span> <span data-ttu-id="5d8c6-182">No se puede usar la palabra clave `string` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-182">You cannot use the `string` keyword instead.</span></span> 

<span data-ttu-id="5d8c6-183">Ahora se puede llamar a los métodos estáticos definidos en la clase <xref:System.String> sin calificar esos métodos como miembros de la clase:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-183">You can now call static methods defined in the <xref:System.String> class without qualifying those methods as members of that class:</span></span>

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

<span data-ttu-id="5d8c6-184">La característica `static using` y los métodos de extensión interactúan de formas interesantes y el diseño del lenguaje incluye algunas reglas dedicadas específicamente a esas interacciones.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-184">The `static using` feature and extension methods interact in interesting ways, and the language design included some rules that specifically address those interactions.</span></span> <span data-ttu-id="5d8c6-185">El objetivo es minimizar las posibilidades de cambios bruscos en códigos base existentes, incluido el suyo.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-185">The goal is to minimize any chances of breaking changes in existing codebases, including yours.</span></span>

<span data-ttu-id="5d8c6-186">Los métodos de extensión solo están en ámbito cuando se llaman mediante la sintaxis de invocación de métodos de extensión, no cuando se llaman como un método estático.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-186">Extension methods are only in scope when called using the extension method invocation syntax, not when called as a static method.</span></span>
<span data-ttu-id="5d8c6-187">A menudo verá esto en las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-187">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="5d8c6-188">Puede importar el modelo LINQ mediante la importación de <xref:System.Linq.Enumerable>.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-188">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="5d8c6-189">Esto importa todos los métodos de la clase <xref:System.Linq.Enumerable>.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-189">This imports all the methods in the <xref:System.Linq.Enumerable> class.</span></span>
<span data-ttu-id="5d8c6-190">Pero los métodos de extensión solo están en ámbito cuando se llaman como métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-190">However, the extension methods are only in scope when called as extension methods.</span></span> <span data-ttu-id="5d8c6-191">No están en el ámbito si se llaman usando la sintaxis de métodos estáticos:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-191">They are not in scope if they are called using the static method syntax:</span></span>

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

<span data-ttu-id="5d8c6-192">Esta decisión se debe a que normalmente los métodos de extensión se llaman mediante expresiones de invocación de método de extensión.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-192">This decision is because extension methods are typically called using extension method invocation expressions.</span></span> <span data-ttu-id="5d8c6-193">El caso excepcional de que se llamen mediante la sintaxis de llamada de método estático es para resolver ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-193">In the rare case where they are called using the static method call syntax it is to resolve ambiguity.</span></span>
<span data-ttu-id="5d8c6-194">Parece aconsejable que se requiera el nombre de clase como parte de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-194">Requiring the class name as part of the invocation seems wise.</span></span>

<span data-ttu-id="5d8c6-195">Hay una última característica de `static using`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-195">There's one last feature of `static using`.</span></span> <span data-ttu-id="5d8c6-196">La directiva `static using` también importa cualquier tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-196">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="5d8c6-197">Esto permite hacer referencia a los tipos anidados sin calificación.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-197">That enables you to reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="5d8c6-198">Operadores condicionales NULL</span><span class="sxs-lookup"><span data-stu-id="5d8c6-198">Null-conditional operators</span></span>

<span data-ttu-id="5d8c6-199">Los valores NULL complican el código.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-199">Null values complicate code.</span></span> <span data-ttu-id="5d8c6-200">Es necesario comprobar todos los accesos de variables para asegurarse de que no se va a desreferenciar `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-200">You need to check every access of variables to ensure you are not dereferencing `null`.</span></span> <span data-ttu-id="5d8c6-201">El *operador condicional NULL* realiza esas comprobaciones de una forma mucho más sencilla y fluida.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-201">The *null conditional operator* makes those checks much easier and fluid.</span></span>

<span data-ttu-id="5d8c6-202">Simplemente reemplace el acceso a miembros `.` por `?.`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-202">Simply replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="5d8c6-203">En el ejemplo anterior, se asigna `null` a la variable `first` si el objeto person es `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-203">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="5d8c6-204">De lo contrario, se le asigna el valor de la propiedad `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-204">Otherwise, it gets assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="5d8c6-205">Lo más importante, `?.` significa que esta línea de código no genera una excepción `NullReferenceException` cuando la variable `person` es `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-205">Most importantly, the `?.` means that this line of code does not generate a `NullReferenceException` when the `person` variable is `null`.</span></span> <span data-ttu-id="5d8c6-206">En su lugar, se cortocircuita y genera `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-206">Instead, it short-circuits and produces `null`.</span></span>

<span data-ttu-id="5d8c6-207">Además, tenga en cuenta que esta expresión devuelve `string`, independientemente del valor de `person`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-207">Also, note that this expression returns a `string`, regardless of the value of `person`.</span></span>
<span data-ttu-id="5d8c6-208">En caso de cortocircuito, se devuelve el valor `null` con tipo para que coincida con la expresión completa.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-208">In the case of short circuiting, the `null` value returned is typed to match the full expression.</span></span>

<span data-ttu-id="5d8c6-209">A menudo se puede usar esta construcción con el operador de *fusión nula* para asignar valores predeterminados cuando una de las propiedades es `null`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-209">You can often use this construct with the *null coalescing* operator to assign default values when one of the properties are `null`:</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="5d8c6-210">El operando del lado derecho del operador `?.` no se limita a propiedades o campos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-210">The right hand side operand of the `?.` operator is not limited to properties or fields.</span></span>
<span data-ttu-id="5d8c6-211">También se puede usar para invocar métodos de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-211">You can also use it to conditionally invoke methods.</span></span> <span data-ttu-id="5d8c6-212">El uso más común de las funciones miembro con el operador condicional NULL es invocar de forma segura delegados (o controladores de eventos) que puedan ser `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-212">The most common use of member functions with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="5d8c6-213">Para ello, se llama al método `Invoke` del delegado usando el operador `?.` para obtener acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-213">You'll do this by calling the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="5d8c6-214">Puede ver un ejemplo en el</span><span class="sxs-lookup"><span data-stu-id="5d8c6-214">You can see an example in the</span></span>  
<span data-ttu-id="5d8c6-215">tema de [patrones de delegado](../delegates-patterns.md#handling-null-delegates).</span><span class="sxs-lookup"><span data-stu-id="5d8c6-215">[delegate patterns](../delegates-patterns.md#handling-null-delegates) topic.</span></span>

<span data-ttu-id="5d8c6-216">Las reglas del operador `?.` garantizan que el lado izquierdo del operador solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-216">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="5d8c6-217">Esto es importante y permite muchos elementos, incluidos el ejemplo mediante controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-217">This is important and enables many idioms, including the example using event handlers.</span></span> <span data-ttu-id="5d8c6-218">Comencemos con el uso del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-218">Let's start with the event handler usage.</span></span> <span data-ttu-id="5d8c6-219">En versiones anteriores de C#, se recomendaba escribir código como este:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-219">In previous versions of C#, you were encouraged to write code like this:</span></span>

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

<span data-ttu-id="5d8c6-220">Esto se prefería a una sintaxis más sencilla:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-220">This was preferred over a simpler syntax:</span></span>

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> <span data-ttu-id="5d8c6-221">El ejemplo anterior presenta una condición de carrera.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-221">The preceding example introduces a race condition.</span></span> <span data-ttu-id="5d8c6-222">El evento `SomethingHappened` puede tener suscriptores cuando se comprueba `null`, y los suscriptores se pueden haber quitado antes de que se genere el evento.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-222">The `SomethingHappened` event may have subscribers when checked against `null`, and those subscribers may have been removed before the event is raised.</span></span> <span data-ttu-id="5d8c6-223">Esto supondría que se produjera una excepción <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-223">That would cause a <xref:System.NullReferenceException> to be thrown.</span></span>

<span data-ttu-id="5d8c6-224">En esta segunda versión, es posible que el controlador de eventos `SomethingHappened` sea distinto de NULL cuando se prueba, pero si otro código quita un controlador, aún podría ser NULL cuando se llama al controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-224">In this second version, the `SomethingHappened` event handler might be non-null when tested, but if other code removes a handler, it could still be null when the event handler was called.</span></span>

<span data-ttu-id="5d8c6-225">El compilador genera código para el operador `?.` que garantiza que el lado izquierdo (`this.SomethingHappened`) de la expresión `?.` se evalúa una vez y el resultado se almacena en caché:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-225">The compiler generates code for the `?.` operator that ensures the left side (`this.SomethingHappened`) of the `?.` expression is evaluated once, and the result is cached:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="5d8c6-226">Asegurarse de que el lado izquierdo se evalúa solo una vez también le permite usar cualquier expresión, incluidas las llamadas de método, en el lado izquierdo del `?.`. Incluso si hay efectos secundarios, se evalúan una vez, por lo que los efectos secundarios solo se producen una vez.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-226">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.` Even if these have side-effects, they are evaluated once, so the side effects occur only once.</span></span> <span data-ttu-id="5d8c6-227">Puede ver un ejemplo en nuestro contenido en [eventos](../events-overview.md#language-support-for-events).</span><span class="sxs-lookup"><span data-stu-id="5d8c6-227">You can see an example in our content on [events](../events-overview.md#language-support-for-events).</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="5d8c6-228">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="5d8c6-228">String Interpolation</span></span>

<span data-ttu-id="5d8c6-229">C# 6 contiene nueva sintaxis para crear cadenas a partir de una cadena de formato y expresiones que se evalúan para generar otros valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-229">C# 6 contains new syntax for composing strings from a format string and expressions that are evaluated to produce other string values.</span></span>

<span data-ttu-id="5d8c6-230">Tradicionalmente, era necesario usar parámetros posicionales en un método como `string.Format`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-230">Traditionally, you needed to use positional parameters in a method like `string.Format`:</span></span>

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

<span data-ttu-id="5d8c6-231">Con C# 6, la nueva característica [interpolación de cadenas](../language-reference/tokens/interpolated.md) permite insertar las expresiones en la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-231">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed the expressions in the format string.</span></span> <span data-ttu-id="5d8c6-232">Solo hay que anteponer la cadena con `$`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-232">Simply preface the string with `$`:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="5d8c6-233">Este ejemplo inicial usa expresiones de propiedad para las expresiones sustituidas.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-233">This initial example uses property expressions for the substituted expressions.</span></span> <span data-ttu-id="5d8c6-234">Se puede expandir esta sintaxis para usar cualquier expresión.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-234">You can expand on this syntax to use any expression.</span></span> <span data-ttu-id="5d8c6-235">Por ejemplo, se podría calcular la puntuación media de un alumno como parte de la interpolación:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-235">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

<span data-ttu-id="5d8c6-236">Al ejecutar el ejemplo anterior, encontrará que es posible que la salida de `Grades.Average()` tenga más posiciones decimales de las que querría.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-236">Running the preceding example, you would find that the output for `Grades.Average()` might have more decimal places than you would like.</span></span> <span data-ttu-id="5d8c6-237">La sintaxis de interpolación de cadena admite todas las cadenas de formato disponibles mediante el uso de los métodos de formato anteriores.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-237">The string interpolation syntax supports all the format strings available using earlier formatting methods.</span></span> <span data-ttu-id="5d8c6-238">Las cadenas de formato se agregan entre las llaves.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-238">You add the format strings inside the braces.</span></span> <span data-ttu-id="5d8c6-239">Agregue un signo `:` después de la expresión a la que se va a dar formato:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-239">Add a `:` following the expression to format:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="5d8c6-240">La línea de código anterior dará formato al valor de `Grades.Average()` como un número de punto flotante con dos posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-240">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="5d8c6-241">El símbolo `:` siempre se interpreta como el separador entre la expresión a la que se va a dar formato y la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-241">The `:` is always interpreted as the separator between the expression being formatted and the format string.</span></span> <span data-ttu-id="5d8c6-242">Esto puede ocasionar problemas cuando la expresión usa un signo `:` de otra manera, por ejemplo como un operador condicional:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-242">This can introduce problems when your expression uses a `:` in another way, such as a conditional operator:</span></span>

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

<span data-ttu-id="5d8c6-243">En el ejemplo anterior, `:` se analiza como el principio de la cadena de formato, no como parte del operador condicional.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-243">In the preceding example, the `:` is parsed as the beginning of the format string, not part of the conditional operator.</span></span> <span data-ttu-id="5d8c6-244">En todos los casos en los que sucede esto, se puede escribir la expresión entre paréntesis para forzar a que el compilador la interprete de la forma esperada:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-244">In all cases where this happens, you can surround the expression with parentheses to force the compiler to interpret the expression as you intend:</span></span>

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

<span data-ttu-id="5d8c6-245">No hay ninguna limitación en cuanto a las expresiones que se pueden colocar entre las llaves.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-245">There aren't any limitations on the expressions you can place between the braces.</span></span> <span data-ttu-id="5d8c6-246">Se puede ejecutar una consulta LINQ compleja dentro de una cadena interpolada para realizar cálculos y mostrar el resultado:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-246">You can execute a complex LINQ query inside an interpolated string to perform computations and display the result:</span></span>

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

<span data-ttu-id="5d8c6-247">En este ejemplo se puede ver que incluso se puede anidar una expresión de interpolación de cadena dentro de otra expresión de interpolación de cadena.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-247">You can see from this sample that you can even nest a string interpolation expression inside another string interpolation expression.</span></span> <span data-ttu-id="5d8c6-248">Este ejemplo probablemente es más complejo de lo que sería aconsejable en código de producción,</span><span class="sxs-lookup"><span data-stu-id="5d8c6-248">This example is very likely more complex than you would want in production code.</span></span>
<span data-ttu-id="5d8c6-249">pero es ilustrativo de la amplitud de la característica.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-249">Rather, it is illustrative of the breadth of the feature.</span></span> <span data-ttu-id="5d8c6-250">Cualquier expresión de C# puede colocarse entre las llaves de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-250">Any C# expression can be placed between the curly braces of an interpolated string.</span></span>

### <a name="string-interpolation-and-specific-cultures"></a><span data-ttu-id="5d8c6-251">Interpolación de cadena y referencias culturales específicas</span><span class="sxs-lookup"><span data-stu-id="5d8c6-251">String interpolation and specific cultures</span></span>

<span data-ttu-id="5d8c6-252">Todos los ejemplos que se muestran en la sección anterior dan formato a las cadenas con la referencia cultural actual y el idioma del equipo donde se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-252">All the examples shown in the preceding section format the strings using the current culture and language on the machine where the code executes.</span></span> <span data-ttu-id="5d8c6-253">A menudo puede ser necesario dar formato a la cadena generada con una referencia cultural concreta.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-253">Often you may need to format the string produced using a specific culture.</span></span>
<span data-ttu-id="5d8c6-254">Para hacerlo, aprovechan que el objeto producido por una interpolación de cadena puede convertirse implícitamente a <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-254">To do that use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString>.</span></span>

<span data-ttu-id="5d8c6-255">La instancia de <xref:System.FormattableString> contiene la cadena de formato y los resultados de la evaluación de las expresiones antes de convertirlas en cadenas.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-255">The <xref:System.FormattableString> instance contains the format string, and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="5d8c6-256">Se pueden usar los métodos públicos de <xref:System.FormattableString> para especificar la referencia cultural al dar formato a una cadena.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-256">You can use public methods of <xref:System.FormattableString> to specify the culture when formatting a string.</span></span> <span data-ttu-id="5d8c6-257">Por ejemplo, en el ejemplo siguiente se genera una cadena con la referencia cultural de alemán.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-257">For example, the following example produces a string using German culture.</span></span> <span data-ttu-id="5d8c6-258">(Usa el carácter "," para el separador de decimales y el carácter "." como separador de miles).</span><span class="sxs-lookup"><span data-stu-id="5d8c6-258">(It uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="5d8c6-259">Para más información, vea el tema [Interpolación de cadenas](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="5d8c6-259">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="5d8c6-260">Filtros de excepciones</span><span class="sxs-lookup"><span data-stu-id="5d8c6-260">Exception Filters</span></span>

<span data-ttu-id="5d8c6-261">Otra característica nueva de C# 6 son los *filtros de excepciones*.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-261">Another new feature in C# 6 is *exception filters*.</span></span> <span data-ttu-id="5d8c6-262">Los filtros de excepciones son cláusulas que determinan cuándo se debe aplicar una cláusula catch determinada.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-262">Exception Filters are clauses that determine when a given catch clause should be applied.</span></span>
<span data-ttu-id="5d8c6-263">Si la expresión usada para un filtro de excepciones se evalúa como `true`, la cláusula catch realiza su procesamiento normal en una excepción.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-263">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="5d8c6-264">Si la expresión se evalúa como `false`, entonces se omite la cláusula `catch`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-264">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span>

<span data-ttu-id="5d8c6-265">Un uso consiste en examinar la información sobre una excepción para determinar si una cláusula `catch` puede procesar la excepción:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-265">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

<span data-ttu-id="5d8c6-266">El código generado por los filtros de excepciones proporciona una mejor información sobre una excepción que se produce y no se procesa.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-266">The code generated by exception filters provides better information about an exception that is thrown and not processed.</span></span> <span data-ttu-id="5d8c6-267">Antes de que se agregaran los filtros de excepciones al lenguaje, era necesario crear un código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-267">Before exception filters were added to the language, you would need to create code like the following:</span></span>

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

<span data-ttu-id="5d8c6-268">El punto donde se produce la excepción cambia entre estos dos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-268">The point where the exception is thrown changes between these two examples.</span></span>
<span data-ttu-id="5d8c6-269">En el código anterior, donde se usa una cláusula `throw`, cualquier análisis de seguimiento de pila o examen de volcado de memoria mostrará que la excepción se produjo desde la instrucción `throw` en la cláusula catch.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-269">In the previous code, where a `throw` clause is used, any stack trace analysis or examination of crash dumps will show that the exception was thrown from the `throw` statement in your catch clause.</span></span> <span data-ttu-id="5d8c6-270">El objeto de excepción real contendrá la pila de llamadas original, pero el resto de la información sobre las variables en la pila de llamadas entre este punto de inicio y la ubicación del punto de inicio original se perdió.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-270">The actual exception object will contain the original call stack, but all other information about any variables in the call stack between this throw point and the location of the original throw point has been lost.</span></span> 

<span data-ttu-id="5d8c6-271">Compare esto con cómo se procesa el código mediante un filtro de excepciones: la expresión de filtro de excepciones se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-271">Contrast that with how the code using an exception filter is processed: the exception filter expression evaluates to `false`.</span></span> <span data-ttu-id="5d8c6-272">Por tanto, la ejecución nunca entra en la cláusula `catch`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-272">Therefore, execution never enters the `catch` clause.</span></span> <span data-ttu-id="5d8c6-273">Dado que la cláusula `catch` no se ejecuta, no se produce el desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-273">Because the `catch` clause does not execute, no stack unwinding takes place.</span></span> <span data-ttu-id="5d8c6-274">Esto significa que la ubicación de inicio original se conserva para cualquier actividad de depuración que tenga lugar más adelante.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-274">That means the original throw location is preserved for any debugging activities that would take place later.</span></span>

<span data-ttu-id="5d8c6-275">Siempre que necesite evaluar los campos o las propiedades de una excepción, en lugar de confiar únicamente en el tipo de excepción, use un filtro de excepciones para conservar más información de depuración.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-275">Whenever you need to evaluate fields or properties of an exception, instead of relying solely on the exception type, use an exception filter to preserve more debugging information.</span></span>

<span data-ttu-id="5d8c6-276">Otro patrón recomendado con los filtros de excepciones es usarlos para rutinas de registro.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-276">Another recommended pattern with exception filters is to use them for logging routines.</span></span> <span data-ttu-id="5d8c6-277">Este uso también aprovecha la manera en la que se conserva el punto de inicio de excepción cuando un filtro de excepciones se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-277">This usage also leverages the manner in which the exception throw point is preserved when an exception filter evaluates to `false`.</span></span>

<span data-ttu-id="5d8c6-278">Un método de registro sería un método cuyo argumento es la excepción que devuelve incondicionalmente `false`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-278">A logging method would be a method whose argument is the exception that unconditionally returns `false`:</span></span>

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

<span data-ttu-id="5d8c6-279">Siempre que quiera registrar una excepción, puede agregar una cláusula catch y usar este método como el filtro de excepciones:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-279">Whenever you want to log an exception, you can add a catch clause, and use this method as the exception filter:</span></span>

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

<span data-ttu-id="5d8c6-280">Las excepciones no se detectan nunca, porque el método `LogException` siempre devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-280">The exceptions are never caught, because the `LogException` method always returns `false`.</span></span> <span data-ttu-id="5d8c6-281">Ese filtro de excepciones que siempre es false significa que se puede colocar este controlador de registro antes de otros controladores de excepciones:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-281">That always false exception filter means that you can place this logging handler before any other exception handlers:</span></span>

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

<span data-ttu-id="5d8c6-282">El ejemplo anterior resalta un aspecto muy importante de los filtros de excepciones.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-282">The preceding example highlights a very important facet of exception filters.</span></span>
<span data-ttu-id="5d8c6-283">Los filtros de excepciones permiten escenarios en los que una cláusula de excepción catch más general puede aparecer antes que otra más específica.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-283">The exception filters enable scenarios where a more general exception catch clause may appear before a more specific one.</span></span> <span data-ttu-id="5d8c6-284">También es posible que el mismo tipo de excepción aparezca en varias cláusulas catch:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-284">It's also possible to have the same exception type appear in multiple catch clauses:</span></span>

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

<span data-ttu-id="5d8c6-285">Otro patrón recomendado hace que sea más fácil impedir que las cláusulas catch procesen las excepciones cuando se adjunta un depurador.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-285">Another recommended pattern helps prevent catch clauses from processing exceptions when a debugger is attached.</span></span> <span data-ttu-id="5d8c6-286">Esta técnica permite ejecutar una aplicación con el depurador y detener la ejecución cuando se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-286">This technique enables you to run an application with the debugger, and stop execution when an exception is thrown.</span></span>

<span data-ttu-id="5d8c6-287">En el código, agregue un filtro de excepciones para que cualquier código de recuperación se ejecute solo cuando no haya un depurador asociado:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-287">In your code, add an exception filter so that any recovery code executes only when a debugger is not attached:</span></span>

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

<span data-ttu-id="5d8c6-288">Después de agregar este código, establezca el depurador para que se interrumpa en todas las excepciones no controladas.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-288">After adding this in code, you set your debugger to break on all unhandled exceptions.</span></span> <span data-ttu-id="5d8c6-289">Ejecute el programa en el depurador, y el depurador siempre se interrumpe cuando `PerformFailingOperation()` produce una excepción `RecoverableException`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-289">Run the program under the debugger, and the debugger breaks whenever `PerformFailingOperation()` throws a `RecoverableException`.</span></span>
<span data-ttu-id="5d8c6-290">El depurador interrumpe el programa, porque la cláusula catch no se ejecutará debido al filtro de excepciones que devuelve false.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-290">The debugger breaks your program, because the catch clause won't be executed due to the false-returning exception filter.</span></span>

## <a name="nameof-expressions"></a><span data-ttu-id="5d8c6-291">Expresiones `nameof`</span><span class="sxs-lookup"><span data-stu-id="5d8c6-291">`nameof` Expressions</span></span>

<span data-ttu-id="5d8c6-292">La expresión `nameof` se evalúa como el nombre de un símbolo.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-292">The `nameof` expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="5d8c6-293">Es una excelente manera de hacer que las herramientas funcionen siempre que se necesita el nombre de una variable, una propiedad o un campo de miembro.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-293">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span>

<span data-ttu-id="5d8c6-294">Uno de los usos más comunes de `nameof` es para proporcionar el nombre de un símbolo que produjo una excepción:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-294">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="5d8c6-295">Otro uso es con aplicaciones basadas en XAML que implementan la interfaz `INotifyPropertyChanged`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-295">Another use is with XAML based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

<span data-ttu-id="5d8c6-296">La ventaja de usar el operador `nameof` en lugar de una cadena de constante es que las herramientas pueden entender el símbolo.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-296">The advantage of using the `nameof` operator over a constant string is that tools can understand the symbol.</span></span> <span data-ttu-id="5d8c6-297">Si usa herramientas de refactorización para cambiar el nombre del símbolo, se cambiará en la expresión `nameof`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-297">If you use refactoring tools to rename the symbol, it will rename it in the `nameof` expression.</span></span> <span data-ttu-id="5d8c6-298">Las cadenas constantes no tienen esta ventaja.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-298">Constant strings don't have that advantage.</span></span> <span data-ttu-id="5d8c6-299">Pruébelo en su editor favorito: cambie el nombre de una variable y todas las expresiones `nameof` también se actualizarán.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-299">Try it yourself in your favorite editor: rename a variable, and any `nameof` expressions will update as well.</span></span>

<span data-ttu-id="5d8c6-300">La expresión `nameof` produce el nombre no completo de su argumento (`LastName` en los ejemplos anteriores) incluso si se usa el nombre completo para el argumento:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-300">The `nameof` expression produces the unqualified name of its argument (`LastName` in the previous examples) even if you use the fully qualified name for the argument:</span></span>

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

<span data-ttu-id="5d8c6-301">Esta expresión `nameof` produce `FirstName`, no `UXComponents.ViewModel.FirstName`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-301">This `nameof` expression produces `FirstName`, not `UXComponents.ViewModel.FirstName`.</span></span>

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="5d8c6-302">Await en bloques Catch y Finally</span><span class="sxs-lookup"><span data-stu-id="5d8c6-302">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="5d8c6-303">C# 5 tenía varias limitaciones en cuanto a dónde se podían colocar las expresiones `await`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-303">C# 5 had several limitations around where you could place `await` expressions.</span></span>
<span data-ttu-id="5d8c6-304">Una de ellas se ha quitado en C# 6.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-304">One of those has been removed in C# 6.</span></span> <span data-ttu-id="5d8c6-305">Ahora se puede usar `await` en expresiones `catch` o `finally`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-305">You can now use `await` in `catch` or `finally` expressions.</span></span> 

<span data-ttu-id="5d8c6-306">La adición de expresiones await en bloques catch y finally puede parecer que complica cómo se procesan.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-306">The addition of await expressions in catch and finally blocks may appear to complicate how those are processed.</span></span> <span data-ttu-id="5d8c6-307">Vamos a agregar un ejemplo para explicar cómo aparece esto.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-307">Let's add an example to discuss how this appears.</span></span> <span data-ttu-id="5d8c6-308">En cualquier método asincrónico, se puede usar una expresión await en una cláusula finally.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-308">In any async method, you can use an await expression in a finally clause.</span></span>

<span data-ttu-id="5d8c6-309">Con C# 6, también se puede usar await en expresiones catch.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-309">With C# 6, you can also await in catch expressions.</span></span> <span data-ttu-id="5d8c6-310">Se suele usar principalmente con escenarios de registro:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-310">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="5d8c6-311">Los detalles de implementación para agregar compatibilidad con `await` dentro de cláusulas `catch` y `finally` garantizan que el comportamiento es coherente con el comportamiento del código sincrónico.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-311">The implementation details for adding `await` support inside `catch` and `finally` clauses ensures that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="5d8c6-312">Cuando el código que se ejecuta en una cláusula `catch` o `finally` produce una excepción, la ejecución busca una cláusula `catch` adecuada en el siguiente bloque adyacente.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-312">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="5d8c6-313">Si había una excepción actual, esa excepción se pierde.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-313">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="5d8c6-314">Lo mismo sucede con las expresiones de await en cláusulas `catch` y `finally`: se busca una cláusula `catch` adecuada y se pierde la excepción actual, si existe.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-314">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="5d8c6-315">Este comportamiento es el motivo por el que se recomienda escribir cláusulas `catch` y `finally` con cuidado, para evitar la introducción de nuevas excepciones.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-315">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="index-initializers"></a><span data-ttu-id="5d8c6-316">Inicializadores de índice</span><span class="sxs-lookup"><span data-stu-id="5d8c6-316">Index Initializers</span></span>

<span data-ttu-id="5d8c6-317">Los *inicializadores de índice* son una de las dos características que hacen que los inicializadores de colección sean más coherentes con el uso del índice.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-317">*Index Initializers* is one of two features that make collection initializers more consistent with index usage.</span></span> <span data-ttu-id="5d8c6-318">En versiones anteriores de C#, solo se podían usar los *inicializadores de colección* con colecciones de estilos de secuencia, incluido <xref:System.Collections.Generic.Dictionary%602> con llaves alrededor de los pares de clave-valor:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-318">In earlier releases of C#, you could use *collection initializers* only with sequence style collections, including <xref:System.Collections.Generic.Dictionary%602> by adding braces around key and value pairs:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

<span data-ttu-id="5d8c6-319">Ahora se pueden usar con colecciones <xref:System.Collections.Generic.Dictionary%602> y tipos similares.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-319">Now, you can use them with <xref:System.Collections.Generic.Dictionary%602> collections and similar types.</span></span> <span data-ttu-id="5d8c6-320">La nueva sintaxis admite la asignación con un índice en la colección:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-320">The new syntax supports assignment using an index into the collection:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="5d8c6-321">Esta característica significa que los contenedores asociativos se pueden inicializar mediante una sintaxis similar a la que se lleva usando en varias versiones para los contenedores de secuencia.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-321">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

## <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="5d8c6-322">Métodos `Add` de extensión para inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="5d8c6-322">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="5d8c6-323">Otra característica que facilita la inicialización de colecciones es la capacidad de usar un *método de extensión* para el método `Add`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-323">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="5d8c6-324">Esta característica se agregó por motivos de paridad con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-324">This feature was added for parity with Visual Basic.</span></span> 

<span data-ttu-id="5d8c6-325">La característica es más útil cuando se tiene una clase de colección personalizada que tiene un método con un nombre diferente para agregar nuevos elementos de forma semántica.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-325">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

<span data-ttu-id="5d8c6-326">Por ejemplo, considere una colección de alumnos similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-326">For example, consider a collection of students like this:</span></span>

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

<span data-ttu-id="5d8c6-327">El método `Enroll` agrega un alumno.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-327">The `Enroll` method adds a student.</span></span> <span data-ttu-id="5d8c6-328">Pero no sigue el patrón de `Add`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-328">But it doesn't follow the `Add` pattern.</span></span>
<span data-ttu-id="5d8c6-329">En versiones anteriores de C#, no se podían usar inicializadores de colección con un objeto `Enrollment`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-329">In previous versions of C#, you could not use collection initializers with an `Enrollment` object:</span></span>

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

<span data-ttu-id="5d8c6-330">Ahora se puede, pero solo si se crea un método de extensión que asigna `Add` a `Enroll`:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-330">Now you can, but only if you create an extension method that maps `Add` to `Enroll`:</span></span>

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

<span data-ttu-id="5d8c6-331">Lo que hace esta característica es asignar cualquier método que agrega elementos a una colección a un método denominado `Add` mediante la creación de un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-331">What you are doing with this feature is to map whatever method adds items to a collection to a method named `Add` by creating an extension method.</span></span>

## <a name="improved-overload-resolution"></a><span data-ttu-id="5d8c6-332">Mejoras en la resolución de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5d8c6-332">Improved overload resolution</span></span>

<span data-ttu-id="5d8c6-333">Es probable que esta última característica no se aprecie.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-333">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="5d8c6-334">Había construcciones en las que la versión anterior del compilador de C# podía considerar ambiguas algunas llamadas a métodos con expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-334">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="5d8c6-335">Considere este método:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-335">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="5d8c6-336">En versiones anteriores de C#, la llamada a este método con la sintaxis de grupo de método produciría un error:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-336">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]
 
<span data-ttu-id="5d8c6-337">El compilador anterior no podía distinguir correctamente entre `Task.Run(Action)` y `Task.Run(Func<Task>())`.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-337">The earlier compiler could not distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="5d8c6-338">En las versiones anteriores, era necesario usar una expresión lambda como argumento:</span><span class="sxs-lookup"><span data-stu-id="5d8c6-338">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="5d8c6-339">El compilador de C# 6 determina correctamente que `Task.Run(Func<Task>())` es una opción mejor.</span><span class="sxs-lookup"><span data-stu-id="5d8c6-339">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>
