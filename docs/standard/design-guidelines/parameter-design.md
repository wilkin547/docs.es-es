---
title: Diseño de parámetros
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: e0bc52f5679a7771d5690be9f903e677ce611605
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621592"
---
# <a name="parameter-design"></a><span data-ttu-id="10de3-102">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="10de3-102">Parameter Design</span></span>

<span data-ttu-id="10de3-103">En esta sección se proporcionan instrucciones generales sobre el diseño de parámetros, incluidas las secciones con instrucciones para comprobar los argumentos.</span><span class="sxs-lookup"><span data-stu-id="10de3-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="10de3-104">Además, debe consultar las directrices descritas en nomenclatura de [parámetros](naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="10de3-104">In addition, you should refer to the guidelines described in [Naming Parameters](naming-parameters.md).</span></span>

 <span data-ttu-id="10de3-105">✔️ usar el tipo de parámetro menos derivado que proporciona la funcionalidad requerida por el miembro.</span><span class="sxs-lookup"><span data-stu-id="10de3-105">✔️ DO use the least derived parameter type that provides the functionality required by the member.</span></span>

 <span data-ttu-id="10de3-106">Por ejemplo, suponga que desea diseñar un método que enumera una colección e imprime cada elemento en la consola.</span><span class="sxs-lookup"><span data-stu-id="10de3-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="10de3-107">Este tipo de método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> o <xref:System.Collections.IList> , por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="10de3-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>

 <span data-ttu-id="10de3-108">❌No use parámetros reservados.</span><span class="sxs-lookup"><span data-stu-id="10de3-108">❌ DO NOT use reserved parameters.</span></span>

 <span data-ttu-id="10de3-109">Si se necesita más entrada a un miembro en alguna versión futura, se puede Agregar una nueva sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="10de3-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>

 <span data-ttu-id="10de3-110">❌NO tenga métodos expuestos públicamente que tomen punteros, matrices de punteros o matrices multidimensionales como parámetros.</span><span class="sxs-lookup"><span data-stu-id="10de3-110">❌ DO NOT have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>

 <span data-ttu-id="10de3-111">Los punteros y las matrices multidimensionales son relativamente difíciles de usar correctamente.</span><span class="sxs-lookup"><span data-stu-id="10de3-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="10de3-112">En casi todos los casos, las API se pueden rediseñar para evitar que estos tipos sean parámetros.</span><span class="sxs-lookup"><span data-stu-id="10de3-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>

 <span data-ttu-id="10de3-113">✔️ Coloque todos los `out` parámetros que siguen a todos los parámetros por valor y `ref` (excepto las matrices de parámetros), incluso si se produce una incoherencia en el orden de los parámetros entre sobrecargas (vea [sobrecarga de miembros](member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="10de3-113">✔️ DO place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](member-overloading.md)).</span></span>

 <span data-ttu-id="10de3-114">Los `out` parámetros se pueden ver como valores devueltos adicionales y agruparlos hace que la firma del método sea más fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="10de3-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>

 <span data-ttu-id="10de3-115">✔️ son coherentes en los parámetros de nomenclatura cuando se invalidan miembros o se implementan miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="10de3-115">✔️ DO be consistent in naming parameters when overriding members or implementing interface members.</span></span>

 <span data-ttu-id="10de3-116">Esto comunica mejor la relación entre los métodos.</span><span class="sxs-lookup"><span data-stu-id="10de3-116">This better communicates the relationship between the methods.</span></span>

### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="10de3-117">Elección entre parámetros booleanos y de enumeración</span><span class="sxs-lookup"><span data-stu-id="10de3-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="10de3-118">✔️ utilizar enumeraciones si, de lo contrario, un miembro tendría dos o más parámetros booleanos.</span><span class="sxs-lookup"><span data-stu-id="10de3-118">✔️ DO use enums if a member would otherwise have two or more Boolean parameters.</span></span>

 <span data-ttu-id="10de3-119">❌No use valores booleanos a menos que esté absolutamente seguro de que nunca habrá una necesidad de más de dos valores.</span><span class="sxs-lookup"><span data-stu-id="10de3-119">❌ DO NOT use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>

 <span data-ttu-id="10de3-120">Las enumeraciones ofrecen algún espacio para la adición futura de valores, pero debe tener en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en el [diseño de enumeraciones](enum.md).</span><span class="sxs-lookup"><span data-stu-id="10de3-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](enum.md).</span></span>

 <span data-ttu-id="10de3-121">✔️ considere la posibilidad de usar valores booleanos para los parámetros de constructor que son realmente de dos Estados y que simplemente se utilizan para inicializar las propiedades booleanas.</span><span class="sxs-lookup"><span data-stu-id="10de3-121">✔️ CONSIDER using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>

### <a name="validating-arguments"></a><span data-ttu-id="10de3-122">Validar argumentos</span><span class="sxs-lookup"><span data-stu-id="10de3-122">Validating Arguments</span></span>
 <span data-ttu-id="10de3-123">✔️ validar los argumentos pasados a miembros públicos, protegidos o implementados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="10de3-123">✔️ DO validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="10de3-124">Produce <xref:System.ArgumentException?displayProperty=nameWithType> una excepción o una de sus subclases si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="10de3-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>

 <span data-ttu-id="10de3-125">Tenga en cuenta que no es necesario que la validación real se produzca en el propio miembro público o protegido.</span><span class="sxs-lookup"><span data-stu-id="10de3-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="10de3-126">Podría producirse en un nivel inferior en algunas rutinas internas o privadas.</span><span class="sxs-lookup"><span data-stu-id="10de3-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="10de3-127">El punto principal es que todo el área expuesta que se expone a los usuarios finales comprueba los argumentos.</span><span class="sxs-lookup"><span data-stu-id="10de3-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>

 <span data-ttu-id="10de3-128">✔️ se inician <xref:System.ArgumentNullException> si se pasa un argumento NULL y el miembro no admite argumentos null.</span><span class="sxs-lookup"><span data-stu-id="10de3-128">✔️ DO throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>

 <span data-ttu-id="10de3-129">✔️ validar los parámetros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="10de3-129">✔️ DO validate enum parameters.</span></span>

 <span data-ttu-id="10de3-130">No asuma que los argumentos de enumeración estarán en el intervalo definido por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="10de3-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="10de3-131">CLR permite convertir cualquier valor entero en un valor de enumeración incluso si el valor no está definido en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="10de3-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>

 <span data-ttu-id="10de3-132">❌NO se usa <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para las comprobaciones de intervalo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="10de3-132">❌ DO NOT use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>

 <span data-ttu-id="10de3-133">✔️ Tenga en cuenta que es posible que los argumentos mutables hayan cambiado después de que se validaran.</span><span class="sxs-lookup"><span data-stu-id="10de3-133">✔️ DO be aware that mutable arguments might have changed after they were validated.</span></span>

 <span data-ttu-id="10de3-134">Si el miembro es sensible a la seguridad, se recomienda hacer una copia y, a continuación, validar y procesar el argumento.</span><span class="sxs-lookup"><span data-stu-id="10de3-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>

### <a name="parameter-passing"></a><span data-ttu-id="10de3-135">Paso de parámetros</span><span class="sxs-lookup"><span data-stu-id="10de3-135">Parameter Passing</span></span>
 <span data-ttu-id="10de3-136">Desde la perspectiva de un diseñador de .NET Framework, hay tres grupos principales de parámetros: por valor, parámetros `ref` y parámetros `out` .</span><span class="sxs-lookup"><span data-stu-id="10de3-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>

 <span data-ttu-id="10de3-137">Cuando un argumento se pasa a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="10de3-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="10de3-138">Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="10de3-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="10de3-139">Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila.</span><span class="sxs-lookup"><span data-stu-id="10de3-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="10de3-140">Los lenguajes CLR más populares, como C#, VB.NET y C++, pasan de forma predeterminada los parámetros por valor.</span><span class="sxs-lookup"><span data-stu-id="10de3-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>

 <span data-ttu-id="10de3-141">Cuando se pasa un argumento a través de un `ref` parámetro, el miembro recibe una referencia al argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="10de3-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="10de3-142">Si el argumento es un tipo de valor, se coloca una referencia al argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="10de3-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="10de3-143">Si el argumento es un tipo de referencia, se coloca en la pila una referencia a la referencia.</span><span class="sxs-lookup"><span data-stu-id="10de3-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="10de3-144">`Ref`los parámetros se pueden usar para permitir que el miembro modifique los argumentos pasados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="10de3-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>

 <span data-ttu-id="10de3-145">`Out`los parámetros son similares a `ref` los parámetros, con algunas pequeñas diferencias.</span><span class="sxs-lookup"><span data-stu-id="10de3-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="10de3-146">El parámetro se considera inicialmente sin asignar y no se puede leer en el cuerpo del miembro antes de que se le asigne algún valor.</span><span class="sxs-lookup"><span data-stu-id="10de3-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="10de3-147">Además, el parámetro tiene que tener asignado algún valor antes de que el miembro devuelva.</span><span class="sxs-lookup"><span data-stu-id="10de3-147">Also, the parameter has to be assigned some value before the member returns.</span></span>

 <span data-ttu-id="10de3-148">❌Evite usar `out` `ref` parámetros o.</span><span class="sxs-lookup"><span data-stu-id="10de3-148">❌ AVOID using `out` or `ref` parameters.</span></span>

 <span data-ttu-id="10de3-149">El uso de `out` `ref` parámetros o requiere experiencia con punteros, comprender cómo difieren los tipos de valor y de referencia, y cómo controlar métodos con varios valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="10de3-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="10de3-150">Además, la diferencia entre `out` los `ref` parámetros y no se comprende ampliamente.</span><span class="sxs-lookup"><span data-stu-id="10de3-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="10de3-151">Los arquitectos de marco de trabajo que diseñan para una audiencia general no deben esperar que los usuarios dominen con `out` `ref` parámetros o.</span><span class="sxs-lookup"><span data-stu-id="10de3-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>

 <span data-ttu-id="10de3-152">❌NO pase tipos de referencia por referencia.</span><span class="sxs-lookup"><span data-stu-id="10de3-152">❌ DO NOT pass reference types by reference.</span></span>

 <span data-ttu-id="10de3-153">Hay algunas excepciones limitadas a la regla, como un método que se puede utilizar para intercambiar referencias.</span><span class="sxs-lookup"><span data-stu-id="10de3-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>

### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="10de3-154">Miembros con número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="10de3-154">Members with Variable Number of Parameters</span></span>
 <span data-ttu-id="10de3-155">Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz.</span><span class="sxs-lookup"><span data-stu-id="10de3-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="10de3-156">Por ejemplo, <xref:System.String> proporciona el método siguiente:</span><span class="sxs-lookup"><span data-stu-id="10de3-156">For example, <xref:System.String> provides the following method:</span></span>

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 <span data-ttu-id="10de3-157">Después, un usuario puede llamar al <xref:System.String.Format%2A?displayProperty=nameWithType> método, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="10de3-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 <span data-ttu-id="10de3-158">La adición de la palabra clave params de C# a un parámetro de matriz cambia el parámetro a un parámetro de matriz de parámetros denominados, y proporciona un acceso directo para crear una matriz temporal.</span><span class="sxs-lookup"><span data-stu-id="10de3-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 <span data-ttu-id="10de3-159">De este modo, el usuario puede llamar al método pasando los elementos de la matriz directamente en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="10de3-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>

 `String.Format("File {0} not found in {1}",filename,directory);`

 <span data-ttu-id="10de3-160">Tenga en cuenta que la palabra clave params solo se puede Agregar al último parámetro de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="10de3-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>

 <span data-ttu-id="10de3-161">✔️ considere la posibilidad de agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales pasen matrices con un número pequeño de elementos.</span><span class="sxs-lookup"><span data-stu-id="10de3-161">✔️ CONSIDER adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="10de3-162">Si se espera que se pasen muchos elementos en escenarios comunes, es probable que los usuarios no pasen estos elementos en línea de todas formas, por lo que no es necesario usar la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="10de3-162">If it's expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>

 <span data-ttu-id="10de3-163">❌Evite usar matrices params si el llamador casi siempre tendrá la entrada en una matriz.</span><span class="sxs-lookup"><span data-stu-id="10de3-163">❌ AVOID using params arrays if the caller would almost always have the input already in an array.</span></span>

 <span data-ttu-id="10de3-164">Por ejemplo, nunca se llamaría a los miembros con parámetros de matriz de bytes pasando bytes individuales.</span><span class="sxs-lookup"><span data-stu-id="10de3-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="10de3-165">Por esta razón, los parámetros de matriz de bytes del .NET Framework no utilizan la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="10de3-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>

 <span data-ttu-id="10de3-166">❌No utilice matrices params si la matriz es modificada por el miembro que toma el parámetro params array.</span><span class="sxs-lookup"><span data-stu-id="10de3-166">❌ DO NOT use params arrays if the array is modified by the member taking the params array parameter.</span></span>

 <span data-ttu-id="10de3-167">Debido al hecho de que muchos compiladores convierten los argumentos en el miembro en una matriz temporal en el sitio de llamada, la matriz puede ser un objeto temporal y, por tanto, se perderán todas las modificaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="10de3-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>

 <span data-ttu-id="10de3-168">✔️ considere la posibilidad de usar la palabra clave params en una sobrecarga simple, incluso si una sobrecarga más compleja no pudiera utilizarla.</span><span class="sxs-lookup"><span data-stu-id="10de3-168">✔️ CONSIDER using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>

 <span data-ttu-id="10de3-169">Pregúntese si los usuarios van a tener la matriz params en una sobrecarga aunque no estuvieran en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="10de3-169">Ask yourself if users would value having the params array in one overload even if it wasn't in all overloads.</span></span>

 <span data-ttu-id="10de3-170">✔️ intente ordenar los parámetros para que sea posible usar la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="10de3-170">✔️ DO try to order parameters to make it possible to use the params keyword.</span></span>

 <span data-ttu-id="10de3-171">✔️ considere la posibilidad de proporcionar sobrecargas especiales y rutas de acceso de código para las llamadas con un número pequeño de argumentos en las API con un rendimiento muy importante.</span><span class="sxs-lookup"><span data-stu-id="10de3-171">✔️ CONSIDER providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>

 <span data-ttu-id="10de3-172">Esto permite evitar la creación de objetos de matriz cuando se llama a la API con un pequeño número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="10de3-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="10de3-173">Formar los nombres de los parámetros tomando una forma singular del parámetro de la matriz y agregando un sufijo numérico.</span><span class="sxs-lookup"><span data-stu-id="10de3-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>

 <span data-ttu-id="10de3-174">Solo debe hacerlo si va a utilizar la ruta de acceso a todo el código, no solo crea una matriz y llama al método más general.</span><span class="sxs-lookup"><span data-stu-id="10de3-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>

 <span data-ttu-id="10de3-175">✔️ Tenga en cuenta que null podría pasarse como un argumento de matriz params.</span><span class="sxs-lookup"><span data-stu-id="10de3-175">✔️ DO be aware that null could be passed as a params array argument.</span></span>

 <span data-ttu-id="10de3-176">Debe validar que la matriz no sea NULL antes del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="10de3-176">You should validate that the array is not null before processing.</span></span>

 <span data-ttu-id="10de3-177">❌No utilice los `varargs` métodos, también conocidos como puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="10de3-177">❌ DO NOT use the `varargs` methods, otherwise known as the ellipsis.</span></span>

 <span data-ttu-id="10de3-178">Algunos lenguajes CLR, como C++, admiten una Convención alternativa para pasar listas de parámetros de variables llamadas `varargs` métodos.</span><span class="sxs-lookup"><span data-stu-id="10de3-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="10de3-179">La Convención no debe usarse en marcos de trabajo, ya que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="10de3-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>

### <a name="pointer-parameters"></a><span data-ttu-id="10de3-180">Parámetros de puntero</span><span class="sxs-lookup"><span data-stu-id="10de3-180">Pointer Parameters</span></span>
 <span data-ttu-id="10de3-181">En general, los punteros no deberían aparecer en el área expuesta pública de un marco de código administrado bien diseñado.</span><span class="sxs-lookup"><span data-stu-id="10de3-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="10de3-182">La mayoría de las veces, se deben encapsular los punteros.</span><span class="sxs-lookup"><span data-stu-id="10de3-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="10de3-183">Sin embargo, en algunos casos, se requieren punteros por motivos de interoperabilidad y el uso de punteros en estos casos es adecuado.</span><span class="sxs-lookup"><span data-stu-id="10de3-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>

 <span data-ttu-id="10de3-184">✔️ proporcionan una alternativa para cualquier miembro que toma un argumento de puntero, ya que los punteros no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="10de3-184">✔️ DO provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>

 <span data-ttu-id="10de3-185">❌Evite realizar una comprobación costosa de los argumentos de puntero.</span><span class="sxs-lookup"><span data-stu-id="10de3-185">❌ AVOID doing expensive argument checking of pointer arguments.</span></span>

 <span data-ttu-id="10de3-186">✔️ seguir las convenciones comunes relacionadas con los punteros al diseñar miembros con punteros.</span><span class="sxs-lookup"><span data-stu-id="10de3-186">✔️ DO follow common pointer-related conventions when designing members with pointers.</span></span>

 <span data-ttu-id="10de3-187">Por ejemplo, no es necesario pasar el índice de inicio, ya que se puede usar una aritmética de puntero simple para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="10de3-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>

 <span data-ttu-id="10de3-188">*Partes &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="10de3-188">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="10de3-189">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="10de3-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="10de3-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="10de3-190">See also</span></span>

- [<span data-ttu-id="10de3-191">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="10de3-191">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="10de3-192">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="10de3-192">Framework Design Guidelines</span></span>](index.md)
