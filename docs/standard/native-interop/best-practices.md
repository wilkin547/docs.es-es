---
title: Procedimientos recomendados de interoperabilidad nativa (.NET)
description: Conozca los procedimientos recomendados para interactuar con componentes nativos en. NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 90a707830049b5edf574b83e7ca03ec30527b001
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "56411481"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="0b349-103">Procedimientos recomendados de interoperabilidad nativa</span><span class="sxs-lookup"><span data-stu-id="0b349-103">Native interoperability best practices</span></span>

<span data-ttu-id="0b349-104">.NET ofrece diversas formas de personalizar el código de interoperabilidad nativa.</span><span class="sxs-lookup"><span data-stu-id="0b349-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="0b349-105">En este artículo se incluye la guía que siguen los equipos de .NET de Microsoft para realizar la interoperabilidad nativa.</span><span class="sxs-lookup"><span data-stu-id="0b349-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="0b349-106">Orientación general</span><span class="sxs-lookup"><span data-stu-id="0b349-106">General guidance</span></span>

<span data-ttu-id="0b349-107">La guía de esta sección se aplica a todos los escenarios de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="0b349-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="0b349-108">**✔️ UTILICE** la misma nomenclatura y uso de mayúsculas y minúsculas para los métodos y parámetros que el método nativo al que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="0b349-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="0b349-109">**✔️ PLANTÉESE** usar la misma nomenclatura y uso de mayúsculas y minúsculas para los valores constantes.</span><span class="sxs-lookup"><span data-stu-id="0b349-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="0b349-110">**✔️ UTILICE** los tipos de .NET que se asignen lo más cerca posible del tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="0b349-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="0b349-111">Por ejemplo, en C#, utilice `uint` cuando el tipo nativo es `unsigned int`.</span><span class="sxs-lookup"><span data-stu-id="0b349-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="0b349-112">**✔️ UTILICE** solamente atributos `[In]` y `[Out]` cuando quiera que el comportamiento sea diferente al predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0b349-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="0b349-113">**✔️ PLANTÉESE** usar <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> para agrupar los búferes de matriz nativa.</span><span class="sxs-lookup"><span data-stu-id="0b349-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="0b349-114">**✔️ PLANTÉESE** encapsular las declaraciones P/Invoke en una clase con el mismo nombre y uso de mayúsculas y minúsculas que la biblioteca nativa.</span><span class="sxs-lookup"><span data-stu-id="0b349-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="0b349-115">De esta forma, los atributos `[DllImport]` usan la característica de lenguaje `nameof` de C# para pasar el nombre de la biblioteca nativa y garantizar que no escribió mal el nombre de la biblioteca nativa.</span><span class="sxs-lookup"><span data-stu-id="0b349-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="0b349-116">Configuración del atributo DllImport</span><span class="sxs-lookup"><span data-stu-id="0b349-116">DllImport attribute settings</span></span>

| <span data-ttu-id="0b349-117">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0b349-117">Setting</span></span> | <span data-ttu-id="0b349-118">Default</span><span class="sxs-lookup"><span data-stu-id="0b349-118">Default</span></span> | <span data-ttu-id="0b349-119">Recomendación</span><span class="sxs-lookup"><span data-stu-id="0b349-119">Recommendation</span></span> | <span data-ttu-id="0b349-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="0b349-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="0b349-121">Mantener el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="0b349-121">keep default</span></span>  | <span data-ttu-id="0b349-122">Cuando se establece explícitamente en false, los valores devueltos de HRESULT con errores se convierten en excepciones (y el valor devuelto en la definición se convierte en NULL).</span><span class="sxs-lookup"><span data-stu-id="0b349-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="0b349-123">Depende de la API</span><span class="sxs-lookup"><span data-stu-id="0b349-123">depends on the API</span></span>  | <span data-ttu-id="0b349-124">Establezca este valor en true si la API utiliza GetLastError y use Marshal.GetLastWin32Error para obtener el valor.</span><span class="sxs-lookup"><span data-stu-id="0b349-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="0b349-125">Si la API establece una condición que indica que tiene un error, obtenga el error antes de realizar otras llamadas para evitar que accidentalmente se sobrescriba.</span><span class="sxs-lookup"><span data-stu-id="0b349-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="0b349-126">`CharSet.None`, que vuelve al comportamiento `CharSet.Ansi`</span><span class="sxs-lookup"><span data-stu-id="0b349-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="0b349-127">Usar explícitamente `CharSet.Unicode` o `CharSet.Ansi` cuando haya cadenas o caracteres en la definición</span><span class="sxs-lookup"><span data-stu-id="0b349-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="0b349-128">Esto especifica el comportamiento de serialización de cadenas y lo que hace `ExactSpelling` cuando `false`.</span><span class="sxs-lookup"><span data-stu-id="0b349-128">This specifies marshalling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="0b349-129">Tenga en cuenta que `CharSet.Ansi` es realmente UTF8 en Unix.</span><span class="sxs-lookup"><span data-stu-id="0b349-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="0b349-130">_La mayoría de las veces_ Windows utiliza Unicode, mientras que Unix usa UTF8.</span><span class="sxs-lookup"><span data-stu-id="0b349-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="0b349-131">Obtenga más información en la [documentación de juegos de caracteres](./charset.md).</span><span class="sxs-lookup"><span data-stu-id="0b349-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="0b349-132">Establezca este valor en true y obtenga una ventaja de rendimiento ligero, ya que el entorno de ejecución no busca nombres de función alternativos con un sufijo "A" o "W" en función del valor de la configuración de `CharSet` ("A" para `CharSet.Ansi` y "W" para `CharSet.Unicode`).</span><span class="sxs-lookup"><span data-stu-id="0b349-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="0b349-133">Parámetros de cadena</span><span class="sxs-lookup"><span data-stu-id="0b349-133">String parameters</span></span>

<span data-ttu-id="0b349-134">Cuando el juego de caracteres es Unicode o el argumento se marca explícitamente como `[MarshalAs(UnmanagedType.LPWSTR)]` _y_ la cadena se pasa por valor (`ref` ni `out`), la cadena se anclará y se usará directamente mediante código nativo (en lugar de una copia).</span><span class="sxs-lookup"><span data-stu-id="0b349-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="0b349-135">Recuerde marcar `[DllImport]` como `Charset.Unicode`, a menos que explícitamente desee un tratamiento ANSI de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="0b349-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="0b349-136">**❌ NO** use parámetros `[Out] string`.</span><span class="sxs-lookup"><span data-stu-id="0b349-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="0b349-137">Los parámetros de cadena pasados por valor con el atributo `[Out]` pueden llegar a desestabilizar el entorno de ejecución si la cadena es una cadena internalizada.</span><span class="sxs-lookup"><span data-stu-id="0b349-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="0b349-138">Obtenga más información sobre el internamiento de cadenas en la documentación de <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b349-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0b349-139">**❌EVITE** usar parámetros `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="0b349-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="0b349-140">La serialización `StringBuilder` *siempre* crea una copia del búfer nativo.</span><span class="sxs-lookup"><span data-stu-id="0b349-140">`StringBuilder` marshalling *always* creates a native buffer copy.</span></span> <span data-ttu-id="0b349-141">Por lo tanto, puede ser extremadamente ineficaz.</span><span class="sxs-lookup"><span data-stu-id="0b349-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="0b349-142">Siga el escenario típico de una llamada a una API de Windows que toma una cadena:</span><span class="sxs-lookup"><span data-stu-id="0b349-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="0b349-143">Cree un SB de la capacidad deseada (asigna la capacidad administrada) **{1}**.</span><span class="sxs-lookup"><span data-stu-id="0b349-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="0b349-144">Invocar</span><span class="sxs-lookup"><span data-stu-id="0b349-144">Invoke</span></span>
   1. <span data-ttu-id="0b349-145">Asigna un búfer nativo **{2}**.</span><span class="sxs-lookup"><span data-stu-id="0b349-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="0b349-146">Copia el contenido si `[In]` _(el valor predeterminado de un `StringBuilder` parámetro)_.</span><span class="sxs-lookup"><span data-stu-id="0b349-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="0b349-147">Copia el búfer de nativo en una matriz administrada recién asignada si `[Out]` **{3}** _(también el valor predeterminado de`StringBuilder`)_.</span><span class="sxs-lookup"><span data-stu-id="0b349-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="0b349-148">`ToString()` asigna otra matriz administrada **{4}**.</span><span class="sxs-lookup"><span data-stu-id="0b349-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="0b349-149">Es decir, asignaciones *{4}* para obtener una cadena del código nativo.</span><span class="sxs-lookup"><span data-stu-id="0b349-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="0b349-150">Lo mejor que puede hacer para limitar esto consiste en reutilizar `StringBuilder` en otra llamada, pero esta todavía solo guarda la asignación *1*.</span><span class="sxs-lookup"><span data-stu-id="0b349-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="0b349-151">Es mucho mejor usar y almacenar en caché un búfer de caracteres de `ArrayPool`; después, puede llegar a la asignación de `ToString()` en las llamadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="0b349-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="0b349-152">El otro problema con `StringBuilder` es que siempre copia la copia de seguridad del búfer de retorno en el primer valor NULL.</span><span class="sxs-lookup"><span data-stu-id="0b349-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="0b349-153">Si la cadena pasada anterior no está terminada o es una cadena terminada en doble NULL, el valor P/Invoke será incorrecto en el mejor de los casos.</span><span class="sxs-lookup"><span data-stu-id="0b349-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="0b349-154">Si *usa* `StringBuilder`, un último problema es que la capacidad **no** incluyen un valor NULL oculto, que siempre se tiene en cuenta en la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="0b349-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="0b349-155">Es habitual equivocarse, ya que la mayoría de las API quieren que el tamaño del búfer *incluyan* el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="0b349-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="0b349-156">Esto puede dar lugar a asignaciones innecesarias.</span><span class="sxs-lookup"><span data-stu-id="0b349-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="0b349-157">Además, este problema impide que el entorno de ejecución optimice la serialización `StringBuilder` para minimizar las copias.</span><span class="sxs-lookup"><span data-stu-id="0b349-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshalling to minimize copies.</span></span>

<span data-ttu-id="0b349-158">**✔️ PLANTÉESE** usar `char[]` desde `ArrayPool`.</span><span class="sxs-lookup"><span data-stu-id="0b349-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="0b349-159">Para obtener más información sobre la serialización cadenas, vea [Cálculo de referencias predeterminado para cadenas](../../framework/interop/default-marshaling-for-strings.md) y [Personalización de la serialización de campos de cadena](customize-parameter-marshalling.md#customizing-string-parameters).</span><span class="sxs-lookup"><span data-stu-id="0b349-159">For more information on string marshalling, see [Default Marshalling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshalling](customize-parameter-marshalling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="0b349-160">__Específico de Windows__</span><span class="sxs-lookup"><span data-stu-id="0b349-160">__Windows Specific__</span></span>  
> <span data-ttu-id="0b349-161">Para las cadenas `[Out]`, CLR utilizará `CoTaskMemFree` de forma predeterminada para liberar las cadenas o `SysStringFree` para las cadenas que están marcadas como `UnmanagedType.BSTR`.</span><span class="sxs-lookup"><span data-stu-id="0b349-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="0b349-162">**Para la mayoría de las API con un búfer de cadena de salida:**</span><span class="sxs-lookup"><span data-stu-id="0b349-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="0b349-163">El número de caracteres pasados debe incluir el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="0b349-163">The passed in character count must include the null.</span></span> <span data-ttu-id="0b349-164">Si el valor devuelto es menor que el número de caracteres pasados, la llamada se realiza correctamente y el valor es el número de caracteres *sin* el carácter NULL.</span><span class="sxs-lookup"><span data-stu-id="0b349-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="0b349-165">En caso contrario, el número es el tamaño del búfer necesario *incluyendo* el carácter NULL.</span><span class="sxs-lookup"><span data-stu-id="0b349-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
> - <span data-ttu-id="0b349-166">Pase 5 y obtenga 4: la cadena tiene 4 caracteres de longitud con un valor NULL final.</span><span class="sxs-lookup"><span data-stu-id="0b349-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="0b349-167">Pase 5 y obtenga 6: la cadena tiene 5 caracteres de longitud y necesita un búfer de 6 caracteres para contener el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="0b349-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> [<span data-ttu-id="0b349-168">Tipos de datos de Windows para cadenas</span><span class="sxs-lookup"><span data-stu-id="0b349-168">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="0b349-169">Parámetros y campos booleanos</span><span class="sxs-lookup"><span data-stu-id="0b349-169">Boolean parameters and fields</span></span>

<span data-ttu-id="0b349-170">Los valores booleanos se desordenan fácilmente.</span><span class="sxs-lookup"><span data-stu-id="0b349-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="0b349-171">De forma predeterminada, .NET `bool` se serializa en un valor `BOOL` de Windows de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="0b349-171">By default, a .NET `bool` is marshalled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="0b349-172">Sin embargo, los tipos `_Bool` y `bool` en C y C++ tienen un *solo* byte.</span><span class="sxs-lookup"><span data-stu-id="0b349-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="0b349-173">De este modo, puede ser complicado realizar un seguimiento de los errores porque la mitad del valor devuelto se descarta, con lo que *posiblemente* se modifica el resultado.</span><span class="sxs-lookup"><span data-stu-id="0b349-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="0b349-174">Para obtener más información sobre la serialización de valores `bool` de .NET en tipos `bool` de C o C++, consulte la documentación sobre [cómo personalizar la serialización de campos booleanos](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span><span class="sxs-lookup"><span data-stu-id="0b349-174">For more for information on marshalling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshalling](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span></span>

## <a name="guids"></a><span data-ttu-id="0b349-175">GUID</span><span class="sxs-lookup"><span data-stu-id="0b349-175">GUIDs</span></span>

<span data-ttu-id="0b349-176">Los GUID se pueden usar directamente en las firmas.</span><span class="sxs-lookup"><span data-stu-id="0b349-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="0b349-177">Muchas de las API de Windows toman los alias de tipo `GUID&` como `REFIID`.</span><span class="sxs-lookup"><span data-stu-id="0b349-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="0b349-178">Cuando se pasan por referencia, se pueden pasar por `ref` o con el atributo `[MarshalAs(UnmanagedType.LPStruct)]`.</span><span class="sxs-lookup"><span data-stu-id="0b349-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="0b349-179">GUID</span><span class="sxs-lookup"><span data-stu-id="0b349-179">GUID</span></span> | <span data-ttu-id="0b349-180">GUID por referencia</span><span class="sxs-lookup"><span data-stu-id="0b349-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="0b349-181">**❌ NO** use `[MarshalAs(UnmanagedType.LPStruct)]` para parámetros GUID que no sean `ref`.</span><span class="sxs-lookup"><span data-stu-id="0b349-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="0b349-182">Tipos que pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="0b349-182">Blittable types</span></span>

<span data-ttu-id="0b349-183">Los tipos que pueden transferirse en bloque de bits son tipos que tienen la misma representación de nivel de bits en código administrado y nativo.</span><span class="sxs-lookup"><span data-stu-id="0b349-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="0b349-184">Por lo tanto, no es necesario convertirlos a otro formato para serializarlos con código nativo como punto de partida o destino, y como se mejora el rendimiento, deben preferirse estos tipos.</span><span class="sxs-lookup"><span data-stu-id="0b349-184">As such they do not need to be converted to another format to be marshalled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="0b349-185">**Tipos que pueden transferirse en bloque de bits:**</span><span class="sxs-lookup"><span data-stu-id="0b349-185">**Blittable types:**</span></span>

- <span data-ttu-id="0b349-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="0b349-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="0b349-187">Matrices unidimensionales no anidadas de tipos que puede transferirse en bloque de bits (por ejemplo, `int[]`).</span><span class="sxs-lookup"><span data-stu-id="0b349-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="0b349-188">Estructuras y clases con distribución fija que solo tienen tipos de valor que pueden transferirse en bloque de bits, por ejemplo, campos.</span><span class="sxs-lookup"><span data-stu-id="0b349-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="0b349-189">La distribución fija requiere `[StructLayout(LayoutKind.Sequential)]` o `[StructLayout(LayoutKind.Explicit)]`.</span><span class="sxs-lookup"><span data-stu-id="0b349-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="0b349-190">De forma predeterminada, las estructuras son `LayoutKind.Sequential` y las clases, `LayoutKind.Auto`.</span><span class="sxs-lookup"><span data-stu-id="0b349-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="0b349-191">**Tipos que no se pueden transferir en bloque de bits:**</span><span class="sxs-lookup"><span data-stu-id="0b349-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="0b349-192">**Tipos que A VECES se pueden transferir en bloque de bits:**</span><span class="sxs-lookup"><span data-stu-id="0b349-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="0b349-193">`char`, `string`</span><span class="sxs-lookup"><span data-stu-id="0b349-193">`char`, `string`</span></span>

<span data-ttu-id="0b349-194">Cuando se pasan tipos que pueden transferirse en bloque de bits por referencia, está anclados simplemente por el serializador en lugar de estar copiados en un búfer intermedio.</span><span class="sxs-lookup"><span data-stu-id="0b349-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="0b349-195">Las clases se pasan intrínsecamente por referencia y las estructuras se pasan por referencia cuando se usa con `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="0b349-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="0b349-196">`char` puede transferirse en bloque de bits en una matriz unidimensional **o** si forma parte de un tipo que lo contiene, se marca explícitamente con `[StructLayout]` con `CharSet = CharSet.Unicode`.</span><span class="sxs-lookup"><span data-stu-id="0b349-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="0b349-197">`string` puede transferirse en bloque de bits si no está contenido en otro tipo y si se pasa como un argumento que se marca con `[MarshalAs(UnmanagedType.LPWStr)]` o `[DllImport]` tiene `CharSet = CharSet.Unicode` establecido.</span><span class="sxs-lookup"><span data-stu-id="0b349-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="0b349-198">Puede ver si un tipo puede transferirse en bloque de bits al intentar crear un controlador `GCHandle` anclado.</span><span class="sxs-lookup"><span data-stu-id="0b349-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="0b349-199">Si el tipo no es una cadena o no puede transferirse en bloque de bits, `GCHandle.Alloc` producirá una excepción `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="0b349-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="0b349-200">**✔️ CREE** estructuras que puedan transferirse en bloque de bits cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="0b349-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="0b349-201">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="0b349-201">For more information, see:</span></span>

- [<span data-ttu-id="0b349-202">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="0b349-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="0b349-203">Serialización de tipos</span><span class="sxs-lookup"><span data-stu-id="0b349-203">Type Marshalling</span></span>](type-marshalling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="0b349-204">Forma de mantener activos los objetos administrados</span><span class="sxs-lookup"><span data-stu-id="0b349-204">Keeping managed objects alive</span></span>

<span data-ttu-id="0b349-205">`GC.KeepAlive()` asegurará que un objeto permanezca dentro del ámbito hasta que se alcance el método KeepAlive.</span><span class="sxs-lookup"><span data-stu-id="0b349-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="0b349-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) permite que el serializador mantenga un objeto activo para la duración de P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="0b349-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="0b349-207">Se puede usar en lugar de `IntPtr` en firmas de método.</span><span class="sxs-lookup"><span data-stu-id="0b349-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="0b349-208">`SafeHandle` reemplaza esta clase de forma eficaz y se debe usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0b349-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="0b349-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) permite anclar un objeto administrado y obtener el puntero nativo.</span><span class="sxs-lookup"><span data-stu-id="0b349-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="0b349-210">El patrón básico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b349-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="0b349-211">Anclar no es la acción predeterminada para `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="0b349-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="0b349-212">El otro patrón principal se usa para pasar una referencia a un objeto administrado a través de código nativo y devolverse al código administrado, normalmente con una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0b349-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="0b349-213">Este es el patrón:</span><span class="sxs-lookup"><span data-stu-id="0b349-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="0b349-214">No olvide que `GCHandle` debe liberarse explícitamente para evitar fugas de memoria.</span><span class="sxs-lookup"><span data-stu-id="0b349-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="0b349-215">Tipos de datos de Windows comunes</span><span class="sxs-lookup"><span data-stu-id="0b349-215">Common Windows data types</span></span>

<span data-ttu-id="0b349-216">Esta es una lista de tipos de datos que se usan frecuentemente en las API de Win32 y qué tipos de C# se usan al llamar al código de Win32.</span><span class="sxs-lookup"><span data-stu-id="0b349-216">Here is a list of data types commonly used in Win32 APIs and which C# types to use when calling into the Win32 code.</span></span>

<span data-ttu-id="0b349-217">Los siguientes tipos tienen el mismo tamaño en Windows 32 bits y 64 bits, a pesar de sus nombres.</span><span class="sxs-lookup"><span data-stu-id="0b349-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="0b349-218">Ancho</span><span class="sxs-lookup"><span data-stu-id="0b349-218">Width</span></span> | <span data-ttu-id="0b349-219">Windows</span><span class="sxs-lookup"><span data-stu-id="0b349-219">Windows</span></span>          | <span data-ttu-id="0b349-220">C (Windows)</span><span class="sxs-lookup"><span data-stu-id="0b349-220">C (Windows)</span></span>          | <span data-ttu-id="0b349-221">C#</span><span class="sxs-lookup"><span data-stu-id="0b349-221">C#</span></span>       | <span data-ttu-id="0b349-222">Alternativa</span><span class="sxs-lookup"><span data-stu-id="0b349-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="0b349-223">32</span><span class="sxs-lookup"><span data-stu-id="0b349-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="0b349-224">8</span><span class="sxs-lookup"><span data-stu-id="0b349-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="0b349-225">8</span><span class="sxs-lookup"><span data-stu-id="0b349-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="0b349-226">8</span><span class="sxs-lookup"><span data-stu-id="0b349-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="0b349-227">8</span><span class="sxs-lookup"><span data-stu-id="0b349-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="0b349-228">16</span><span class="sxs-lookup"><span data-stu-id="0b349-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="0b349-229">16</span><span class="sxs-lookup"><span data-stu-id="0b349-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="0b349-230">16</span><span class="sxs-lookup"><span data-stu-id="0b349-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="0b349-231">16</span><span class="sxs-lookup"><span data-stu-id="0b349-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="0b349-232">16</span><span class="sxs-lookup"><span data-stu-id="0b349-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="0b349-233">32</span><span class="sxs-lookup"><span data-stu-id="0b349-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="0b349-234">32</span><span class="sxs-lookup"><span data-stu-id="0b349-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="0b349-235">32</span><span class="sxs-lookup"><span data-stu-id="0b349-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="0b349-236">32</span><span class="sxs-lookup"><span data-stu-id="0b349-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="0b349-237">64</span><span class="sxs-lookup"><span data-stu-id="0b349-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="0b349-238">64</span><span class="sxs-lookup"><span data-stu-id="0b349-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="0b349-239">64</span><span class="sxs-lookup"><span data-stu-id="0b349-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="0b349-240">64</span><span class="sxs-lookup"><span data-stu-id="0b349-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="0b349-241">64</span><span class="sxs-lookup"><span data-stu-id="0b349-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="0b349-242">32</span><span class="sxs-lookup"><span data-stu-id="0b349-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="0b349-243">32</span><span class="sxs-lookup"><span data-stu-id="0b349-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |


<span data-ttu-id="0b349-244">Los siguientes tipos, que son punteros, siguen el ancho de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0b349-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="0b349-245">Use `IntPtr`/`UIntPtr` para estos.</span><span class="sxs-lookup"><span data-stu-id="0b349-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="0b349-246">Tipos de puntero con signo (use `IntPtr`)</span><span class="sxs-lookup"><span data-stu-id="0b349-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="0b349-247">Tipos de puntero sin signo (use `UIntPtr`)</span><span class="sxs-lookup"><span data-stu-id="0b349-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="0b349-248">Un tipo `PVOID` de Windows que es un tipo `void*` de C se pueden serializar como `IntPtr` o `UIntPtr`, pero prefiere `void*` cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="0b349-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="0b349-249">Tipos de datos de Windows</span><span class="sxs-lookup"><span data-stu-id="0b349-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="0b349-250">Intervalos de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0b349-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="0b349-251">Estructuras</span><span class="sxs-lookup"><span data-stu-id="0b349-251">Structs</span></span>

<span data-ttu-id="0b349-252">Las estructuras administradas se crean en la pila y no se quitan hasta que el método se devuelve.</span><span class="sxs-lookup"><span data-stu-id="0b349-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="0b349-253">Por definición, se anclan (la recolección de elementos no utilizados no las mueve).</span><span class="sxs-lookup"><span data-stu-id="0b349-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="0b349-254">Puede simplemente tomar la dirección en bloques de código no seguros si el código nativo no utilizará el puntero más allá del final del método actual.</span><span class="sxs-lookup"><span data-stu-id="0b349-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="0b349-255">Las estructuras de bits/bytes son mucho más eficaces, ya que simplemente puede utilizarlas directamente la capa de serialización.</span><span class="sxs-lookup"><span data-stu-id="0b349-255">Blittable structs are much more performant as they can simply be used directly by the marshalling layer.</span></span> <span data-ttu-id="0b349-256">Trate de crear estructuras que pueden transferirse en bloque de bits (por ejemplo, evite `bool`).</span><span class="sxs-lookup"><span data-stu-id="0b349-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="0b349-257">Para obtener más información, consulte la sección [Tipos que pueden transferirse en bloque de bits](#blittable-types).</span><span class="sxs-lookup"><span data-stu-id="0b349-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="0b349-258">*Si* la estructura se puede transferir en bloque de bits, use `sizeof()` en lugar de `Marshal.SizeOf<MyStruct>()` para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0b349-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="0b349-259">Como se mencionó anteriormente, puede validar que el tipo se pueda transferir en bloques de bits al intentar crear un controlador `GCHandle` anclado.</span><span class="sxs-lookup"><span data-stu-id="0b349-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="0b349-260">Si el tipo no es una cadena o no puede transferirse en bloque de bits, `GCHandle.Alloc` producirá una excepción `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="0b349-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="0b349-261">Los punteros a las estructuras en definiciones deben pasarse por `ref` o usar `unsafe` y `*`.</span><span class="sxs-lookup"><span data-stu-id="0b349-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="0b349-262">**✔️ HAGA COINCIDIR** la estructura administrada lo máximo posible con la forma y los nombres que se usan en el encabezado o la documentación oficial de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0b349-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="0b349-263">**✔️ USE** el tipo `sizeof()` de C# en lugar de `Marshal.SizeOf<MyStruct>()` para las estructuras que pueden transferirse en bloque de bits con el fin de mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0b349-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="0b349-264">Una matriz como `INT_PTR Reserved1[2]` tiene que serializarse a dos campos `IntPtr`, `Reserved1a` y `Reserved1b`.</span><span class="sxs-lookup"><span data-stu-id="0b349-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="0b349-265">Cuando la matriz nativa es un tipo primitivo, podemos usar la palabra clave `fixed` para escribir de forma más limpia.</span><span class="sxs-lookup"><span data-stu-id="0b349-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="0b349-266">Por ejemplo, `SYSTEM_PROCESS_INFORMATION` tiene este aspecto en el encabezado nativo:</span><span class="sxs-lookup"><span data-stu-id="0b349-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="0b349-267">En C#, podemos escribirlo así:</span><span class="sxs-lookup"><span data-stu-id="0b349-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="0b349-268">Sin embargo, existen los búferes fijos tienen algunas trampas.</span><span class="sxs-lookup"><span data-stu-id="0b349-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="0b349-269">Los búferes fijos de tipos que no pueden transferirse en bloques de bits no se serializarán correctamente, por lo que la matriz en contexto debe expandirse a varios campos individuales.</span><span class="sxs-lookup"><span data-stu-id="0b349-269">Fixed buffers of non-blittable types won't be correctly marshalled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="0b349-270">Además, en .NET Framework y .NET Core antes de la versión 3.0, si una estructura que contiene un campo de búfer fijo se anida dentro de una estructura que no puede transferirse en bloque de bits, el campo de búfer fijo no se serializará correctamente al código nativo.</span><span class="sxs-lookup"><span data-stu-id="0b349-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshalled to native code.</span></span>
