---
title: "Argumentos opcionales y con nombre (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e6fceb569a79b5988171f06ae6c09d86b5fc667d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="ce1fe-102">Argumentos opcionales y con nombre (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ce1fe-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="ce1fe-103"> introduce argumentos opcionales y con nombre.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-103"> introduces named and optional arguments.</span></span> <span data-ttu-id="ce1fe-104">Los *argumentos con nombre* permiten especificar un argumento para un parámetro concreto asociando el argumento al nombre del parámetro y no a la posición del parámetro en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="ce1fe-105">Los *argumentos opcionales* permiten omitir argumentos para algunos parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="ce1fe-106">Ambas técnicas se pueden usar con métodos, indexadores, constructores y delegados.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="ce1fe-107">Cuando se usan argumentos opcionales y con nombre, los argumentos se evalúan por el orden en que aparecen en la lista de argumentos, no en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="ce1fe-108">Los parámetros opcionales y con nombre, cuando se usan conjuntamente, solo permiten especificar argumentos para algunos parámetros de una lista de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="ce1fe-109">Esta funcionalidad facilita enormemente las llamadas a interfaces COM, como las API de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="ce1fe-110">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="ce1fe-110">Named Arguments</span></span>  
 <span data-ttu-id="ce1fe-111">Los argumentos con nombre le liberan de la necesidad de recordar o buscar el orden de los parámetros de la lista de parámetros de los métodos llamados.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="ce1fe-112">El parámetro de cada argumento se puede especificar por nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="ce1fe-113">Por ejemplo, una función que imprime los detalles del pedido (como por ejemplo, nombre de vendedor, el nombre de producto & número de orden) puede llamar de manera estándar mediante el envío de argumentos por posición, en el orden definido por la función.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="ce1fe-114">Si no recuerda el orden de los parámetros pero conoce sus nombres, puede enviar los argumentos en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="ce1fe-115">Los argumentos con nombre también mejoran la legibilidad del código al identificar lo que cada argumento representa.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="ce1fe-116">En el método de ejemplo siguiente, el `sellerName` no puede ser null o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-116">In the example method below, the `sellerName` cannot be null or whitespace.</span></span> <span data-ttu-id="ce1fe-117">Como ambos `sellerName` y `productName` son tipos de cadenas, en lugar de enviar argumentos por posición, tiene sentido usar argumentos con nombre para eliminar la ambigüedad de los dos y reducir la confusión para cualquiera que lea el código.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="ce1fe-118">Argumentos con nombre, cuando se usa con argumentos posicionales, son válidas tanto en cuanto</span><span class="sxs-lookup"><span data-stu-id="ce1fe-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="ce1fe-119">no va seguidos de los argumentos posicionales, o</span><span class="sxs-lookup"><span data-stu-id="ce1fe-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="ce1fe-120">_a partir de C# 7.2_, se utilizan en la posición correcta.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="ce1fe-121">En el ejemplo siguiente, el parámetro `orderNum` está en la posición correcta pero no se denomine explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="ce1fe-122">Sin embargo, no son válidos si va seguidos de argumentos posicionales argumentos con nombre fuera de servicio.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-122">However, out-of-order named arguments are invalid if they're followed by positional arguments.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="ce1fe-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce1fe-123">Example</span></span>  
 <span data-ttu-id="ce1fe-124">El código siguiente implementa los ejemplos de esta sección junto con algunos adicionales.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="ce1fe-125">Argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="ce1fe-125">Optional Arguments</span></span>  
 <span data-ttu-id="ce1fe-126">La definición de un método, constructor, indexador o delegado puede especificar que sus parámetros son necesarios o que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="ce1fe-127">Todas las llamadas deben proporcionar argumentos para todos los parámetros necesarios, pero pueden omitir los argumentos para los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="ce1fe-128">Cada parámetro opcional tiene un valor predeterminado como parte de su definición.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="ce1fe-129">Si no se envía ningún argumento para ese parámetro, se usa el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="ce1fe-130">Un valor predeterminado debe ser uno de los siguientes tipos de expresiones:</span><span class="sxs-lookup"><span data-stu-id="ce1fe-130">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="ce1fe-131">una expresión constante;</span><span class="sxs-lookup"><span data-stu-id="ce1fe-131">a constant expression;</span></span>  
  
-   <span data-ttu-id="ce1fe-132">una expresión con el formato `new ValType()`, donde `ValType` es un tipo de valor, como [enum](../../../csharp/language-reference/keywords/enum.md) o [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span><span class="sxs-lookup"><span data-stu-id="ce1fe-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="ce1fe-133">una expresión con el formato [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), donde `ValType` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-133">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="ce1fe-134">Los parámetros opcionales se definen al final de la lista de parámetros después de los parámetros necesarios.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="ce1fe-135">Si el autor de la llamada proporciona un argumento para algún parámetro de una sucesión de parámetros opcionales, debe proporcionar argumentos para todos los parámetros opcionales anteriores.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="ce1fe-136">No se admiten espacios separados por comas en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="ce1fe-137">Por ejemplo, en el código siguiente, el método de instancia `ExampleMethod` se define con un parámetro necesario y dos opcionales.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 <span data-ttu-id="ce1fe-138">La llamada siguiente a `ExampleMethod` genera un error del compilador, porque se proporciona un argumento para el tercer parámetro pero no para el segundo.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="ce1fe-139">Pero si conoce el nombre del tercer parámetro, puede usar un argumento con nombre para realizar la tarea.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="ce1fe-140">IntelliSense usa corchetes para indicar parámetros opcionales, tal y como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="ce1fe-141">![Información rápida de IntelliSense para el método ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="ce1fe-141">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="ce1fe-142">Parámetros opcionales en ExampleMethod</span><span class="sxs-lookup"><span data-stu-id="ce1fe-142">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce1fe-143">También puede declarar parámetros opcionales con la clase <xref:System.Runtime.InteropServices.OptionalAttribute> de .NET.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-143">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="ce1fe-144">Los parámetros `OptionalAttribute` no requieren un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-144">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce1fe-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce1fe-145">Example</span></span>  
 <span data-ttu-id="ce1fe-146">En el ejemplo siguiente, el constructor de `ExampleClass` tiene un solo parámetro, que es opcional.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-146">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="ce1fe-147">El método de instancia `ExampleMethod` tiene un parámetro necesario, `required`, y dos parámetros opcionales, `optionalstr` y `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-147">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="ce1fe-148">El código de `Main` muestra las distintas formas en que se pueden invocar el constructor y el método.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-148">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="ce1fe-149">Interfaces COM</span><span class="sxs-lookup"><span data-stu-id="ce1fe-149">COM Interfaces</span></span>  
 <span data-ttu-id="ce1fe-150">Los argumentos opcionales y con nombre, además de compatibilidad con objetos dinámicos y otros avances, mejoran considerablemente la interoperabilidad con las API de COM, como las API de automatización de Office.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-150">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="ce1fe-151">Por ejemplo, el método [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) de la interfaz [Range](http://go.microsoft.com/fwlink/?LinkId=148196) de Microsoft Office Excel tiene siete parámetros, todos ellos opcionales.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-151">For example, the [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) method in the Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="ce1fe-152">Estos parámetros se muestran en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-152">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="ce1fe-153">![Información rápida de IntelliSense para el método AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="ce1fe-153">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="ce1fe-154">Parámetros de AutoFormat</span><span class="sxs-lookup"><span data-stu-id="ce1fe-154">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="ce1fe-155">En C# 3.0 y versiones anteriores, se requiere un argumento para cada parámetro, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 <span data-ttu-id="ce1fe-156">Pero la llamada a `AutoFormat` se puede simplificar considerablemente mediante argumentos opcionales y con nombre, que se introducen en C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="ce1fe-157">Los parámetros opcionales y con nombre permiten omitir el argumento de un parámetro opcional si no se quiere cambiar el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="ce1fe-158">En la siguiente llamada, solo se especifica un valor para uno de los siete parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 <span data-ttu-id="ce1fe-159">Para obtener más información y ejemplos, vea [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) [Cómo: Usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)] y [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)].</span><span class="sxs-lookup"><span data-stu-id="ce1fe-159">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="ce1fe-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="ce1fe-160">Overload Resolution</span></span>  
 <span data-ttu-id="ce1fe-161">El uso de argumentos opcionales y con nombre afecta a la resolución de sobrecarga de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce1fe-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="ce1fe-162">Un método, indexador o constructor es un candidato para la ejecución si cada uno de sus parámetros es opcional o corresponde, por nombre o por posición, a un solo argumento de la instrucción de llamada y el argumento se puede convertir al tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="ce1fe-163">Si se encuentra más de un candidato, se aplican las reglas de resolución de sobrecarga de las conversiones preferidas a los argumentos que se especifican explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="ce1fe-164">Los argumentos omitidos en parámetros opcionales se ignoran.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="ce1fe-165">Si dos candidatos se consideran igualmente correctos, la preferencia pasa a un candidato que no tenga parámetros opcionales cuyos argumentos se hayan omitido en la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="ce1fe-166">Se trata de una consecuencia de una preferencia general en la resolución de sobrecarga para los candidatos con menos parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce1fe-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ce1fe-167">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ce1fe-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce1fe-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce1fe-168">See Also</span></span>  
 [<span data-ttu-id="ce1fe-169">Cómo: Usar argumentos opcionales y con nombre en la programación de Office</span><span class="sxs-lookup"><span data-stu-id="ce1fe-169">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [<span data-ttu-id="ce1fe-170">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="ce1fe-170">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="ce1fe-171">Utilizar constructores</span><span class="sxs-lookup"><span data-stu-id="ce1fe-171">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
 [<span data-ttu-id="ce1fe-172">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="ce1fe-172">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)
