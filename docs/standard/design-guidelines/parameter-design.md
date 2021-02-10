---
description: 'Más información acerca de: Diseño de parámetros'
title: Diseño de parámetros
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 9663ef8146054985374fdb3e2974fcd996fd1402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731830"
---
# <a name="parameter-design"></a><span data-ttu-id="567e3-103">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="567e3-103">Parameter Design</span></span>

<span data-ttu-id="567e3-104">En esta sección se proporcionan instrucciones generales sobre el diseño de parámetros, incluidas las secciones con instrucciones para comprobar los argumentos.</span><span class="sxs-lookup"><span data-stu-id="567e3-104">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="567e3-105">Además, debe consultar las instrucciones descritas en [Asignación de nombres a parámetros](naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="567e3-105">In addition, you should refer to the guidelines described in [Naming Parameters](naming-parameters.md).</span></span>

 <span data-ttu-id="567e3-106">✔️ USE el tipo de parámetro menos derivado que proporcione la funcionalidad necesaria para el miembro.</span><span class="sxs-lookup"><span data-stu-id="567e3-106">✔️ DO use the least derived parameter type that provides the functionality required by the member.</span></span>

 <span data-ttu-id="567e3-107">Por ejemplo, suponga que desea diseñar un método que enumere una colección e imprima cada elemento en la consola.</span><span class="sxs-lookup"><span data-stu-id="567e3-107">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="567e3-108">Este tipo de método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> ni <xref:System.Collections.IList>, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="567e3-108">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>

 <span data-ttu-id="567e3-109">❌ NO use parámetros reservados.</span><span class="sxs-lookup"><span data-stu-id="567e3-109">❌ DO NOT use reserved parameters.</span></span>

 <span data-ttu-id="567e3-110">Si se necesita más información de un miembro en alguna versión futura, se puede agregar una nueva sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="567e3-110">If more input to a member is needed in some future version, a new overload can be added.</span></span>

 <span data-ttu-id="567e3-111">❌ NO tenga métodos expuestos públicamente que tomen punteros, matrices de punteros o matrices multidimensionales como parámetros.</span><span class="sxs-lookup"><span data-stu-id="567e3-111">❌ DO NOT have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>

 <span data-ttu-id="567e3-112">Los punteros y las matrices multidimensionales son relativamente difíciles de usar de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="567e3-112">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="567e3-113">En casi todos los casos, las API se pueden rediseñar para evitar que estos tipos se tomen como parámetros.</span><span class="sxs-lookup"><span data-stu-id="567e3-113">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>

 <span data-ttu-id="567e3-114">✔️ COLOQUE todos los parámetros `out` que siguen a todos los parámetros `ref` y por valor (excepto las matrices de parámetros), incluso si se produce una incoherencia en el orden de los parámetros entre sobrecargas (consulte [Sobrecarga de miembro](member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="567e3-114">✔️ DO place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](member-overloading.md)).</span></span>

 <span data-ttu-id="567e3-115">Los parámetros `out` se pueden ver como valores devueltos adicionales y, al agruparlos, la firma del método resulta más fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="567e3-115">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>

 <span data-ttu-id="567e3-116">✔️ SEA coherente a la hora de asignar nombres cuando se invaliden los miembros o se implementen los miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="567e3-116">✔️ DO be consistent in naming parameters when overriding members or implementing interface members.</span></span>

 <span data-ttu-id="567e3-117">Esto hace que se comunique mejor la relación entre los métodos.</span><span class="sxs-lookup"><span data-stu-id="567e3-117">This better communicates the relationship between the methods.</span></span>

### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="567e3-118">Elección entre parámetros booleanos y de enumeración</span><span class="sxs-lookup"><span data-stu-id="567e3-118">Choosing Between Enum and Boolean Parameters</span></span>  

 <span data-ttu-id="567e3-119">✔️ USE enumeraciones si, de lo contrario, un miembro tendría dos o más parámetros booleanos.</span><span class="sxs-lookup"><span data-stu-id="567e3-119">✔️ DO use enums if a member would otherwise have two or more Boolean parameters.</span></span>

 <span data-ttu-id="567e3-120">❌ NO use valores booleanos a menos que esté absolutamente seguro de que nunca se necesitarán más de dos valores.</span><span class="sxs-lookup"><span data-stu-id="567e3-120">❌ DO NOT use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>

 <span data-ttu-id="567e3-121">Las enumeraciones le ofrecen espacio para la adición futura de valores, pero debe tener en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en [Diseño de enumeraciones](enum.md).</span><span class="sxs-lookup"><span data-stu-id="567e3-121">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](enum.md).</span></span>

 <span data-ttu-id="567e3-122">✔️ CONSIDERE la posibilidad de usar valores booleanos para los parámetros del constructor que sean en realidad valores de dos estados y se utilicen simplemente para inicializar las propiedades booleanas.</span><span class="sxs-lookup"><span data-stu-id="567e3-122">✔️ CONSIDER using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>

### <a name="validating-arguments"></a><span data-ttu-id="567e3-123">Validación de argumentos</span><span class="sxs-lookup"><span data-stu-id="567e3-123">Validating Arguments</span></span>

 <span data-ttu-id="567e3-124">✔️ VALIDE los argumentos pasados a miembros públicos, protegidos o implementados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="567e3-124">✔️ DO validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="567e3-125">Inicie <xref:System.ArgumentException?displayProperty=nameWithType> o una de sus subclases si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="567e3-125">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>

 <span data-ttu-id="567e3-126">Tenga en cuenta que no es necesario que la validación real se produzca en el propio miembro público o protegido.</span><span class="sxs-lookup"><span data-stu-id="567e3-126">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="567e3-127">Podría producirse en un nivel inferior en algunas rutinas internas o privadas.</span><span class="sxs-lookup"><span data-stu-id="567e3-127">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="567e3-128">Lo más importante es que todo el área expuesta que se expone a los usuarios finales comprueba los argumentos.</span><span class="sxs-lookup"><span data-stu-id="567e3-128">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>

 <span data-ttu-id="567e3-129">✔️ INICIE <xref:System.ArgumentNullException> si se pasa un argumento NULL y el miembro no admite argumentos NULL.</span><span class="sxs-lookup"><span data-stu-id="567e3-129">✔️ DO throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>

 <span data-ttu-id="567e3-130">✔️ VALIDE los parámetros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="567e3-130">✔️ DO validate enum parameters.</span></span>

 <span data-ttu-id="567e3-131">No suponga que los argumentos de enumeración estarán en el intervalo definido por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="567e3-131">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="567e3-132">CLR permite convertir cualquier valor entero en un valor de enumeración incluso si el valor no está definido en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="567e3-132">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>

 <span data-ttu-id="567e3-133">❌ NO use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para las comprobaciones de intervalos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="567e3-133">❌ DO NOT use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>

 <span data-ttu-id="567e3-134">✔️ TENGA en cuenta que los argumentos mutables podrían haber cambiado una vez validados.</span><span class="sxs-lookup"><span data-stu-id="567e3-134">✔️ DO be aware that mutable arguments might have changed after they were validated.</span></span>

 <span data-ttu-id="567e3-135">Si el miembro es sensible desde el punto de vista de la seguridad, se recomienda que realice una copia y, a continuación, valide y procese el argumento.</span><span class="sxs-lookup"><span data-stu-id="567e3-135">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>

### <a name="parameter-passing"></a><span data-ttu-id="567e3-136">Paso de parámetros</span><span class="sxs-lookup"><span data-stu-id="567e3-136">Parameter Passing</span></span>

 <span data-ttu-id="567e3-137">Desde la perspectiva de un diseñador de marcos, hay tres grupos principales de parámetros: por valor, `ref` y `out`.</span><span class="sxs-lookup"><span data-stu-id="567e3-137">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>

 <span data-ttu-id="567e3-138">Cuando un argumento se pasa a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="567e3-138">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="567e3-139">Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="567e3-139">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="567e3-140">Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila.</span><span class="sxs-lookup"><span data-stu-id="567e3-140">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="567e3-141">Los lenguajes CLR más populares, como C# , VB.NET y C++, usan el paso de parámetros por valor como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="567e3-141">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>

 <span data-ttu-id="567e3-142">Cuando un argumento se pasa a través de un parámetro `ref`, el miembro recibe una referencia al argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="567e3-142">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="567e3-143">Si el argumento es un tipo de valor, se coloca una referencia al argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="567e3-143">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="567e3-144">Si el argumento es un tipo de referencia, se coloca una referencia a la referencia en la pila.</span><span class="sxs-lookup"><span data-stu-id="567e3-144">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="567e3-145">Los parámetros `Ref` se pueden usar para permitir que el miembro modifique los argumentos pasados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="567e3-145">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>

 <span data-ttu-id="567e3-146">Los parámetros `Out` son similares a los parámetros `ref`, con algunas pequeñas diferencias.</span><span class="sxs-lookup"><span data-stu-id="567e3-146">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="567e3-147">Se considera inicialmente que el parámetro está sin asignar y no se puede leer en el cuerpo del miembro antes de que se le asigne algún valor.</span><span class="sxs-lookup"><span data-stu-id="567e3-147">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="567e3-148">Además, debe asignarse algún valor al parámetro antes de que vuelva el miembro.</span><span class="sxs-lookup"><span data-stu-id="567e3-148">Also, the parameter has to be assigned some value before the member returns.</span></span>

 <span data-ttu-id="567e3-149">❌ EVITE usar los parámetros `out` o `ref`.</span><span class="sxs-lookup"><span data-stu-id="567e3-149">❌ AVOID using `out` or `ref` parameters.</span></span>

 <span data-ttu-id="567e3-150">Para usar los parámetros `out` o `ref` es necesario tener experiencia con punteros, saber la diferencia entre los tipos de referencia y los tipos de valor, y controlar métodos con varios valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="567e3-150">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="567e3-151">Además, no se suele saber qué diferencia hay entre los parámetros `out` y `ref`.</span><span class="sxs-lookup"><span data-stu-id="567e3-151">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="567e3-152">Los arquitectos de marcos que diseñan para una audiencia general no deben esperar que los usuarios dominen el trabajo con los parámetros `out` o `ref`.</span><span class="sxs-lookup"><span data-stu-id="567e3-152">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>

 <span data-ttu-id="567e3-153">❌ NO pase tipos de referencia por referencia.</span><span class="sxs-lookup"><span data-stu-id="567e3-153">❌ DO NOT pass reference types by reference.</span></span>

 <span data-ttu-id="567e3-154">Hay algunas excepciones limitadas a la regla, como un método que se puede utilizar para intercambiar referencias.</span><span class="sxs-lookup"><span data-stu-id="567e3-154">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>

### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="567e3-155">Miembros con un número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="567e3-155">Members with Variable Number of Parameters</span></span>

 <span data-ttu-id="567e3-156">Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz.</span><span class="sxs-lookup"><span data-stu-id="567e3-156">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="567e3-157">Por ejemplo, <xref:System.String> proporciona el método siguiente:</span><span class="sxs-lookup"><span data-stu-id="567e3-157">For example, <xref:System.String> provides the following method:</span></span>

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 <span data-ttu-id="567e3-158">A continuación, un usuario puede llamar al método <xref:System.String.Format%2A?displayProperty=nameWithType>, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="567e3-158">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 <span data-ttu-id="567e3-159">Con la incorporación de la palabra clave params de C# a un parámetro de matriz, el parámetro cambia a un parámetro de matriz llamado params y se proporciona un acceso directo a la creación de una matriz temporal.</span><span class="sxs-lookup"><span data-stu-id="567e3-159">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 <span data-ttu-id="567e3-160">De este modo, el usuario puede llamar al método pasando los elementos de matriz directamente a la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="567e3-160">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>

 `String.Format("File {0} not found in {1}",filename,directory);`

 <span data-ttu-id="567e3-161">Tenga en cuenta que la palabra clave params solo se puede agregar al último parámetro de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="567e3-161">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>

 <span data-ttu-id="567e3-162">✔️ CONSIDERE la posibilidad de agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales pasen matrices con un pequeño número de elementos.</span><span class="sxs-lookup"><span data-stu-id="567e3-162">✔️ CONSIDER adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="567e3-163">Si se espera que se pasen muchos elementos a escenarios comunes, es probable que los usuarios no pasen estos elementos en línea de todas formas, por lo que no es necesaria la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="567e3-163">If it's expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>

 <span data-ttu-id="567e3-164">❌ EVITE usar matrices params si el llamador ya tuviera casi siempre la entrada en una matriz.</span><span class="sxs-lookup"><span data-stu-id="567e3-164">❌ AVOID using params arrays if the caller would almost always have the input already in an array.</span></span>

 <span data-ttu-id="567e3-165">Por ejemplo, nunca se llamaría a los miembros con parámetros de matriz de bytes pasando bytes individuales.</span><span class="sxs-lookup"><span data-stu-id="567e3-165">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="567e3-166">Es por ello que los parámetros de matriz de bytes de .NET Framework no usan la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="567e3-166">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>

 <span data-ttu-id="567e3-167">❌ NO use matrices params si el miembro que toma el parámetro de matriz params modifica la matriz.</span><span class="sxs-lookup"><span data-stu-id="567e3-167">❌ DO NOT use params arrays if the array is modified by the member taking the params array parameter.</span></span>

 <span data-ttu-id="567e3-168">Dado que muchos compiladores convierten los argumentos del miembro en una matriz temporal en el sitio de llamada, la matriz podría ser un objeto temporal y, por tanto, se perderán todas las modificaciones en la matriz.</span><span class="sxs-lookup"><span data-stu-id="567e3-168">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>

 <span data-ttu-id="567e3-169">✔️ CONSIDERE la posibilidad de usar la palabra clave params en una sobrecarga simple, incluso si una sobrecarga más compleja no pudiera utilizarla.</span><span class="sxs-lookup"><span data-stu-id="567e3-169">✔️ CONSIDER using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>

 <span data-ttu-id="567e3-170">Pregúntese si los usuarios valorarían el hecho de tener la matriz params en una sobrecarga incluso si no estuviera en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="567e3-170">Ask yourself if users would value having the params array in one overload even if it wasn't in all overloads.</span></span>

 <span data-ttu-id="567e3-171">✔️ INTENTE ordenar los parámetros para poder usar la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="567e3-171">✔️ DO try to order parameters to make it possible to use the params keyword.</span></span>

 <span data-ttu-id="567e3-172">✔️ CONSIDERE la posibilidad de proporcionar sobrecargas y rutas de acceso al código especiales para las llamadas con un pequeño número de argumentos en las API que requieran un rendimiento muy alto.</span><span class="sxs-lookup"><span data-stu-id="567e3-172">✔️ CONSIDER providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>

 <span data-ttu-id="567e3-173">Esto permite evitar la creación de objetos de matriz cuando se llama a la API con un pequeño número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="567e3-173">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="567e3-174">Forme los nombres de los parámetros tomando una forma singular del parámetro de matriz y agregando un sufijo numérico.</span><span class="sxs-lookup"><span data-stu-id="567e3-174">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>

 <span data-ttu-id="567e3-175">Solo debe hacerlo si va a marcar como caso especial toda la ruta de acceso al código, no solo crear una matriz y llamar al método más general.</span><span class="sxs-lookup"><span data-stu-id="567e3-175">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>

 <span data-ttu-id="567e3-176">✔️ TENGA EN CUENTA que NULL podría pasarse como un argumento de matriz params.</span><span class="sxs-lookup"><span data-stu-id="567e3-176">✔️ DO be aware that null could be passed as a params array argument.</span></span>

 <span data-ttu-id="567e3-177">Debe validar que la matriz no sea NULL antes del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="567e3-177">You should validate that the array is not null before processing.</span></span>

 <span data-ttu-id="567e3-178">❌ NO use los métodos`varargs`, también conocidos como puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="567e3-178">❌ DO NOT use the `varargs` methods, otherwise known as the ellipsis.</span></span>

 <span data-ttu-id="567e3-179">Algunos lenguajes CLR, como C++, admiten una convención alternativa para pasar listas de parámetros variables llamadas métodos `varargs`.</span><span class="sxs-lookup"><span data-stu-id="567e3-179">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="567e3-180">La convención no debe usarse en marcos, ya que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="567e3-180">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>

### <a name="pointer-parameters"></a><span data-ttu-id="567e3-181">Parámetros de puntero</span><span class="sxs-lookup"><span data-stu-id="567e3-181">Pointer Parameters</span></span>

 <span data-ttu-id="567e3-182">En general, los punteros no deberían aparecer en el área expuesta pública de un marco de código administrado bien diseñado.</span><span class="sxs-lookup"><span data-stu-id="567e3-182">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="567e3-183">La mayoría de las veces, se deben encapsular los punteros.</span><span class="sxs-lookup"><span data-stu-id="567e3-183">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="567e3-184">Sin embargo, en algunos casos, se requieren punteros por motivos de interoperabilidad y, en estos casos, su uso es adecuado.</span><span class="sxs-lookup"><span data-stu-id="567e3-184">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>

 <span data-ttu-id="567e3-185">✔️ PROPORCIONE una alternativa para cualquier miembro que tome un argumento de puntero, ya que los punteros no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="567e3-185">✔️ DO provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>

 <span data-ttu-id="567e3-186">❌ EVITE realizar una comprobación costosa de los argumentos de puntero.</span><span class="sxs-lookup"><span data-stu-id="567e3-186">❌ AVOID doing expensive argument checking of pointer arguments.</span></span>

 <span data-ttu-id="567e3-187">✔️ SIGA las convenciones habituales relacionadas con el puntero al diseñar miembros con punteros.</span><span class="sxs-lookup"><span data-stu-id="567e3-187">✔️ DO follow common pointer-related conventions when designing members with pointers.</span></span>

 <span data-ttu-id="567e3-188">Por ejemplo, no es necesario pasar el índice de inicio, ya que se puede usar una aritmética de puntero simple para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="567e3-188">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>

 <span data-ttu-id="567e3-189">*Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="567e3-189">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="567e3-190">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="567e3-190">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="567e3-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="567e3-191">See also</span></span>

- [<span data-ttu-id="567e3-192">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="567e3-192">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="567e3-193">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="567e3-193">Framework Design Guidelines</span></span>](index.md)
