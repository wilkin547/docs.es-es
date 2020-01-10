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
ms.openlocfilehash: e3725cd11e170c64b6cbf7d77a7a6526603dfd95
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709119"
---
# <a name="parameter-design"></a><span data-ttu-id="d1b70-102">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="d1b70-102">Parameter design</span></span>

<span data-ttu-id="d1b70-103">En esta sección se proporcionan instrucciones generales sobre el diseño de parámetros, incluidas las secciones con instrucciones para comprobar los argumentos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="d1b70-104">Además, debe consultar las directrices descritas en nomenclatura de [parámetros](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d1b70-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="d1b70-105">**✓ DO** usar el tipo de parámetro menos derivado que proporciona la funcionalidad requerida por el miembro.</span><span class="sxs-lookup"><span data-stu-id="d1b70-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="d1b70-106">Por ejemplo, suponga que desea diseñar un método que enumera una colección e imprime cada elemento en la consola.</span><span class="sxs-lookup"><span data-stu-id="d1b70-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="d1b70-107">Este tipo de método debe tomar <xref:System.Collections.IEnumerable> como parámetro, no <xref:System.Collections.ArrayList> ni <xref:System.Collections.IList>, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1b70-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="d1b70-108">**X DO NOT** utilizar parámetros reservados.</span><span class="sxs-lookup"><span data-stu-id="d1b70-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="d1b70-109">Si se necesita más entrada a un miembro en alguna versión futura, se puede Agregar una nueva sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="d1b70-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="d1b70-110">**X DO NOT** públicamente ha expuesto métodos que toman punteros, matrices de punteros o matrices multidimensionales como parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="d1b70-111">Los punteros y las matrices multidimensionales son relativamente difíciles de usar correctamente.</span><span class="sxs-lookup"><span data-stu-id="d1b70-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="d1b70-112">En casi todos los casos, las API se pueden rediseñar para evitar que estos tipos sean parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="d1b70-113">**✓ DO** colocar todos `out` seguir todos los valores de parámetros y `ref` parámetros (excluyendo matrices de parámetros), incluso si se produce una incoherencia en el orden entre las sobrecargas de los parámetros (consulte [miembro Sobrecarga](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="d1b70-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="d1b70-114">Los parámetros `out` se pueden ver como valores devueltos adicionales y, al agruparlos, la firma del método resulta más fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="d1b70-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="d1b70-115">**✓ DO** sea coherente en los nombres de parámetros al reemplazar los miembros o implementar miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="d1b70-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="d1b70-116">Esto comunica mejor la relación entre los métodos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choose-between-enum-and-boolean-parameters"></a><span data-ttu-id="d1b70-117">Elección entre parámetros booleanos y de enumeración</span><span class="sxs-lookup"><span data-stu-id="d1b70-117">Choose between enum and boolean parameters</span></span>  
 <span data-ttu-id="d1b70-118">**✓ DO** utilice enumeraciones si un miembro podría tener dos o más parámetros booleanos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="d1b70-119">**X DO NOT** utilice valores booleanos a menos que esté completamente seguro de que nunca será una necesidad de más de dos valores.</span><span class="sxs-lookup"><span data-stu-id="d1b70-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="d1b70-120">Las enumeraciones ofrecen algún espacio para la adición futura de valores, pero debe tener en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en el [diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="d1b70-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="d1b70-121">**✓ CONSIDER** con valores booleanos para parámetros de constructor que son valores realmente de dos Estados y simplemente se utilizan para inicializar propiedades booleanas.</span><span class="sxs-lookup"><span data-stu-id="d1b70-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validate-arguments"></a><span data-ttu-id="d1b70-122">Validar argumentos</span><span class="sxs-lookup"><span data-stu-id="d1b70-122">Validate arguments</span></span>  
 <span data-ttu-id="d1b70-123">**✓ DO** validar los argumentos pasados a miembros públicos, protegidos o implementados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="d1b70-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="d1b70-124">Produce <xref:System.ArgumentException?displayProperty=nameWithType>, o una de sus subclases, si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="d1b70-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="d1b70-125">Tenga en cuenta que no es necesario que la validación real se produzca en el propio miembro público o protegido.</span><span class="sxs-lookup"><span data-stu-id="d1b70-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="d1b70-126">Podría producirse en un nivel inferior en algunas rutinas internas o privadas.</span><span class="sxs-lookup"><span data-stu-id="d1b70-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="d1b70-127">El punto principal es que todo el área expuesta que se expone a los usuarios finales comprueba los argumentos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="d1b70-128">**✓ DO** throw <xref:System.ArgumentNullException> si se pasa un argumento nulo y el miembro no es compatible con los argumentos null.</span><span class="sxs-lookup"><span data-stu-id="d1b70-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="d1b70-129">**✓ DO** validar los parámetros enum.</span><span class="sxs-lookup"><span data-stu-id="d1b70-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="d1b70-130">No asuma que los argumentos de enumeración estarán en el intervalo definido por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d1b70-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="d1b70-131">CLR permite convertir cualquier valor entero en un valor de enumeración incluso si el valor no está definido en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d1b70-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="d1b70-132">**X DO NOT** usar <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para intervalo de enumeración comprueba.</span><span class="sxs-lookup"><span data-stu-id="d1b70-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="d1b70-133">**✓ DO** tenga en cuenta que los argumentos mutables pueden haber cambiado después de que se validaron.</span><span class="sxs-lookup"><span data-stu-id="d1b70-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="d1b70-134">Si el miembro es sensible a la seguridad, se recomienda hacer una copia y, a continuación, validar y procesar el argumento.</span><span class="sxs-lookup"><span data-stu-id="d1b70-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="pass-parameters"></a><span data-ttu-id="d1b70-135">Paso de parámetros</span><span class="sxs-lookup"><span data-stu-id="d1b70-135">Pass parameters</span></span>  
 <span data-ttu-id="d1b70-136">Desde la perspectiva de un diseñador de Marcos, hay tres grupos principales de parámetros: por valor, parámetros `ref` y parámetros de `out`.</span><span class="sxs-lookup"><span data-stu-id="d1b70-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="d1b70-137">Cuando un argumento se pasa a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="d1b70-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="d1b70-138">Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="d1b70-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="d1b70-139">Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila.</span><span class="sxs-lookup"><span data-stu-id="d1b70-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="d1b70-140">Los lenguajes CLR más populares, C#como, Visual Basic y C++, de forma predeterminada pasan los parámetros por valor.</span><span class="sxs-lookup"><span data-stu-id="d1b70-140">Most popular CLR languages, such as C#, Visual Basic, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="d1b70-141">Cuando un argumento se pasa a través de un parámetro `ref`, el miembro recibe una referencia al argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="d1b70-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="d1b70-142">Si el argumento es un tipo de valor, se coloca una referencia al argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="d1b70-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="d1b70-143">Si el argumento es un tipo de referencia, se coloca en la pila una referencia a la referencia.</span><span class="sxs-lookup"><span data-stu-id="d1b70-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="d1b70-144">`Ref` parámetros se pueden usar para permitir que el miembro modifique los argumentos pasados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d1b70-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="d1b70-145">`Out` parámetros son similares a los parámetros de `ref`, con algunas pequeñas diferencias.</span><span class="sxs-lookup"><span data-stu-id="d1b70-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="d1b70-146">El parámetro se considera inicialmente sin asignar y no se puede leer en el cuerpo del miembro antes de que se le asigne algún valor.</span><span class="sxs-lookup"><span data-stu-id="d1b70-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="d1b70-147">Además, el parámetro tiene que tener asignado algún valor antes de que el miembro devuelva.</span><span class="sxs-lookup"><span data-stu-id="d1b70-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="d1b70-148">**X AVOID** con `out` o `ref` parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="d1b70-149">El uso de los parámetros `out` o `ref` requiere experiencia con punteros, comprender cómo difieren los tipos de valor y de referencia, y cómo controlar métodos con varios valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="d1b70-150">Además, la diferencia entre los parámetros `out` y `ref` no se comprende ampliamente.</span><span class="sxs-lookup"><span data-stu-id="d1b70-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="d1b70-151">Los arquitectos de Framework que diseñan para una audiencia general no deben esperar que los usuarios dominen el trabajo con `out` o `ref` parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="d1b70-152">**X DO NOT** pasar tipos de referencia por referencia.</span><span class="sxs-lookup"><span data-stu-id="d1b70-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="d1b70-153">Hay algunas excepciones limitadas a la regla, como un método que se puede utilizar para intercambiar referencias.</span><span class="sxs-lookup"><span data-stu-id="d1b70-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="d1b70-154">Miembros con número variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="d1b70-154">Members with variable number of parameters</span></span>  
 <span data-ttu-id="d1b70-155">Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz.</span><span class="sxs-lookup"><span data-stu-id="d1b70-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="d1b70-156">Por ejemplo, <xref:System.String> proporciona el método siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1b70-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```csharp  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="d1b70-157">Después, un usuario puede llamar al método <xref:System.String.Format%2A?displayProperty=nameWithType>, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d1b70-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="d1b70-158">Al agregar C# la palabra clave params a un parámetro de matriz, se cambia el parámetro a un parámetro de matriz denominado params y se proporciona un acceso directo a la creación de una matriz temporal.</span><span class="sxs-lookup"><span data-stu-id="d1b70-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```csharp  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="d1b70-159">De este modo, el usuario puede llamar al método pasando los elementos de la matriz directamente en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="d1b70-160">Tenga en cuenta que la palabra clave params solo se puede Agregar al último parámetro de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="d1b70-161">**✓ CONSIDER** agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales para pasar matrices con un número pequeño de elementos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="d1b70-162">Si se espera que se pasen muchos elementos en escenarios comunes, es probable que los usuarios no pasen estos elementos en línea de todas formas, por lo que no es necesario usar la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="d1b70-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="d1b70-163">**X AVOID** usar matrices de parámetros si el llamador casi siempre tendrá la entrada ya en una matriz.</span><span class="sxs-lookup"><span data-stu-id="d1b70-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="d1b70-164">Por ejemplo, nunca se llamaría a los miembros con parámetros de matriz de bytes pasando bytes individuales.</span><span class="sxs-lookup"><span data-stu-id="d1b70-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="d1b70-165">Por esta razón, los parámetros de matriz de bytes del .NET Framework no utilizan la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="d1b70-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="d1b70-166">**X DO NOT** usar matrices de parámetros si se modifica la matriz por el miembro que toma el parámetro de matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="d1b70-167">Debido al hecho de que muchos compiladores convierten los argumentos en el miembro en una matriz temporal en el sitio de llamada, la matriz puede ser un objeto temporal y, por tanto, se perderán todas las modificaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d1b70-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="d1b70-168">**✓ CONSIDER** mediante la palabra clave params en una sobrecarga simple, aun cuando una sobrecarga más compleja no pudo usar.</span><span class="sxs-lookup"><span data-stu-id="d1b70-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="d1b70-169">Pregúntese si los usuarios van a tener la matriz params en una sobrecarga aunque no estuvieran en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="d1b70-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="d1b70-170">**✓ DO** intenta reorganizar los parámetros para que sea posible utilizar la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="d1b70-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="d1b70-171">**✓ CONSIDER** proporcionar sobrecargas especiales y las rutas de código para las llamadas con un número pequeño de argumentos en las API de rendimiento es sumamente importante.</span><span class="sxs-lookup"><span data-stu-id="d1b70-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="d1b70-172">Esto permite evitar la creación de objetos de matriz cuando se llama a la API con un pequeño número de argumentos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="d1b70-173">Formar los nombres de los parámetros tomando una forma singular del parámetro de la matriz y agregando un sufijo numérico.</span><span class="sxs-lookup"><span data-stu-id="d1b70-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="d1b70-174">Solo debe hacerlo si va a utilizar la ruta de acceso a todo el código, no solo crea una matriz y llama al método más general.</span><span class="sxs-lookup"><span data-stu-id="d1b70-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="d1b70-175">**✓ DO** tenga en cuenta que null podría pasarse como un argumento de matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="d1b70-176">Debe validar que la matriz no sea NULL antes del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d1b70-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="d1b70-177">**X DO NOT** utilizar el `varargs` métodos, también conocidas como los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="d1b70-178">Algunos lenguajes CLR, como C++, admiten una Convención alternativa para pasar listas de parámetros de variables llamadas `varargs` métodos.</span><span class="sxs-lookup"><span data-stu-id="d1b70-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="d1b70-179">La Convención no debe usarse en marcos de trabajo, ya que no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="d1b70-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="d1b70-180">Parámetros de puntero</span><span class="sxs-lookup"><span data-stu-id="d1b70-180">Pointer parameters</span></span>  
 <span data-ttu-id="d1b70-181">En general, los punteros no deberían aparecer en el área expuesta pública de un marco de código administrado bien diseñado.</span><span class="sxs-lookup"><span data-stu-id="d1b70-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="d1b70-182">La mayoría de las veces, se deben encapsular los punteros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="d1b70-183">Sin embargo, en algunos casos, se requieren punteros por motivos de interoperabilidad y el uso de punteros en estos casos es adecuado.</span><span class="sxs-lookup"><span data-stu-id="d1b70-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="d1b70-184">**✓ DO** proporcionan una alternativa para cualquier miembro que tome un argumento de puntero, como punteros no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="d1b70-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="d1b70-185">**X AVOID** realizar comprobaciones de los argumentos de puntero de argumento costoso.</span><span class="sxs-lookup"><span data-stu-id="d1b70-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="d1b70-186">**✓ DO** siga las convenciones comunes relacionadas con el puntero al diseñar los miembros con punteros.</span><span class="sxs-lookup"><span data-stu-id="d1b70-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="d1b70-187">Por ejemplo, no es necesario pasar el índice de inicio, ya que se puede usar una aritmética de puntero simple para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="d1b70-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="d1b70-188">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="d1b70-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d1b70-189">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="d1b70-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b70-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1b70-190">See also</span></span>

- [<span data-ttu-id="d1b70-191">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="d1b70-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="d1b70-192">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1b70-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
