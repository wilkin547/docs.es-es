---
title: "Diseño de parámetros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d49c4263517830f46b1416684c7d9b874cda4db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-design"></a><span data-ttu-id="925c1-102">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="925c1-102">Parameter Design</span></span>
<span data-ttu-id="925c1-103">Esta sección proporciona instrucciones generales sobre el diseño de parámetro, incluidas las secciones con instrucciones para la comprobación de argumentos.</span><span class="sxs-lookup"><span data-stu-id="925c1-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="925c1-104">Además, debe hacer referencia a las directrices descritas en [parámetros nomenclatura](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="925c1-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="925c1-105">**✓ HACER** usar el tipo de parámetro menos derivado que proporciona la funcionalidad requerida por el miembro.</span><span class="sxs-lookup"><span data-stu-id="925c1-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="925c1-106">Por ejemplo, imagine que desea diseñar un método que enumera una colección e imprime cada elemento en la consola.</span><span class="sxs-lookup"><span data-stu-id="925c1-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="925c1-107">Este tipo de método debe tomar <xref:System.Collections.IEnumerable> como el parámetro, no <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="925c1-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="925c1-108">**X DO NOT** utilizar parámetros reservados.</span><span class="sxs-lookup"><span data-stu-id="925c1-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="925c1-109">Si se necesitan más entradas de a un miembro de alguna versión futura, se puede agregar una nueva sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="925c1-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="925c1-110">**X DO NOT** públicamente ha expuesto métodos que toman punteros, matrices de punteros o matrices multidimensionales como parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="925c1-111">Los punteros y matrices multidimensionales son relativamente difíciles de usar correctamente.</span><span class="sxs-lookup"><span data-stu-id="925c1-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="925c1-112">En casi todos casos, se pueden volver a diseñar las API para evitar realizar estos tipos como parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="925c1-113">**✓ HACER** colocar todos `out` seguir todos los valores de parámetros y `ref` parámetros (excluyendo matrices de parámetros), incluso si se produce una incoherencia en el orden entre las sobrecargas de los parámetros (consulte [miembro Sobrecarga](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="925c1-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="925c1-114">El `out` parámetros pueden verse como valores devueltos adicionales y agruparlos juntos hace más fácil de entender que la firma del método.</span><span class="sxs-lookup"><span data-stu-id="925c1-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="925c1-115">**✓ HACER** sea coherente en los nombres de parámetros al reemplazar los miembros o implementar miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="925c1-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="925c1-116">Esto comunica mejor la relación entre los métodos.</span><span class="sxs-lookup"><span data-stu-id="925c1-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="925c1-117">Elegir entre Enum y parámetros booleanos</span><span class="sxs-lookup"><span data-stu-id="925c1-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="925c1-118">**✓ HACER** utilice enumeraciones si un miembro podría tener dos o más parámetros booleanos.</span><span class="sxs-lookup"><span data-stu-id="925c1-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="925c1-119">**X DO NOT** utilice valores booleanos a menos que esté completamente seguro de que nunca será una necesidad de más de dos valores.</span><span class="sxs-lookup"><span data-stu-id="925c1-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="925c1-120">Las enumeraciones proporcionan algo de espacio para futuras además de valores, pero tenga en cuenta todas las implicaciones de agregar valores a las enumeraciones, que se describen en [Enum diseño](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="925c1-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="925c1-121">**✓ Considere la posibilidad de** con valores booleanos para parámetros de constructor que son valores realmente de dos Estados y simplemente se utilizan para inicializar propiedades booleanas.</span><span class="sxs-lookup"><span data-stu-id="925c1-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="925c1-122">Validación de argumentos</span><span class="sxs-lookup"><span data-stu-id="925c1-122">Validating Arguments</span></span>  
 <span data-ttu-id="925c1-123">**✓ HACER** validar los argumentos pasados a miembros públicos, protegidos o implementados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="925c1-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="925c1-124">Iniciar <xref:System.ArgumentException?displayProperty=nameWithType>, o una de sus subclases, si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="925c1-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="925c1-125">Tenga en cuenta que la validación real no tiene que producirse necesariamente en el propio miembro público o protegido.</span><span class="sxs-lookup"><span data-stu-id="925c1-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="925c1-126">Se puede producir en un nivel inferior de algunos rutina privado o interno.</span><span class="sxs-lookup"><span data-stu-id="925c1-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="925c1-127">La cuestión principal es que toda la superficie que se expone a los usuarios finales las comprobaciones de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="925c1-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="925c1-128">**✓ HACER** throw <xref:System.ArgumentNullException> si se pasa un argumento nulo y el miembro no es compatible con los argumentos null.</span><span class="sxs-lookup"><span data-stu-id="925c1-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="925c1-129">**✓ HACER** validar los parámetros enum.</span><span class="sxs-lookup"><span data-stu-id="925c1-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="925c1-130">No se da por supuesto argumentos enum estará en el intervalo definido por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="925c1-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="925c1-131">CLR permite convertir un valor entero a un valor de enumeración, incluso si el valor no está definido en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="925c1-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="925c1-132">**X DO NOT** usar <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para intervalo de enumeración comprueba.</span><span class="sxs-lookup"><span data-stu-id="925c1-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="925c1-133">**✓ HACER** tenga en cuenta que los argumentos mutables pueden haber cambiado después de que se validaron.</span><span class="sxs-lookup"><span data-stu-id="925c1-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="925c1-134">Si el miembro es importante para la seguridad, se recomienda realizar una copia y, a continuación, validar y procesar el argumento.</span><span class="sxs-lookup"><span data-stu-id="925c1-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="925c1-135">Paso de parámetros</span><span class="sxs-lookup"><span data-stu-id="925c1-135">Parameter Passing</span></span>  
 <span data-ttu-id="925c1-136">Desde la perspectiva de un diseñador de framework, hay tres grupos principales de parámetros: parámetros, por valor `ref` parámetros, y `out` parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="925c1-137">Cuando un argumento se pasa a través de un parámetro por valor, el miembro recibe una copia del argumento real pasado en.</span><span class="sxs-lookup"><span data-stu-id="925c1-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="925c1-138">Si el argumento es un tipo de valor, se coloca una copia del argumento en la pila.</span><span class="sxs-lookup"><span data-stu-id="925c1-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="925c1-139">Si el argumento es un tipo de referencia, se coloca una copia de la referencia en la pila.</span><span class="sxs-lookup"><span data-stu-id="925c1-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="925c1-140">Lenguajes más populares de CLR, como C#, VB.NET y C++, de forma predeterminada para pasar parámetros por valor.</span><span class="sxs-lookup"><span data-stu-id="925c1-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="925c1-141">Cuando se pasa un argumento a través de un `ref` parámetro, el miembro recibe una referencia para el argumento real pasado.</span><span class="sxs-lookup"><span data-stu-id="925c1-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="925c1-142">Si el argumento es un tipo de valor, una referencia al argumento se coloca en la pila.</span><span class="sxs-lookup"><span data-stu-id="925c1-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="925c1-143">Si el argumento es un tipo de referencia, una referencia a la referencia se coloca en la pila.</span><span class="sxs-lookup"><span data-stu-id="925c1-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="925c1-144">`Ref`parámetros pueden utilizarse para permitir que el miembro que se va a modificar los argumentos pasados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="925c1-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="925c1-145">`Out`parámetros son similares a `ref` parámetros, con algunas pequeñas diferencias.</span><span class="sxs-lookup"><span data-stu-id="925c1-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="925c1-146">Inicialmente se considera que el parámetro sin asignar y no se puede leer en el cuerpo del miembro antes de que se asigne un valor.</span><span class="sxs-lookup"><span data-stu-id="925c1-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="925c1-147">Además, el parámetro debe asignarse un valor antes de que el miembro devuelve.</span><span class="sxs-lookup"><span data-stu-id="925c1-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="925c1-148">**X evitar** con `out` o `ref` parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="925c1-149">Usar `out` o `ref` parámetros es necesario tener experiencia con punteros, saber la diferencia entre los tipos de valor y tipos de referencia y controlar métodos con varios valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="925c1-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="925c1-150">Además, la diferencia entre `out` y `ref` parámetros no se entiende ampliamente.</span><span class="sxs-lookup"><span data-stu-id="925c1-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="925c1-151">Arquitectos de Framework diseñar para una audiencia general no deben esperar que los usuarios dominen el uso `out` o `ref` parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="925c1-152">**X DO NOT** pasar tipos de referencia por referencia.</span><span class="sxs-lookup"><span data-stu-id="925c1-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="925c1-153">Hay algunas excepciones limitadas a la regla, por ejemplo, un método que puede usarse para intercambiar las referencias.</span><span class="sxs-lookup"><span data-stu-id="925c1-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="925c1-154">Miembros con un número Variable de parámetros</span><span class="sxs-lookup"><span data-stu-id="925c1-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="925c1-155">Los miembros que pueden tomar un número variable de argumentos se expresan proporcionando un parámetro de matriz.</span><span class="sxs-lookup"><span data-stu-id="925c1-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="925c1-156">Por ejemplo, <xref:System.String> proporciona el método siguiente:</span><span class="sxs-lookup"><span data-stu-id="925c1-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="925c1-157">A continuación, puede llamar un usuario la <xref:System.String.Format%2A?displayProperty=nameWithType> método, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="925c1-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="925c1-158">Agregar la palabra clave params de C# para un parámetro de matriz cambia el parámetro a un parámetro de matriz de parámetros como los denominados y proporciona un acceso directo a la creación de una matriz temporal.</span><span class="sxs-lookup"><span data-stu-id="925c1-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="925c1-159">Esto permite al usuario llamar al método pasando los elementos de matriz directamente en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="925c1-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="925c1-160">Tenga en cuenta que se puede agregar la palabra clave params solo para el último parámetro en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="925c1-161">**✓ Considere la posibilidad de** agregar la palabra clave params a los parámetros de matriz si espera que los usuarios finales para pasar matrices con un número pequeño de elementos.</span><span class="sxs-lookup"><span data-stu-id="925c1-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="925c1-162">Si se espera que una gran cantidad de elementos se pasará en común escenarios, los usuarios probablemente no pasará estos elementos insertados todos modos y, por lo que la palabra clave params no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="925c1-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="925c1-163">**X evitar** usar matrices de parámetros si el llamador casi siempre tendrá la entrada ya en una matriz.</span><span class="sxs-lookup"><span data-stu-id="925c1-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="925c1-164">Por ejemplo, los miembros con parámetros de matriz de bytes casi nunca se denominaría pasando bytes individuales.</span><span class="sxs-lookup"><span data-stu-id="925c1-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="925c1-165">Por esta razón, los parámetros de matriz de bytes en .NET Framework no utilizan la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="925c1-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="925c1-166">**X DO NOT** usar matrices de parámetros si se modifica la matriz por el miembro que toma el parámetro de matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="925c1-167">Por el hecho de que muchos compiladores convierten los argumentos para el miembro en una matriz temporal en el sitio de llamada, la matriz puede ser un objeto temporal y, por lo tanto, se perderán las modificaciones a la matriz.</span><span class="sxs-lookup"><span data-stu-id="925c1-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="925c1-168">**✓ Considere la posibilidad de** mediante la palabra clave params en una sobrecarga simple, aun cuando una sobrecarga más compleja no pudo usar.</span><span class="sxs-lookup"><span data-stu-id="925c1-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="925c1-169">Pregúntese lo siguiente: si los usuarios valoraría disponer de la matriz de parámetros en una sobrecarga incluso si no estaba en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="925c1-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="925c1-170">**✓ HACER** intenta reorganizar los parámetros para que sea posible utilizar la palabra clave params.</span><span class="sxs-lookup"><span data-stu-id="925c1-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="925c1-171">**✓ Considere la posibilidad de** proporcionar sobrecargas especiales y las rutas de código para las llamadas con un número pequeño de argumentos en las API de rendimiento es sumamente importante.</span><span class="sxs-lookup"><span data-stu-id="925c1-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="925c1-172">Esto permite evitar la creación de objetos de matriz cuando se llama a la API con un número pequeño de argumentos.</span><span class="sxs-lookup"><span data-stu-id="925c1-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="925c1-173">Forman los nombres de los parámetros mediante la obtención de una forma singular del parámetro de matriz y agregar un sufijo numérico.</span><span class="sxs-lookup"><span data-stu-id="925c1-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="925c1-174">Solo debe hacer esto si va a la ruta de acceso de código completo de casos especiales, no basta con crear una matriz y llamar al método más general.</span><span class="sxs-lookup"><span data-stu-id="925c1-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="925c1-175">**✓ HACER** tenga en cuenta que null podría pasarse como un argumento de matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="925c1-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="925c1-176">Debe validar que la matriz no es null antes del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="925c1-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="925c1-177">**X DO NOT** utilizar el `varargs` métodos, también conocidas como los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="925c1-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="925c1-178">Algunos lenguajes CLR, como C++, admiten una convención alternativa para pasar listas de parámetros variable llama `varargs` métodos.</span><span class="sxs-lookup"><span data-stu-id="925c1-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="925c1-179">La convención no debe usarse en marcos de trabajo, porque no es compatible con CLS.</span><span class="sxs-lookup"><span data-stu-id="925c1-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="925c1-180">Parámetros de puntero</span><span class="sxs-lookup"><span data-stu-id="925c1-180">Pointer Parameters</span></span>  
 <span data-ttu-id="925c1-181">En general, los punteros no deben aparecer en el área expuesta público de un marco de código administrado bien diseñada.</span><span class="sxs-lookup"><span data-stu-id="925c1-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="925c1-182">La mayoría de los casos, se deben encapsular punteros.</span><span class="sxs-lookup"><span data-stu-id="925c1-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="925c1-183">Sin embargo, en algunos casos, punteros son necesarios por motivos de interoperabilidad, y el uso de punteros en estos casos es adecuado.</span><span class="sxs-lookup"><span data-stu-id="925c1-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="925c1-184">**✓ HACER** proporcionan una alternativa para cualquier miembro que tome un argumento de puntero, como punteros no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="925c1-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="925c1-185">**X evitar** realizar comprobaciones de los argumentos de puntero de argumento costoso.</span><span class="sxs-lookup"><span data-stu-id="925c1-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="925c1-186">**✓ HACER** siga las convenciones comunes relacionadas con el puntero al diseñar los miembros con punteros.</span><span class="sxs-lookup"><span data-stu-id="925c1-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="925c1-187">Por ejemplo, no hay ninguna necesidad de pasar el índice de inicio, porque aritmética de puntero simple puede usarse para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="925c1-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="925c1-188">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="925c1-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="925c1-189">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="925c1-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925c1-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="925c1-190">See Also</span></span>  
 [<span data-ttu-id="925c1-191">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="925c1-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="925c1-192">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="925c1-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
