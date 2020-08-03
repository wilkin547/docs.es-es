---
title: 'Argumentos opcionales y con nombre: Guía de programación de C#'
description: En C#, los argumentos con nombre especifican argumentos por nombre, no posición. Los argumentos opcionales se pueden omitir.
ms.date: 07/20/2015
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
ms.openlocfilehash: 46b9dc23644e68aea2767f2b990fe7f243a4f357
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864987"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="afacc-104">Argumentos opcionales y con nombre (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="afacc-104">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="afacc-105">C# 4 introduce argumentos opcionales y con nombre.</span><span class="sxs-lookup"><span data-stu-id="afacc-105">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="afacc-106">Los *argumentos con nombre* permiten especificar un argumento para un parámetro concreto asociando el argumento al nombre del parámetro y no a la posición del parámetro en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="afacc-106">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="afacc-107">Los *argumentos opcionales* permiten omitir argumentos para algunos parámetros.</span><span class="sxs-lookup"><span data-stu-id="afacc-107">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="afacc-108">Ambas técnicas se pueden usar con métodos, indexadores, constructores y delegados.</span><span class="sxs-lookup"><span data-stu-id="afacc-108">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="afacc-109">Cuando se usan argumentos opcionales y con nombre, los argumentos se evalúan por el orden en que aparecen en la lista de argumentos, no en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="afacc-109">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="afacc-110">Los parámetros opcionales y con nombre, cuando se usan conjuntamente, solo permiten especificar argumentos para algunos parámetros de una lista de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="afacc-110">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="afacc-111">Esta funcionalidad facilita enormemente las llamadas a interfaces COM, como las API de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="afacc-111">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="afacc-112">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="afacc-112">Named Arguments</span></span>  
 <span data-ttu-id="afacc-113">Los argumentos con nombre le liberan de la necesidad de recordar o buscar el orden de los parámetros de la lista de parámetros de los métodos llamados.</span><span class="sxs-lookup"><span data-stu-id="afacc-113">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="afacc-114">El parámetro de cada argumento se puede especificar por nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="afacc-114">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="afacc-115">Por ejemplo, se puede llamar de la manera habitual a una función que imprime los detalles de un pedido (como por ejemplo, el nombre de vendedor, el nombre de producto y el número del pedido) mediante el envío de argumentos por posición, en el orden definido por la función.</span><span class="sxs-lookup"><span data-stu-id="afacc-115">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="afacc-116">Si no recuerda el orden de los parámetros pero conoce sus nombres, puede enviar los argumentos en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="afacc-116">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="afacc-117">Los argumentos con nombre también mejoran la legibilidad del código al identificar lo que cada argumento representa.</span><span class="sxs-lookup"><span data-stu-id="afacc-117">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="afacc-118">En el método de ejemplo siguiente, `sellerName` no puede ser nulo ni un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="afacc-118">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="afacc-119">Como `sellerName` y `productName` son tipos de cadena, en lugar de enviar argumentos por posición, tiene sentido usar argumentos con nombre para eliminar la ambigüedad entre ambos y evitar confusiones para aquellos que lean el código.</span><span class="sxs-lookup"><span data-stu-id="afacc-119">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="afacc-120">Los argumentos con nombre, cuando se usan con argumentos posicionales, son válidos siempre que</span><span class="sxs-lookup"><span data-stu-id="afacc-120">Named arguments, when used with positional arguments, are valid as long as</span></span>

- <span data-ttu-id="afacc-121">no vayan seguidos de ningún argumento posicional o,</span><span class="sxs-lookup"><span data-stu-id="afacc-121">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="afacc-122">_a partir de C# 7.2_, se usen en la posición correcta.</span><span class="sxs-lookup"><span data-stu-id="afacc-122">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="afacc-123">En este ejemplo, el parámetro `orderNum` está en la posición correcta pero no se le asigna un nombre de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="afacc-123">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="afacc-124">Los argumentos posicionales que siguen a los argumentos con nombre desordenados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="afacc-124">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="afacc-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afacc-125">Example</span></span>  
 <span data-ttu-id="afacc-126">Con este código se implementan los ejemplos de esta sección junto con otros adicionales.</span><span class="sxs-lookup"><span data-stu-id="afacc-126">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="afacc-127">Argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="afacc-127">Optional Arguments</span></span>  
 <span data-ttu-id="afacc-128">La definición de un método, constructor, indexador o delegado puede especificar que sus parámetros son necesarios o que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="afacc-128">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="afacc-129">Todas las llamadas deben proporcionar argumentos para todos los parámetros necesarios, pero pueden omitir los argumentos para los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="afacc-129">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="afacc-130">Cada parámetro opcional tiene un valor predeterminado como parte de su definición.</span><span class="sxs-lookup"><span data-stu-id="afacc-130">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="afacc-131">Si no se envía ningún argumento para ese parámetro, se usa el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="afacc-131">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="afacc-132">Un valor predeterminado debe ser uno de los siguientes tipos de expresiones:</span><span class="sxs-lookup"><span data-stu-id="afacc-132">A default value must be one of the following types of expressions:</span></span>  
  
- <span data-ttu-id="afacc-133">una expresión constante;</span><span class="sxs-lookup"><span data-stu-id="afacc-133">a constant expression;</span></span>  
  
- <span data-ttu-id="afacc-134">una expresión con el formato `new ValType()`, donde `ValType` es un tipo de valor, como [enum](../../language-reference/builtin-types/enum.md) o [struct](../../language-reference/builtin-types/struct.md);</span><span class="sxs-lookup"><span data-stu-id="afacc-134">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/builtin-types/enum.md) or a [struct](../../language-reference/builtin-types/struct.md);</span></span>  
  
- <span data-ttu-id="afacc-135">una expresión con el formato [default(ValType)](../../language-reference/operators/default.md), donde `ValType` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="afacc-135">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="afacc-136">Los parámetros opcionales se definen al final de la lista de parámetros después de los parámetros necesarios.</span><span class="sxs-lookup"><span data-stu-id="afacc-136">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="afacc-137">Si el autor de la llamada proporciona un argumento para algún parámetro de una sucesión de parámetros opcionales, debe proporcionar argumentos para todos los parámetros opcionales anteriores.</span><span class="sxs-lookup"><span data-stu-id="afacc-137">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="afacc-138">No se admiten espacios separados por comas en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="afacc-138">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="afacc-139">Por ejemplo, en el código siguiente, el método de instancia `ExampleMethod` se define con un parámetro necesario y dos opcionales.</span><span class="sxs-lookup"><span data-stu-id="afacc-139">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 <span data-ttu-id="afacc-140">La llamada siguiente a `ExampleMethod` genera un error del compilador, porque se proporciona un argumento para el tercer parámetro pero no para el segundo.</span><span class="sxs-lookup"><span data-stu-id="afacc-140">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="afacc-141">Pero si conoce el nombre del tercer parámetro, puede usar un argumento con nombre para realizar la tarea.</span><span class="sxs-lookup"><span data-stu-id="afacc-141">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="afacc-142">En IntelliSense los corchetes se usan para indicar parámetros opcionales, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="afacc-142">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>  
  
 ![Captura de pantalla en la que se muestra información rápida de IntelliSense para el método ExampleMethod.](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> <span data-ttu-id="afacc-144">También puede declarar parámetros opcionales con la clase <xref:System.Runtime.InteropServices.OptionalAttribute> de .NET.</span><span class="sxs-lookup"><span data-stu-id="afacc-144">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="afacc-145">Los parámetros `OptionalAttribute` no requieren un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="afacc-145">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afacc-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afacc-146">Example</span></span>  
 <span data-ttu-id="afacc-147">En el ejemplo siguiente, el constructor de `ExampleClass` tiene un solo parámetro, que es opcional.</span><span class="sxs-lookup"><span data-stu-id="afacc-147">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="afacc-148">El método de instancia `ExampleMethod` tiene un parámetro necesario, `required`, y dos parámetros opcionales, `optionalstr` y `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="afacc-148">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="afacc-149">El código de `Main` muestra las distintas formas en que se pueden invocar el constructor y el método.</span><span class="sxs-lookup"><span data-stu-id="afacc-149">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="afacc-150">Interfaces COM</span><span class="sxs-lookup"><span data-stu-id="afacc-150">COM Interfaces</span></span>  
 <span data-ttu-id="afacc-151">Los argumentos opcionales y con nombre, además de compatibilidad con objetos dinámicos y otros avances, mejoran considerablemente la interoperabilidad con las API de COM, como las API de automatización de Office.</span><span class="sxs-lookup"><span data-stu-id="afacc-151">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="afacc-152">Por ejemplo, el método <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> de la interfaz <xref:Microsoft.Office.Interop.Excel.Range> de Microsoft Office Excel tiene siete parámetros, todos ellos opcionales.</span><span class="sxs-lookup"><span data-stu-id="afacc-152">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="afacc-153">Estos parámetros se muestran en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="afacc-153">These parameters are shown in the following illustration:</span></span>  
  
 ![Captura de pantalla en la que se muestra información rápida de IntelliSense para el método AutoFormat.](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 <span data-ttu-id="afacc-155">En C# 3.0 y versiones anteriores, se requiere un argumento para cada parámetro, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="afacc-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 <span data-ttu-id="afacc-156">Pero la llamada a `AutoFormat` se puede simplificar considerablemente mediante argumentos opcionales y con nombre, que se introducen en C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="afacc-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="afacc-157">Los parámetros opcionales y con nombre permiten omitir el argumento de un parámetro opcional si no se quiere cambiar el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="afacc-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="afacc-158">En la siguiente llamada, solo se especifica un valor para uno de los siete parámetros.</span><span class="sxs-lookup"><span data-stu-id="afacc-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 <span data-ttu-id="afacc-159">Para obtener más información y ejemplos, vea [Procedimiento para usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)](./how-to-use-named-and-optional-arguments-in-office-programming.md) y [Procedimiento para tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="afacc-159">For more information and examples, see [How to use named and optional arguments in Office programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to access Office interop objects by using C# features](../interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="afacc-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="afacc-160">Overload Resolution</span></span>  
 <span data-ttu-id="afacc-161">El uso de argumentos opcionales y con nombre afecta a la resolución de sobrecarga de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="afacc-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
- <span data-ttu-id="afacc-162">Un método, indexador o constructor es un candidato para la ejecución si cada uno de sus parámetros es opcional o corresponde, por nombre o por posición, a un solo argumento de la instrucción de llamada y el argumento se puede convertir al tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="afacc-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
- <span data-ttu-id="afacc-163">Si se encuentra más de un candidato, se aplican las reglas de resolución de sobrecarga de las conversiones preferidas a los argumentos que se especifican explícitamente.</span><span class="sxs-lookup"><span data-stu-id="afacc-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="afacc-164">Los argumentos omitidos en parámetros opcionales se ignoran.</span><span class="sxs-lookup"><span data-stu-id="afacc-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
- <span data-ttu-id="afacc-165">Si dos candidatos se consideran igualmente correctos, la preferencia pasa a un candidato que no tenga parámetros opcionales cuyos argumentos se hayan omitido en la llamada.</span><span class="sxs-lookup"><span data-stu-id="afacc-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="afacc-166">Se trata de una consecuencia de una preferencia general en la resolución de sobrecarga para los candidatos con menos parámetros.</span><span class="sxs-lookup"><span data-stu-id="afacc-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="afacc-167">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="afacc-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="afacc-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="afacc-168">See also</span></span>

- [<span data-ttu-id="afacc-169">Procedimiento para usar argumentos opcionales y con nombre en la programación de Office</span><span class="sxs-lookup"><span data-stu-id="afacc-169">How to use named and optional arguments in Office programming</span></span>](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="afacc-170">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="afacc-170">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="afacc-171">Utilizar constructores</span><span class="sxs-lookup"><span data-stu-id="afacc-171">Using Constructors</span></span>](./using-constructors.md)
- [<span data-ttu-id="afacc-172">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="afacc-172">Using Indexers</span></span>](../indexers/using-indexers.md)
