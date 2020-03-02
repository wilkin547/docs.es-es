---
title: 'Argumentos opcionales y con nombre: Guía de programación de C#'
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
ms.openlocfilehash: 3685482caebd892c460a3cc2ecf3a22acbe3c9ec
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673412"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="b722c-102">Argumentos opcionales y con nombre (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b722c-102">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="b722c-103">C# 4 introduce argumentos opcionales y con nombre.</span><span class="sxs-lookup"><span data-stu-id="b722c-103">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="b722c-104">Los *argumentos con nombre* permiten especificar un argumento para un parámetro concreto asociando el argumento al nombre del parámetro y no a la posición del parámetro en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="b722c-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="b722c-105">Los *argumentos opcionales* permiten omitir argumentos para algunos parámetros.</span><span class="sxs-lookup"><span data-stu-id="b722c-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="b722c-106">Ambas técnicas se pueden usar con métodos, indexadores, constructores y delegados.</span><span class="sxs-lookup"><span data-stu-id="b722c-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="b722c-107">Cuando se usan argumentos opcionales y con nombre, los argumentos se evalúan por el orden en que aparecen en la lista de argumentos, no en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="b722c-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="b722c-108">Los parámetros opcionales y con nombre, cuando se usan conjuntamente, solo permiten especificar argumentos para algunos parámetros de una lista de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="b722c-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="b722c-109">Esta funcionalidad facilita enormemente las llamadas a interfaces COM, como las API de automatización de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="b722c-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="b722c-110">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="b722c-110">Named Arguments</span></span>  
 <span data-ttu-id="b722c-111">Los argumentos con nombre le liberan de la necesidad de recordar o buscar el orden de los parámetros de la lista de parámetros de los métodos llamados.</span><span class="sxs-lookup"><span data-stu-id="b722c-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="b722c-112">El parámetro de cada argumento se puede especificar por nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="b722c-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="b722c-113">Por ejemplo, se puede llamar de la manera habitual a una función que imprime los detalles de un pedido (como por ejemplo, el nombre de vendedor, el nombre de producto y el número del pedido) mediante el envío de argumentos por posición, en el orden definido por la función.</span><span class="sxs-lookup"><span data-stu-id="b722c-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="b722c-114">Si no recuerda el orden de los parámetros pero conoce sus nombres, puede enviar los argumentos en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="b722c-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="b722c-115">Los argumentos con nombre también mejoran la legibilidad del código al identificar lo que cada argumento representa.</span><span class="sxs-lookup"><span data-stu-id="b722c-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="b722c-116">En el método de ejemplo siguiente, `sellerName` no puede ser nulo ni un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="b722c-116">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="b722c-117">Como `sellerName` y `productName` son tipos de cadena, en lugar de enviar argumentos por posición, tiene sentido usar argumentos con nombre para eliminar la ambigüedad entre ambos y evitar confusiones para aquellos que lean el código.</span><span class="sxs-lookup"><span data-stu-id="b722c-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="b722c-118">Los argumentos con nombre, cuando se usan con argumentos posicionales, son válidos siempre que</span><span class="sxs-lookup"><span data-stu-id="b722c-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="b722c-119">no vayan seguidos de ningún argumento posicional o,</span><span class="sxs-lookup"><span data-stu-id="b722c-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="b722c-120">_a partir de C# 7.2_, se usen en la posición correcta.</span><span class="sxs-lookup"><span data-stu-id="b722c-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="b722c-121">En este ejemplo, el parámetro `orderNum` está en la posición correcta pero no se le asigna un nombre de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="b722c-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="b722c-122">Los argumentos posicionales que siguen a los argumentos con nombre desordenados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="b722c-122">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="b722c-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b722c-123">Example</span></span>  
 <span data-ttu-id="b722c-124">Con este código se implementan los ejemplos de esta sección junto con otros adicionales.</span><span class="sxs-lookup"><span data-stu-id="b722c-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="b722c-125">Argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="b722c-125">Optional Arguments</span></span>  
 <span data-ttu-id="b722c-126">La definición de un método, constructor, indexador o delegado puede especificar que sus parámetros son necesarios o que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="b722c-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="b722c-127">Todas las llamadas deben proporcionar argumentos para todos los parámetros necesarios, pero pueden omitir los argumentos para los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="b722c-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="b722c-128">Cada parámetro opcional tiene un valor predeterminado como parte de su definición.</span><span class="sxs-lookup"><span data-stu-id="b722c-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="b722c-129">Si no se envía ningún argumento para ese parámetro, se usa el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b722c-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="b722c-130">Un valor predeterminado debe ser uno de los siguientes tipos de expresiones:</span><span class="sxs-lookup"><span data-stu-id="b722c-130">A default value must be one of the following types of expressions:</span></span>  
  
- <span data-ttu-id="b722c-131">una expresión constante;</span><span class="sxs-lookup"><span data-stu-id="b722c-131">a constant expression;</span></span>  
  
- <span data-ttu-id="b722c-132">una expresión con el formato `new ValType()`, donde `ValType` es un tipo de valor, como [enum](../../language-reference/builtin-types/enum.md) o [struct](../../language-reference/builtin-types/struct.md);</span><span class="sxs-lookup"><span data-stu-id="b722c-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/builtin-types/enum.md) or a [struct](../../language-reference/builtin-types/struct.md);</span></span>  
  
- <span data-ttu-id="b722c-133">una expresión con el formato [default(ValType)](../../language-reference/operators/default.md), donde `ValType` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="b722c-133">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="b722c-134">Los parámetros opcionales se definen al final de la lista de parámetros después de los parámetros necesarios.</span><span class="sxs-lookup"><span data-stu-id="b722c-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="b722c-135">Si el autor de la llamada proporciona un argumento para algún parámetro de una sucesión de parámetros opcionales, debe proporcionar argumentos para todos los parámetros opcionales anteriores.</span><span class="sxs-lookup"><span data-stu-id="b722c-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="b722c-136">No se admiten espacios separados por comas en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="b722c-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="b722c-137">Por ejemplo, en el código siguiente, el método de instancia `ExampleMethod` se define con un parámetro necesario y dos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b722c-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 <span data-ttu-id="b722c-138">La llamada siguiente a `ExampleMethod` genera un error del compilador, porque se proporciona un argumento para el tercer parámetro pero no para el segundo.</span><span class="sxs-lookup"><span data-stu-id="b722c-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="b722c-139">Pero si conoce el nombre del tercer parámetro, puede usar un argumento con nombre para realizar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b722c-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="b722c-140">En IntelliSense los corchetes se usan para indicar parámetros opcionales, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="b722c-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>  
  
 ![Captura de pantalla en la que se muestra información rápida de IntelliSense para el método ExampleMethod.](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> <span data-ttu-id="b722c-142">También puede declarar parámetros opcionales con la clase <xref:System.Runtime.InteropServices.OptionalAttribute> de .NET.</span><span class="sxs-lookup"><span data-stu-id="b722c-142">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="b722c-143">Los parámetros `OptionalAttribute` no requieren un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b722c-143">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b722c-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b722c-144">Example</span></span>  
 <span data-ttu-id="b722c-145">En el ejemplo siguiente, el constructor de `ExampleClass` tiene un solo parámetro, que es opcional.</span><span class="sxs-lookup"><span data-stu-id="b722c-145">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="b722c-146">El método de instancia `ExampleMethod` tiene un parámetro necesario, `required`, y dos parámetros opcionales, `optionalstr` y `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="b722c-146">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="b722c-147">El código de `Main` muestra las distintas formas en que se pueden invocar el constructor y el método.</span><span class="sxs-lookup"><span data-stu-id="b722c-147">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="b722c-148">Interfaces COM</span><span class="sxs-lookup"><span data-stu-id="b722c-148">COM Interfaces</span></span>  
 <span data-ttu-id="b722c-149">Los argumentos opcionales y con nombre, además de compatibilidad con objetos dinámicos y otros avances, mejoran considerablemente la interoperabilidad con las API de COM, como las API de automatización de Office.</span><span class="sxs-lookup"><span data-stu-id="b722c-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="b722c-150">Por ejemplo, el método <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> de la interfaz <xref:Microsoft.Office.Interop.Excel.Range> de Microsoft Office Excel tiene siete parámetros, todos ellos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b722c-150">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="b722c-151">Estos parámetros se muestran en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="b722c-151">These parameters are shown in the following illustration:</span></span>  
  
 ![Captura de pantalla en la que se muestra información rápida de IntelliSense para el método AutoFormat.](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 <span data-ttu-id="b722c-153">En C# 3.0 y versiones anteriores, se requiere un argumento para cada parámetro, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b722c-153">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 <span data-ttu-id="b722c-154">Pero la llamada a `AutoFormat` se puede simplificar considerablemente mediante argumentos opcionales y con nombre, que se introducen en C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="b722c-154">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="b722c-155">Los parámetros opcionales y con nombre permiten omitir el argumento de un parámetro opcional si no se quiere cambiar el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="b722c-155">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="b722c-156">En la siguiente llamada, solo se especifica un valor para uno de los siete parámetros.</span><span class="sxs-lookup"><span data-stu-id="b722c-156">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 <span data-ttu-id="b722c-157">Para obtener más información y ejemplos, vea [Procedimiento para usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)](./how-to-use-named-and-optional-arguments-in-office-programming.md) y [Procedimiento para tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="b722c-157">For more information and examples, see [How to use named and optional arguments in Office programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to access Office interop objects by using C# features](../interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="b722c-158">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="b722c-158">Overload Resolution</span></span>  
 <span data-ttu-id="b722c-159">El uso de argumentos opcionales y con nombre afecta a la resolución de sobrecarga de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b722c-159">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
- <span data-ttu-id="b722c-160">Un método, indexador o constructor es un candidato para la ejecución si cada uno de sus parámetros es opcional o corresponde, por nombre o por posición, a un solo argumento de la instrucción de llamada y el argumento se puede convertir al tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="b722c-160">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
- <span data-ttu-id="b722c-161">Si se encuentra más de un candidato, se aplican las reglas de resolución de sobrecarga de las conversiones preferidas a los argumentos que se especifican explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b722c-161">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="b722c-162">Los argumentos omitidos en parámetros opcionales se ignoran.</span><span class="sxs-lookup"><span data-stu-id="b722c-162">Omitted arguments for optional parameters are ignored.</span></span>  
  
- <span data-ttu-id="b722c-163">Si dos candidatos se consideran igualmente correctos, la preferencia pasa a un candidato que no tenga parámetros opcionales cuyos argumentos se hayan omitido en la llamada.</span><span class="sxs-lookup"><span data-stu-id="b722c-163">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="b722c-164">Se trata de una consecuencia de una preferencia general en la resolución de sobrecarga para los candidatos con menos parámetros.</span><span class="sxs-lookup"><span data-stu-id="b722c-164">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b722c-165">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b722c-165">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b722c-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="b722c-166">See also</span></span>

- [<span data-ttu-id="b722c-167">Procedimiento para usar argumentos opcionales y con nombre en la programación de Office</span><span class="sxs-lookup"><span data-stu-id="b722c-167">How to use named and optional arguments in Office programming</span></span>](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="b722c-168">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="b722c-168">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="b722c-169">Utilizar constructores</span><span class="sxs-lookup"><span data-stu-id="b722c-169">Using Constructors</span></span>](./using-constructors.md)
- [<span data-ttu-id="b722c-170">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="b722c-170">Using Indexers</span></span>](../indexers/using-indexers.md)
