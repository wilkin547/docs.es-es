---
title: Texto sin formato
description: 'Aprenda a usar printf y otro formato de texto sin formato en aplicaciones y scripts de F #.'
ms.date: 07/22/2020
ms.openlocfilehash: 90a861736dae69dfbc199a19e24f587c42404737
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063788"
---
# <a name="plain-text-formatting"></a><span data-ttu-id="e5b76-103">Formato de texto sin formato</span><span class="sxs-lookup"><span data-stu-id="e5b76-103">Plain text formatting</span></span>

<span data-ttu-id="e5b76-104">F # admite el formato de texto sin formato con comprobación de tipos mediante `printf` ,, `printfn` `sprintf` y las funciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e5b76-104">F# supports type-checked formatting of plain text using `printf`, `printfn`, `sprintf`, and related functions.</span></span>
<span data-ttu-id="e5b76-105">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-105">For example,</span></span>

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

<span data-ttu-id="e5b76-106">proporciona la salida</span><span class="sxs-lookup"><span data-stu-id="e5b76-106">gives the output</span></span>

```fsharp
Hello world, 2 + 2 is 4
```

<span data-ttu-id="e5b76-107">F # también permite dar formato de texto sin formato a los valores estructurados.</span><span class="sxs-lookup"><span data-stu-id="e5b76-107">F# also allows structured values to be formatted as plain text.</span></span>
<span data-ttu-id="e5b76-108">Por ejemplo, considere el siguiente ejemplo en el que se da formato a la salida como una presentación de tuplas de tipo matriz.</span><span class="sxs-lookup"><span data-stu-id="e5b76-108">For example, consider the following example that formats the output as a matrix-like display of tuples.</span></span>

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

<span data-ttu-id="e5b76-109">El formato de texto sin formato estructurado se activa cuando se usa el `%A` formato en `printf` cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-109">Structured plain text formatting is activated when you use the `%A` format in `printf` formatting strings.</span></span>
<span data-ttu-id="e5b76-110">También se activa al dar formato a la salida de valores de F # Interactive, donde la salida incluye información adicional y también se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="e5b76-110">It's also activated when formatting the output of values in F# interactive, where the output includes extra information and is additionally customizable.</span></span>
<span data-ttu-id="e5b76-111">El formato de texto sin formato también se puede observar a través de cualquier llamada a `x.ToString()` en valores de registro y Unión de F #, incluidos los que se producen implícitamente en la depuración, el registro y otras herramientas.</span><span class="sxs-lookup"><span data-stu-id="e5b76-111">Plain text formatting is also observable through any calls to `x.ToString()` on F# union and record values, including those that occur implicitly in debugging, logging, and other tooling.</span></span>

## <a name="checking-of-printf-format-strings"></a><span data-ttu-id="e5b76-112">Comprobando `printf` cadenas de formato</span><span class="sxs-lookup"><span data-stu-id="e5b76-112">Checking of `printf`-format strings</span></span>

<span data-ttu-id="e5b76-113">Se informará de un error en tiempo de compilación si `printf` se usa una función de formato con un argumento que no coincida con los especificadores de formato printf en la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-113">A compile-time error will be reported if a `printf` formatting function is used with an argument that doesn't match the printf format specifiers in the format string.</span></span>  <span data-ttu-id="e5b76-114">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-114">For example,</span></span>

```fsharp
sprintf "Hello %s" (2+2)
```

<span data-ttu-id="e5b76-115">proporciona la salida</span><span class="sxs-lookup"><span data-stu-id="e5b76-115">gives the output</span></span>

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

<span data-ttu-id="e5b76-116">Técnicamente hablando, al usar `printf` y otras funciones relacionadas, una regla especial en el compilador de F # comprueba el literal de cadena pasado como la cadena de formato, asegurándose de que los argumentos subsiguientes aplicados son del tipo correcto para que coincidan con los especificadores de formato usados.</span><span class="sxs-lookup"><span data-stu-id="e5b76-116">Technically speaking, when using `printf` and other related functions, a special rule in the F# compiler checks the string literal passed as the format string, ensuring the subsequent arguments applied are of the correct type to match the format specifiers used.</span></span>

## <a name="format-specifiers-for-printf"></a><span data-ttu-id="e5b76-117">Especificadores de formato para`printf`</span><span class="sxs-lookup"><span data-stu-id="e5b76-117">Format specifiers for `printf`</span></span>

<span data-ttu-id="e5b76-118">Las especificaciones de formato de los `printf` formatos son cadenas con `%` marcadores que indican el formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-118">Format specifications for `printf` formats are strings with `%` markers that indicate format.</span></span> <span data-ttu-id="e5b76-119">Los marcadores de posición de formato se componen de `%[flags][width][.precision][type]` que el tipo se interpreta de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e5b76-119">Format placeholders consist of `%[flags][width][.precision][type]` where the type is interpreted as follows:</span></span>

| <span data-ttu-id="e5b76-120">Especificador de formato</span><span class="sxs-lookup"><span data-stu-id="e5b76-120">Format specifier</span></span>   | <span data-ttu-id="e5b76-121">Tipos (s)</span><span class="sxs-lookup"><span data-stu-id="e5b76-121">Type(s)</span></span>        | <span data-ttu-id="e5b76-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5b76-122">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | <span data-ttu-id="e5b76-123">bool</span><span class="sxs-lookup"><span data-stu-id="e5b76-123">bool</span></span>      | <span data-ttu-id="e5b76-124">Con formato `true` o`false`</span><span class="sxs-lookup"><span data-stu-id="e5b76-124">Formatted as `true` or `false`</span></span>                |
| `%s`               | <span data-ttu-id="e5b76-125">string</span><span class="sxs-lookup"><span data-stu-id="e5b76-125">string</span></span>    | <span data-ttu-id="e5b76-126">Con formato de contenido sin escape</span><span class="sxs-lookup"><span data-stu-id="e5b76-126">Formatted as its unescaped contents</span></span>         |
| `%c`               | <span data-ttu-id="e5b76-127">char</span><span class="sxs-lookup"><span data-stu-id="e5b76-127">char</span></span>      | <span data-ttu-id="e5b76-128">Con formato del literal de carácter</span><span class="sxs-lookup"><span data-stu-id="e5b76-128">Formatted as the character literal</span></span>  |
| <span data-ttu-id="e5b76-129">`%d`, `%i`</span><span class="sxs-lookup"><span data-stu-id="e5b76-129">`%d`, `%i`</span></span>         | <span data-ttu-id="e5b76-130">un tipo entero básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-130">a basic integer type</span></span> | <span data-ttu-id="e5b76-131">Con formato de entero decimal, con signo si el tipo entero básico está firmado</span><span class="sxs-lookup"><span data-stu-id="e5b76-131">Formatted as a decimal integer, signed if the basic integer type is signed</span></span> |
| `%u`               | <span data-ttu-id="e5b76-132">un tipo entero básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-132">a basic integer type</span></span> | <span data-ttu-id="e5b76-133">Con formato de entero decimal sin signo</span><span class="sxs-lookup"><span data-stu-id="e5b76-133">Formatted as an unsigned decimal integer</span></span>   |
| <span data-ttu-id="e5b76-134">`%x`, `%X`</span><span class="sxs-lookup"><span data-stu-id="e5b76-134">`%x`, `%X`</span></span>         | <span data-ttu-id="e5b76-135">un tipo entero básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-135">a basic integer type</span></span> | <span data-ttu-id="e5b76-136">Con formato de número hexadecimal sin signo (a-f o A-F para dígitos hexadecimales, respectivamente)</span><span class="sxs-lookup"><span data-stu-id="e5b76-136">Formatted as an unsigned hexadecimal number (a-f or A-F for hex digits respectively)</span></span>  |
|  `%o`              | <span data-ttu-id="e5b76-137">un tipo entero básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-137">a basic integer type</span></span> | <span data-ttu-id="e5b76-138">Con formato de número octal sin signo</span><span class="sxs-lookup"><span data-stu-id="e5b76-138">Formatted as an unsigned octal number</span></span> |
| <span data-ttu-id="e5b76-139">`%e`, `%E`</span><span class="sxs-lookup"><span data-stu-id="e5b76-139">`%e`, `%E`</span></span>         | <span data-ttu-id="e5b76-140">un tipo de punto flotante básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-140">a basic floating point type</span></span> | <span data-ttu-id="e5b76-141">Con formato como un valor con signo que tiene el formato `[-]d.dddde[sign]ddd` donde d es un solo dígito decimal, dddd es uno o más dígitos decimales, DDD tiene exactamente tres dígitos decimales y sign es `+` o`-`</span><span class="sxs-lookup"><span data-stu-id="e5b76-141">Formatted as a signed value having the form `[-]d.dddde[sign]ddd` where d is a single decimal digit, dddd is one or more decimal digits, ddd is exactly three decimal digits, and sign is `+` or `-`</span></span> |
| `%f`               | <span data-ttu-id="e5b76-142">un tipo de punto flotante básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-142">a basic floating point type</span></span> | <span data-ttu-id="e5b76-143">Con formato como un valor con signo que tiene el formato `[-]dddd.dddd` , donde `dddd` es uno o más dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="e5b76-143">Formatted as a signed value having the form `[-]dddd.dddd`, where `dddd` is one or more decimal digits.</span></span> <span data-ttu-id="e5b76-144">El número de dígitos que hay delante del separador decimal depende de la magnitud del número y el número de dígitos que hay detrás del separador decimal depende de la precisión solicitada.</span><span class="sxs-lookup"><span data-stu-id="e5b76-144">The number of digits before the decimal point depends on the magnitude of the number, and the number of digits after the decimal point depends on the requested precision.</span></span> |
| <span data-ttu-id="e5b76-145">`%g`, `%G`</span><span class="sxs-lookup"><span data-stu-id="e5b76-145">`%g`, `%G`</span></span> | <span data-ttu-id="e5b76-146">un tipo de punto flotante básico</span><span class="sxs-lookup"><span data-stu-id="e5b76-146">a basic floating point type</span></span> |  <span data-ttu-id="e5b76-147">Con formato con como valor con signo impreso en `%f` o en `%e` formato, lo que sea más compacto para el valor y la precisión especificados.</span><span class="sxs-lookup"><span data-stu-id="e5b76-147">Formatted using as a signed value printed in `%f` or `%e` format, whichever is more compact for the given value and precision.</span></span> |
| `%M` | <span data-ttu-id="e5b76-148">un `System.Decimal` valor</span><span class="sxs-lookup"><span data-stu-id="e5b76-148">a `System.Decimal` value</span></span>  |    <span data-ttu-id="e5b76-149">Con formato mediante el `"G"` especificador de formato para`System.Decimal.ToString(format)`</span><span class="sxs-lookup"><span data-stu-id="e5b76-149">Formatted using the `"G"` format specifier for `System.Decimal.ToString(format)`</span></span> |
| `%O` | <span data-ttu-id="e5b76-150">cualquier valor</span><span class="sxs-lookup"><span data-stu-id="e5b76-150">any value</span></span>  |   <span data-ttu-id="e5b76-151">Formateado mediante la conversión boxing del objeto y la llamada a su `System.Object.ToString()` método</span><span class="sxs-lookup"><span data-stu-id="e5b76-151">Formatted by boxing the object and calling its `System.Object.ToString()` method</span></span> |
| `%A` | <span data-ttu-id="e5b76-152">cualquier valor</span><span class="sxs-lookup"><span data-stu-id="e5b76-152">any value</span></span>  |   <span data-ttu-id="e5b76-153">Con formato de [texto sin formato estructurado](plaintext-formatting.md) con la configuración de diseño predeterminada</span><span class="sxs-lookup"><span data-stu-id="e5b76-153">Formatted using [structured plain text formatting](plaintext-formatting.md) with the default layout settings</span></span> |
| `%a` | <span data-ttu-id="e5b76-154">cualquier valor</span><span class="sxs-lookup"><span data-stu-id="e5b76-154">any value</span></span>  |   <span data-ttu-id="e5b76-155">Requiere dos argumentos: una función de formato que acepte un parámetro de contexto y el valor, y el valor concreto que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="e5b76-155">Requires two arguments: a formatting function accepting a context parameter and the value, and the particular value to print</span></span> |
| `%t` | <span data-ttu-id="e5b76-156">cualquier valor</span><span class="sxs-lookup"><span data-stu-id="e5b76-156">any value</span></span>  |   <span data-ttu-id="e5b76-157">Requiere un argumento: una función de formato que acepte un parámetro de contexto que genere o devuelva el texto adecuado</span><span class="sxs-lookup"><span data-stu-id="e5b76-157">Requires one argument: a formatting function accepting a context parameter that either outputs or returns the appropriate text</span></span> |
| `%%` | <span data-ttu-id="e5b76-158">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="e5b76-158">(none)</span></span>  |   <span data-ttu-id="e5b76-159">No requiere ningún argumento e imprime un signo de porcentaje sin formato:`%`</span><span class="sxs-lookup"><span data-stu-id="e5b76-159">Requires no arguments and prints a plain percent sign: `%`</span></span> |

<span data-ttu-id="e5b76-160">Los tipos enteros básicos son `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), `int16` ( `System.Int16` ), `uint16` ( `System.UInt16` ), `int32` ( `System.Int32` ), `uint32` ( `System.UInt32` ), `int64` ( `System.Int64` ), `uint64` ( `System.UInt64` ), `nativeint` ( `System.IntPtr` ) y `unativeint` ( `System.UIntPtr` ).</span><span class="sxs-lookup"><span data-stu-id="e5b76-160">Basic integer types are `byte` (`System.Byte`), `sbyte` (`System.SByte`), `int16` (`System.Int16`), `uint16` (`System.UInt16`), `int32` (`System.Int32`), `uint32` (`System.UInt32`), `int64` (`System.Int64`), `uint64` (`System.UInt64`), `nativeint`  (`System.IntPtr`), and `unativeint`  (`System.UIntPtr`).</span></span>
<span data-ttu-id="e5b76-161">Los tipos de punto flotante básicos son `float` ( `System.Double` ) y `float32` ( `System.Single` ).</span><span class="sxs-lookup"><span data-stu-id="e5b76-161">Basic floating point types are `float` (`System.Double`) and `float32` (`System.Single`).</span></span>

<span data-ttu-id="e5b76-162">El ancho opcional es un entero que indica el ancho mínimo del resultado.</span><span class="sxs-lookup"><span data-stu-id="e5b76-162">The optional width is an integer indicating the minimal width of the result.</span></span> <span data-ttu-id="e5b76-163">Por ejemplo, `%6d` imprime un entero, prefijando espacios en blanco para rellenar al menos seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="e5b76-163">For instance, `%6d` prints an integer, prefixing it with spaces to fill at least six characters.</span></span> <span data-ttu-id="e5b76-164">Si el ancho es `*` , se toma un argumento entero adicional para especificar el ancho correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e5b76-164">If width is `*`, then an extra integer  argument is taken to specify the corresponding width.</span></span>

<span data-ttu-id="e5b76-165">Las marcas válidas son:</span><span class="sxs-lookup"><span data-stu-id="e5b76-165">Valid flags are:</span></span>

| <span data-ttu-id="e5b76-166">Marca</span><span class="sxs-lookup"><span data-stu-id="e5b76-166">Flag</span></span>   | <span data-ttu-id="e5b76-167">Efecto</span><span class="sxs-lookup"><span data-stu-id="e5b76-167">Effect</span></span>        | <span data-ttu-id="e5b76-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5b76-168">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | <span data-ttu-id="e5b76-169">Agregue ceros en lugar de espacios para crear el ancho necesario</span><span class="sxs-lookup"><span data-stu-id="e5b76-169">Add zeros instead of spaces to make up the required width</span></span> |    |
| `-` |  <span data-ttu-id="e5b76-170">Justificar a la izquierda el resultado dentro del ancho especificado</span><span class="sxs-lookup"><span data-stu-id="e5b76-170">Left justify the result within the specified width</span></span> |   |
| `+`  | <span data-ttu-id="e5b76-171">Agregue un `+` carácter si el número es positivo (para que coincida con un `-` signo para los negativos)</span><span class="sxs-lookup"><span data-stu-id="e5b76-171">Add a `+` character if the number is positive (to match a `-` sign for negatives)</span></span> |   |
| <span data-ttu-id="e5b76-172">carácter de espacio</span><span class="sxs-lookup"><span data-stu-id="e5b76-172">space character</span></span> | <span data-ttu-id="e5b76-173">Agregue un espacio adicional si el número es positivo (para que coincida con un signo "-" para los negativos)</span><span class="sxs-lookup"><span data-stu-id="e5b76-173">Add an extra space if the number is positive (to match a '-' sign for negatives)</span></span> |

<span data-ttu-id="e5b76-174">La `#` marca printf no es válida y se indicará un error en tiempo de compilación si se usa.</span><span class="sxs-lookup"><span data-stu-id="e5b76-174">The printf `#` flag is invalid and a compile-time error will be reported if it is used.</span></span>

<span data-ttu-id="e5b76-175">Se da formato a los valores mediante una referencia cultural invariable.</span><span class="sxs-lookup"><span data-stu-id="e5b76-175">Values are formatted using invariant culture.</span></span> <span data-ttu-id="e5b76-176">La configuración de la referencia cultural es irrelevante para `printf` dar formato, excepto cuando afecta a los resultados de `%O` y el `%A` formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-176">Culture settings are irrelevant to `printf` formatting except when they affect the results of `%O` and `%A` formatting.</span></span> <span data-ttu-id="e5b76-177">Para obtener más información, vea [formato de texto sin formato estructurado](plaintext-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="e5b76-177">For more information, see [structured plain text formatting](plaintext-formatting.md).</span></span>

## <a name="a-formatting"></a><span data-ttu-id="e5b76-178">`%A`formato</span><span class="sxs-lookup"><span data-stu-id="e5b76-178">`%A` formatting</span></span>

<span data-ttu-id="e5b76-179">El `%A` especificador de formato se usa para dar formato a los valores de una manera legible y también puede ser útil para notificar información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e5b76-179">The `%A` format specifier is used to format values in a human-readable way, and can also be useful for reporting diagnostic information.</span></span>

### <a name="primitive-values"></a><span data-ttu-id="e5b76-180">Valores primitivos</span><span class="sxs-lookup"><span data-stu-id="e5b76-180">Primitive values</span></span>

<span data-ttu-id="e5b76-181">Al dar formato a texto sin formato mediante el `%A` especificador, se da formato a los valores numéricos de F # con su sufijo y referencia cultural de todos los idiomas.</span><span class="sxs-lookup"><span data-stu-id="e5b76-181">When formatting plain text using the `%A` specifier, F# numeric values are formatted with their suffix and invariant culture.</span></span> <span data-ttu-id="e5b76-182">Los valores de punto flotante se formatean con 10 lugares de precisión de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e5b76-182">Floating point values are formatted using 10 places of floating point precision.</span></span> <span data-ttu-id="e5b76-183">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-183">For example,</span></span>

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

<span data-ttu-id="e5b76-184">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-184">produces</span></span>

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

<span data-ttu-id="e5b76-185">Al usar el `%A` especificador, se da formato a las cadenas con comillas.</span><span class="sxs-lookup"><span data-stu-id="e5b76-185">When using the `%A` specifier, strings are formatted using quotes.</span></span> <span data-ttu-id="e5b76-186">Los códigos de escape no se agregan y, en su lugar, se imprimen los caracteres sin formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-186">Escape codes are not added and instead the raw characters are printed.</span></span> <span data-ttu-id="e5b76-187">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-187">For example,</span></span>

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

<span data-ttu-id="e5b76-188">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-188">produces</span></span>

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a><span data-ttu-id="e5b76-189">Valores de .NET</span><span class="sxs-lookup"><span data-stu-id="e5b76-189">.NET values</span></span>

<span data-ttu-id="e5b76-190">Al dar formato a texto sin formato mediante el `%A` especificador, se da formato a los objetos de .net que no son de F # mediante `x.ToString()` el uso de la configuración predeterminada de .net especificada por `System.Globalization.CultureInfo.CurrentCulture` y `System.Globalization.CultureInfo.CurrentUICulture` .</span><span class="sxs-lookup"><span data-stu-id="e5b76-190">When formatting plain text using the `%A` specifier, non-F# .NET objects are formatted by using `x.ToString()` using the default settings of .NET given by `System.Globalization.CultureInfo.CurrentCulture` and `System.Globalization.CultureInfo.CurrentUICulture`.</span></span>  <span data-ttu-id="e5b76-191">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-191">For example,</span></span>

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

<span data-ttu-id="e5b76-192">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-192">produces</span></span>

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a><span data-ttu-id="e5b76-193">Valores estructurados</span><span class="sxs-lookup"><span data-stu-id="e5b76-193">Structured values</span></span>

<span data-ttu-id="e5b76-194">Al dar formato a texto sin formato mediante el `%A` especificador, la sangría de bloque se usa para las listas y tuplas de F #.</span><span class="sxs-lookup"><span data-stu-id="e5b76-194">When formatting plain text using the `%A` specifier, block indentation is used for F# lists and tuples.</span></span> <span data-ttu-id="e5b76-195">Esto se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e5b76-195">This shown in the previous example.</span></span>
<span data-ttu-id="e5b76-196">También se utiliza la estructura de matrices, incluidas las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="e5b76-196">The structure of arrays is also used, including multi-dimensional arrays.</span></span>  <span data-ttu-id="e5b76-197">Las matrices unidimensionales se muestran con `[| ... |]` Sintaxis.</span><span class="sxs-lookup"><span data-stu-id="e5b76-197">Single-dimensional arrays are shown with `[| ... |]` syntax.</span></span> <span data-ttu-id="e5b76-198">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-198">For example,</span></span>

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

<span data-ttu-id="e5b76-199">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-199">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

<span data-ttu-id="e5b76-200">El ancho de impresión predeterminado es 80.</span><span class="sxs-lookup"><span data-stu-id="e5b76-200">The default print width is 80.</span></span>  <span data-ttu-id="e5b76-201">Este ancho se puede personalizar mediante el uso de un ancho de impresión en el especificador de formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-201">This width can be customized by using a print width in the format specifier.</span></span> <span data-ttu-id="e5b76-202">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-202">For example,</span></span>

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

<span data-ttu-id="e5b76-203">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-203">produces</span></span>

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

<span data-ttu-id="e5b76-204">Si se especifica un ancho de impresión de 0, no se utilizará ningún ancho de impresión.</span><span class="sxs-lookup"><span data-stu-id="e5b76-204">Specifying a print width of 0 results in no print width being used.</span></span> <span data-ttu-id="e5b76-205">Se producirá una sola línea de texto, excepto donde las cadenas incrustadas en la salida contengan saltos de línea.</span><span class="sxs-lookup"><span data-stu-id="e5b76-205">A single line of text will result, except where embedded strings in the output contain line breaks.</span></span>  <span data-ttu-id="e5b76-206">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5b76-206">For example</span></span>

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

<span data-ttu-id="e5b76-207">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-207">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

<span data-ttu-id="e5b76-208">Se usa un límite de profundidad de 4 para los valores de secuencia ( `IEnumerable` ), que se muestran como `seq { ...}` .</span><span class="sxs-lookup"><span data-stu-id="e5b76-208">A depth limit of 4 is used for sequence (`IEnumerable`) values, which are shown as `seq { ...}`.</span></span> <span data-ttu-id="e5b76-209">Se usa un límite de profundidad de 100 para los valores de lista y matriz.</span><span class="sxs-lookup"><span data-stu-id="e5b76-209">A depth limit of 100 is used for list and array values.</span></span>
<span data-ttu-id="e5b76-210">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-210">For example,</span></span>

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

<span data-ttu-id="e5b76-211">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-211">produces</span></span>

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

<span data-ttu-id="e5b76-212">La sangría de bloque también se usa para la estructura de los valores de registro y Unión públicos.</span><span class="sxs-lookup"><span data-stu-id="e5b76-212">Block indentation is also used for the structure of public record and union values.</span></span> <span data-ttu-id="e5b76-213">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-213">For example,</span></span>

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="e5b76-214">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-214">produces</span></span>

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="e5b76-215">Si `%+A` se utiliza, la estructura privada de los registros y las uniones también se revela mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="e5b76-215">If `%+A` is used, then the private structure of records and unions is also revealed by using reflection.</span></span> <span data-ttu-id="e5b76-216">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5b76-216">For example</span></span>

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

<span data-ttu-id="e5b76-217">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-217">produces</span></span>

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a><span data-ttu-id="e5b76-218">Valores grandes, cíclicos o profundamente anidados</span><span class="sxs-lookup"><span data-stu-id="e5b76-218">Large, cyclic, or deeply nested values</span></span>

<span data-ttu-id="e5b76-219">Los valores estructurados grandes tienen el formato de un número máximo de nodos de objetos globales de 10000.</span><span class="sxs-lookup"><span data-stu-id="e5b76-219">Large structured values are formatted to a maximum overall object node count of 10000.</span></span>
<span data-ttu-id="e5b76-220">Los valores profundamente anidados tienen el formato de una profundidad de 100.</span><span class="sxs-lookup"><span data-stu-id="e5b76-220">Deeply nested values are formatted to a depth of 100.</span></span>  <span data-ttu-id="e5b76-221">En ambos casos, `...` se usa para Elide parte de la salida.</span><span class="sxs-lookup"><span data-stu-id="e5b76-221">In both cases `...` is used to elide some of the output.</span></span>  <span data-ttu-id="e5b76-222">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-222">For example,</span></span>

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

<span data-ttu-id="e5b76-223">genera una salida grande con algunas partes eliden:</span><span class="sxs-lookup"><span data-stu-id="e5b76-223">produces a large output with some parts elided:</span></span>

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

<span data-ttu-id="e5b76-224">Los ciclos se detectan en los gráficos de objetos y `...` se utilizan en los lugares donde se detectan los ciclos.</span><span class="sxs-lookup"><span data-stu-id="e5b76-224">Cycles are detected in the object graphs and `...` is used at places where cycles are detected.</span></span> <span data-ttu-id="e5b76-225">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5b76-225">For example</span></span>

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

<span data-ttu-id="e5b76-226">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-226">produces</span></span>

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a><span data-ttu-id="e5b76-227">Valores de función Lazy, NULL y</span><span class="sxs-lookup"><span data-stu-id="e5b76-227">Lazy, null, and function values</span></span>

<span data-ttu-id="e5b76-228">Los valores diferidos se imprimen como `Value is not created` o texto equivalente cuando el valor aún no se ha evaluado.</span><span class="sxs-lookup"><span data-stu-id="e5b76-228">Lazy values are printed as `Value is not created` or equivalent text when the value has not yet been evaluated.</span></span>

<span data-ttu-id="e5b76-229">Los valores NULL se imprimen como `null` a menos que el tipo estático del valor se determine como un tipo de Unión donde `null` es una representación permitida.</span><span class="sxs-lookup"><span data-stu-id="e5b76-229">Null values are printed as `null` unless the static type of the value is determined to be a union type where `null` is a permitted representation.</span></span>

<span data-ttu-id="e5b76-230">Los valores de función de F # se imprimen como su nombre de cierre generado internamente, por ejemplo, `<fun:it@43-7>` .</span><span class="sxs-lookup"><span data-stu-id="e5b76-230">F# function values are printed as their internally generated closure name, for example, `<fun:it@43-7>`.</span></span>

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a><span data-ttu-id="e5b76-231">Personalizar el formato de texto sin formato con`StructuredFormatDisplay`</span><span class="sxs-lookup"><span data-stu-id="e5b76-231">Customize plain text formatting with `StructuredFormatDisplay`</span></span>

<span data-ttu-id="e5b76-232">Cuando se usa el `%A` especificador, se respeta la presencia del `StructuredFormatDisplay` atributo en las declaraciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="e5b76-232">When using the `%A` specifier, the presence of the `StructuredFormatDisplay` attribute on type declarations is respected.</span></span>  <span data-ttu-id="e5b76-233">Se puede usar para especificar texto suplente y la propiedad para mostrar un valor.</span><span class="sxs-lookup"><span data-stu-id="e5b76-233">This can be used to specify surrogate text and property to display a value.</span></span> <span data-ttu-id="e5b76-234">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e5b76-234">For example:</span></span>

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

<span data-ttu-id="e5b76-235">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-235">produces</span></span>

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a><span data-ttu-id="e5b76-236">Personalizar el formato de texto sin formato invalidando`ToString`</span><span class="sxs-lookup"><span data-stu-id="e5b76-236">Customize plain text formatting by overriding `ToString`</span></span>

<span data-ttu-id="e5b76-237">La implementación predeterminada de `ToString` es observable en programación en F #.</span><span class="sxs-lookup"><span data-stu-id="e5b76-237">The default implementation of `ToString` is observable in F# programming.</span></span> <span data-ttu-id="e5b76-238">A menudo, los resultados predeterminados no son adecuados para su uso en la presentación de información orientada al programador o en el resultado del usuario y, como resultado, es habitual reemplazar la implementación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e5b76-238">Often, the default results aren't suitable for use in either programmer-facing information display or user output, and as a result it is common to override the default implementation.</span></span>  

<span data-ttu-id="e5b76-239">De forma predeterminada, los tipos de registro y Unión de F # invalidan la implementación de `ToString` con una implementación de que usa `sprintf "%+A"` .</span><span class="sxs-lookup"><span data-stu-id="e5b76-239">By default, F# record and union types override the implementation of `ToString` with an implementation that uses `sprintf "%+A"`.</span></span>  <span data-ttu-id="e5b76-240">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-240">For example,</span></span>

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

<span data-ttu-id="e5b76-241">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-241">produces</span></span>

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

<span data-ttu-id="e5b76-242">En el caso de los tipos de clase, no se proporciona ninguna implementación predeterminada de `ToString` y se usa el valor predeterminado de .net, que indica el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="e5b76-242">For class types, no default implementation of `ToString` is provided and the .NET default is used, which reports the name of the type.</span></span> <span data-ttu-id="e5b76-243">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5b76-243">For example,</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="e5b76-244">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-244">produces</span></span>

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

<span data-ttu-id="e5b76-245">Agregar una invalidación para `ToString` puede dar un mejor formato.</span><span class="sxs-lookup"><span data-stu-id="e5b76-245">Adding an override for `ToString` can give better formatting.</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="e5b76-246">Obtiene</span><span class="sxs-lookup"><span data-stu-id="e5b76-246">produces</span></span>

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="e5b76-247">F# interactivo impresión estructurada</span><span class="sxs-lookup"><span data-stu-id="e5b76-247">F# Interactive structured printing</span></span>

<span data-ttu-id="e5b76-248">F# interactivo ( `dotnet fsi` ) utiliza una versión extendida de formato de texto sin formato estructurado para informar de los valores y permite la personalización adicional.</span><span class="sxs-lookup"><span data-stu-id="e5b76-248">F# Interactive (`dotnet fsi`) uses an extended version of structured plain text formatting to report values and allows additional customizability.</span></span> <span data-ttu-id="e5b76-249">Para obtener más información, vea [F# interactivo](fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="e5b76-249">For more information, see [F# Interactive](fsharp-interactive-options.md).</span></span>

## <a name="customize-debug-displays"></a><span data-ttu-id="e5b76-250">Personalizar las visualizaciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e5b76-250">Customize debug displays</span></span>

<span data-ttu-id="e5b76-251">Los depuradores para .NET respetan el uso de atributos como `DebuggerDisplay` y `DebuggerTypeProxy` , y afectan a la presentación estructurada de objetos en las ventanas de inspección del depurador.</span><span class="sxs-lookup"><span data-stu-id="e5b76-251">Debuggers for .NET respect the use of attributes such as `DebuggerDisplay` and `DebuggerTypeProxy`, and these affect the structured display of objects in debugger inspection windows.</span></span>
<span data-ttu-id="e5b76-252">El compilador de F # generaba automáticamente estos atributos para los tipos de Unión y de registro discriminados, pero no los tipos de clase, interfaz o estructura.</span><span class="sxs-lookup"><span data-stu-id="e5b76-252">The F# compiler automatically generated these attributes for discriminated union and record types, but not class, interface, or struct types.</span></span>

<span data-ttu-id="e5b76-253">Estos atributos se omiten en el formato de texto sin formato de F #, pero puede ser útil implementar estos métodos para mejorar las visualizaciones al depurar tipos de F #.</span><span class="sxs-lookup"><span data-stu-id="e5b76-253">These attributes are ignored in F# plain text formatting, but it can be useful to implement these methods to improve displays when debugging F# types.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5b76-254">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5b76-254">See also</span></span>

- [<span data-ttu-id="e5b76-255">Cadenas</span><span class="sxs-lookup"><span data-stu-id="e5b76-255">Strings</span></span>](strings.md)
- [<span data-ttu-id="e5b76-256">Registros</span><span class="sxs-lookup"><span data-stu-id="e5b76-256">Records</span></span>](records.md)
- [<span data-ttu-id="e5b76-257">Uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="e5b76-257">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="e5b76-258">F# Interactive</span><span class="sxs-lookup"><span data-stu-id="e5b76-258">F# Interactive</span></span>](fsharp-interactive-options.md)
