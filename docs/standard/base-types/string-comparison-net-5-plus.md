---
title: Cambios de comportamiento al comparar cadenas en .NET 5 +
description: Obtenga información sobre los cambios de comportamiento en la comparación de cadenas en .NET 5 y versiones posteriores en Windows.
ms.date: 12/07/2020
ms.openlocfilehash: a53c36b31785fb43c0aa5f5040042abb6d40031a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851756"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a><span data-ttu-id="5390f-103">Cambios de comportamiento al comparar cadenas en .NET 5 +</span><span class="sxs-lookup"><span data-stu-id="5390f-103">Behavior changes when comparing strings on .NET 5+</span></span>

<span data-ttu-id="5390f-104">.NET 5.0 presenta un cambio de comportamiento en el entorno de ejecución por el que las API de globalización [ahora usan ICU de forma predeterminada](../../core/compatibility/globalization/5.0/icu-globalization-api.md) en todas las plataformas admitidas.</span><span class="sxs-lookup"><span data-stu-id="5390f-104">.NET 5.0 introduces a runtime behavioral change where globalization APIs [now use ICU by default](../../core/compatibility/globalization/5.0/icu-globalization-api.md) across all supported platforms.</span></span> <span data-ttu-id="5390f-105">Esto representa una divergencia respecto a versiones anteriores de .NET Core y .NET Framework, que usan la funcionalidad de compatibilidad con el idioma nacional (NLS) del sistema operativo cuando se ejecutan en Windows.</span><span class="sxs-lookup"><span data-stu-id="5390f-105">This is a departure from earlier versions of .NET Core and from .NET Framework, which utilize the operating system's national language support (NLS) functionality when running on Windows.</span></span> <span data-ttu-id="5390f-106">Para obtener más información sobre estos cambios, incluidos los modificadores de compatibilidad que pueden revertir el cambio de comportamiento, vea [Globalización de .NET y ICU](../globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="5390f-106">For more information on these changes, including compatibility switches that can revert the behavior change, see [.NET globalization and ICU](../globalization-localization/globalization-icu.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5390f-107">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5390f-107">Reason for change</span></span>

<span data-ttu-id="5390f-108">Este cambio se presentó para unificar el comportamiento de globalización de .NET en todos los sistemas operativos compatibles.</span><span class="sxs-lookup"><span data-stu-id="5390f-108">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="5390f-109">También ofrece la posibilidad de que las aplicaciones agrupen sus propias bibliotecas de globalización en lugar de depender de las bibliotecas integradas del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5390f-109">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the OS's built-in libraries.</span></span> <span data-ttu-id="5390f-110">Para obtener más información, vea [la notificación de cambio importante](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span><span class="sxs-lookup"><span data-stu-id="5390f-110">For more information, see [the breaking change notification](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="5390f-111">Diferencias de comportamiento</span><span class="sxs-lookup"><span data-stu-id="5390f-111">Behavioral differences</span></span>

<span data-ttu-id="5390f-112">Si usa funciones como `string.IndexOf(string)` sin llamar a la sobrecarga que toma un argumento <xref:System.StringComparison>, es posible que tenga la intención de realizar una búsqueda *ordinal*, pero en su lugar, toma involuntariamente una dependencia del comportamiento específico de la cultura.</span><span class="sxs-lookup"><span data-stu-id="5390f-112">If you use functions like `string.IndexOf(string)` without calling the overload that takes a <xref:System.StringComparison> argument, you might intend to perform an *ordinal* search, but instead you inadvertently take a dependency on culture-specific behavior.</span></span> <span data-ttu-id="5390f-113">Dado que NLS y ICU implementan una lógica diferente en sus comparadores lingüísticos, los resultados de métodos como `string.IndexOf(string)` pueden devolver valores inesperados.</span><span class="sxs-lookup"><span data-stu-id="5390f-113">Since NLS and ICU implement different logic in their linguistic comparers, the results of methods like `string.IndexOf(string)` can return unexpected values.</span></span>

<span data-ttu-id="5390f-114">Esto puede manifestarse incluso en lugares donde no siempre se espera que las instalaciones de globalización estén activas.</span><span class="sxs-lookup"><span data-stu-id="5390f-114">This can manifest itself even in places where you aren't always expecting globalization facilities to be active.</span></span> <span data-ttu-id="5390f-115">Por ejemplo, el código siguiente puede generar una respuesta diferente en función del entorno de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="5390f-115">For example, the following code can produce a different answer depending on the current runtime.</span></span>

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a><span data-ttu-id="5390f-116">Protección frente a un comportamiento inesperado</span><span class="sxs-lookup"><span data-stu-id="5390f-116">Guard against unexpected behavior</span></span>

<span data-ttu-id="5390f-117">En esta sección se proporcionan dos opciones para tratar los cambios de comportamiento inesperados en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="5390f-117">This section provides two options for dealing with unexpected behavior changes in .NET 5.0.</span></span>

### <a name="enable-code-analyzers"></a><span data-ttu-id="5390f-118">Habilitación de analizadores de código</span><span class="sxs-lookup"><span data-stu-id="5390f-118">Enable code analyzers</span></span>

<span data-ttu-id="5390f-119">Los [analizadores de código](../../fundamentals/code-analysis/overview.md) pueden detectar sitios de llamada posiblemente erróneos.</span><span class="sxs-lookup"><span data-stu-id="5390f-119">[Code analyzers](../../fundamentals/code-analysis/overview.md) can detect possibly buggy call sites.</span></span> <span data-ttu-id="5390f-120">Para protegerse frente a comportamientos sorprendentes, se recomienda habilitar los analizadores de .NET Compiler Platform (Roslyn) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5390f-120">To help guard against any surprising behaviors, we recommend enabling .NET compiler platform (Roslyn) analyzers in your project.</span></span> <span data-ttu-id="5390f-121">Estos analizadores ayudan a marcar el código que podría estar utilizando un comparador lingüístico involuntariamente cuando se tiene previsto utilizar un comparador ordinal.</span><span class="sxs-lookup"><span data-stu-id="5390f-121">The analyzers help flag code that might inadvertently be using a linguistic comparer when an ordinal comparer was likely intended.</span></span> <span data-ttu-id="5390f-122">Las siguientes reglas deberían ayudar a marcar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="5390f-122">The following rules should help flag these issues:</span></span>

- [<span data-ttu-id="5390f-123">CA1307: Especificar StringComparison para mayor claridad</span><span class="sxs-lookup"><span data-stu-id="5390f-123">CA1307: Specify StringComparison for clarity</span></span>](../../fundamentals/code-analysis/quality-rules/ca1307.md)
- [<span data-ttu-id="5390f-124">CA1309: Utilizar StringComparison ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-124">CA1309: Use ordinal StringComparison</span></span>](../../fundamentals/code-analysis/quality-rules/ca1309.md)
- [<span data-ttu-id="5390f-125">CA1310: Especificar StringComparison para mayor corrección</span><span class="sxs-lookup"><span data-stu-id="5390f-125">CA1310: Specify StringComparison for correctness</span></span>](../../fundamentals/code-analysis/quality-rules/ca1310.md)

<span data-ttu-id="5390f-126">Estas reglas específicas no están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5390f-126">These specific rules aren't enabled by default.</span></span> <span data-ttu-id="5390f-127">Para habilitarlas y hacer que las infracciones se muestren como errores de compilación, establezca las siguientes propiedades en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="5390f-127">To enable them and show any violations as build errors, set the following properties in your project file:</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
  <WarningsAsErrors>$(WarningsAsErrors);CA1307;CA1309;CA1310</WarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="5390f-128">En el fragmento de código siguiente se muestran ejemplos de código que producen advertencias o errores pertinentes del analizador de código.</span><span class="sxs-lookup"><span data-stu-id="5390f-128">The following snippet shows examples of code that produces the relevant code analyzer warnings or errors.</span></span>

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1310 for string; CA1307 matches on char ','
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

<span data-ttu-id="5390f-129">Del mismo modo, al crear una instancia de una colección ordenada de cadenas u ordenar una colección basada en cadenas existente, especifique un comparador explícito.</span><span class="sxs-lookup"><span data-stu-id="5390f-129">Similarly, when instantiating a sorted collection of strings or sorting an existing string-based collection, specify an explicit comparer.</span></span>

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

### <a name="revert-back-to-nls-behaviors"></a><span data-ttu-id="5390f-130">Reversión a los comportamientos de NLS</span><span class="sxs-lookup"><span data-stu-id="5390f-130">Revert back to NLS behaviors</span></span>

<span data-ttu-id="5390f-131">Para revertir las aplicaciones de .NET 5 a los comportamientos de NLS anteriores cuando se ejecutan en Windows, siga los pasos descritos en [Globalización de .NET e ICU](../globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="5390f-131">To revert .NET 5 applications back to older NLS behaviors when running on Windows, follow the steps in [.NET Globalization and ICU](../globalization-localization/globalization-icu.md).</span></span> <span data-ttu-id="5390f-132">Este modificador de compatibilidad para toda la aplicación debe establecerse en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5390f-132">This application-wide compatibility switch must be set at the application level.</span></span> <span data-ttu-id="5390f-133">Las bibliotecas individuales no pueden aceptar este comportamiento ni excluirse de él.</span><span class="sxs-lookup"><span data-stu-id="5390f-133">Individual libraries cannot opt-in or opt-out of this behavior.</span></span>

> [!TIP]
> <span data-ttu-id="5390f-134">Le recomendamos encarecidamente que habilite las reglas de análisis de código [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) y [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) para ayudar a mejorar la higiene del código y detectar los errores latentes existentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-134">We strongly recommend you enable the [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md), and [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) code analysis rules to help improve code hygiene and discover any existing latent bugs.</span></span> <span data-ttu-id="5390f-135">Para obtener más información, vea [Habilitación de analizadores de código](#enable-code-analyzers).</span><span class="sxs-lookup"><span data-stu-id="5390f-135">For more information, see [Enable code analyzers](#enable-code-analyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5390f-136">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5390f-136">Affected APIs</span></span>

<span data-ttu-id="5390f-137">La mayoría de las aplicaciones de .NET no encontrará ningún comportamiento inesperado provocado por los cambios en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="5390f-137">Most .NET applications won't encounter any unexpected behaviors due to the changes in .NET 5.0.</span></span> <span data-ttu-id="5390f-138">Sin embargo, debido al número de API afectadas y el grado en que estas API son fundamentales para el ecosistema de .NET más amplio, debe ser consciente del potencial de .NET 5.0 para introducir comportamientos no deseados o exponer errores latentes que ya existen en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5390f-138">However, due to the number of affected APIs and how foundational these APIs are to the wider .NET ecosystem, you should be aware of the potential for .NET 5.0 to introduce unwanted behaviors or to expose latent bugs that already exist in your application.</span></span>

<span data-ttu-id="5390f-139">Entre las API afectadas están las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5390f-139">The affected APIs include:</span></span>

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <span data-ttu-id="5390f-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (la mayoría de los miembros)</span><span class="sxs-lookup"><span data-stu-id="5390f-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="5390f-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (la mayoría de los miembros)</span><span class="sxs-lookup"><span data-stu-id="5390f-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="5390f-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (al ordenar matrices de cadenas)</span><span class="sxs-lookup"><span data-stu-id="5390f-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting arrays of strings)</span></span>
- <span data-ttu-id="5390f-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (cuando los elementos de lista son cadenas)</span><span class="sxs-lookup"><span data-stu-id="5390f-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="5390f-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (cuando las claves son cadenas)</span><span class="sxs-lookup"><span data-stu-id="5390f-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="5390f-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (cuando las claves son cadenas)</span><span class="sxs-lookup"><span data-stu-id="5390f-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="5390f-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (cuando el conjunto contiene cadenas)</span><span class="sxs-lookup"><span data-stu-id="5390f-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

> [!NOTE]
> <span data-ttu-id="5390f-147">Esta no es una lista exhaustiva de las API afectadas.</span><span class="sxs-lookup"><span data-stu-id="5390f-147">This is not an exhaustive list of affected APIs.</span></span>

<span data-ttu-id="5390f-148">Todas las API anteriores usan la búsqueda y comparación de cadenas *lingüística* con la [referencia cultural actual](xref:System.Threading.Thread.CurrentCulture) del subproceso, de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5390f-148">All of the above APIs use *linguistic* string searching and comparison using the thread's [current culture](xref:System.Threading.Thread.CurrentCulture), by default.</span></span> <span data-ttu-id="5390f-149">Las diferencias entre la búsqueda y comparación *lingüística* y *ordinal* se mencionan en [Diferencias entre la búsqueda y comparación lingüística y ordinal](#ordinal-vs-linguistic-search-and-comparison).</span><span class="sxs-lookup"><span data-stu-id="5390f-149">The differences between *linguistic* and *ordinal* search and comparison are called out in the [Ordinal vs. linguistic search and comparison](#ordinal-vs-linguistic-search-and-comparison).</span></span>

<span data-ttu-id="5390f-150">Dado que ICU implementa comparaciones de cadenas lingüísticas de forma diferente a NLS, las aplicaciones basadas en Windows que se actualizan a .NET 5.0 desde una versión anterior de .NET Core o .NET Framework y que llaman a una de las API afectadas pueden observar que las API comienzan a presentar comportamientos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-150">Because ICU implements linguistic string comparisons differently from NLS, Windows-based applications that upgrade to .NET 5.0 from an earlier version of .NET Core or .NET Framework and that call one of the affected APIs may notice that the APIs begin exhibiting different behaviors.</span></span>

### <a name="exceptions"></a><span data-ttu-id="5390f-151">Excepciones</span><span class="sxs-lookup"><span data-stu-id="5390f-151">Exceptions</span></span>

* <span data-ttu-id="5390f-152">Si una API acepta un parámetro explícito `StringComparison` o `CultureInfo`, ese parámetro invalida el comportamiento predeterminado de la API.</span><span class="sxs-lookup"><span data-stu-id="5390f-152">If an API accepts an explicit `StringComparison` or `CultureInfo` parameter, that parameter overrides the API's default behavior.</span></span>
* <span data-ttu-id="5390f-153">Los miembros de `System.String` donde el primer parámetro es de tipo `char` (por ejemplo, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>) usan la búsqueda ordinal, a menos que el que llama pase un argumento `StringComparison` explícito que especifique `CurrentCulture[IgnoreCase]` o `InvariantCulture[IgnoreCase]`.</span><span class="sxs-lookup"><span data-stu-id="5390f-153">`System.String` members where the first parameter is of type `char` (for example, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>) use ordinal searching, unless the caller passes an explicit `StringComparison` argument that specifies `CurrentCulture[IgnoreCase]` or `InvariantCulture[IgnoreCase]`.</span></span>

<span data-ttu-id="5390f-154">Para obtener un análisis más detallado del comportamiento predeterminado de cada API de <xref:System.String>, vea la sección [Tipos de comparación y búsqueda predeterminados](#default-search-and-comparison-types).</span><span class="sxs-lookup"><span data-stu-id="5390f-154">For a more detailed analysis of the default behavior of each <xref:System.String> API, see the [Default search and comparison types](#default-search-and-comparison-types) section.</span></span>

## <a name="ordinal-vs-linguistic-search-and-comparison"></a><span data-ttu-id="5390f-155">Diferencias entre la búsqueda y comparación lingüística y ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-155">Ordinal vs. linguistic search and comparison</span></span>

<span data-ttu-id="5390f-156">La búsqueda y comparación *ordinal* (también conocida como *no lingüística*) descompone una cadena en sus elementos `char` individuales y realiza una búsqueda o comparación carácter por carácter.</span><span class="sxs-lookup"><span data-stu-id="5390f-156">*Ordinal* (also known as *non-linguistic*) search and comparison decomposes a string into its individual `char` elements and performs a char-by-char search or comparison.</span></span> <span data-ttu-id="5390f-157">Por ejemplo, las cadenas `"dog"` y `"dog"` se comparan como *iguales* en un comparador de `Ordinal`, ya que las dos cadenas están compuestas de la misma secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5390f-157">For example, the strings `"dog"` and `"dog"` compare as *equal* under an `Ordinal` comparer, since the two strings consist of the exact same sequence of chars.</span></span> <span data-ttu-id="5390f-158">Sin embargo, `"dog"` y `"Dog"` se comparan como *no iguales* en un comparador de `Ordinal`, porque no se componen de la misma secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5390f-158">However, `"dog"` and `"Dog"` compare as *not equal* under an `Ordinal` comparer, because they don't consist of the exact same sequence of chars.</span></span> <span data-ttu-id="5390f-159">Es decir, el punto de código de `'D'` en mayúsculas `U+0044` aparece antes del punto de código de `'d'` en minúsculas `U+0064`, lo que resulta en una clasificación `"dog"` antes de `"Dog"`.</span><span class="sxs-lookup"><span data-stu-id="5390f-159">That is, uppercase `'D'`'s code point `U+0044` occurs before lowercase `'d'`'s code point `U+0064`, resulting in `"dog"` sorting before `"Dog"`.</span></span>

<span data-ttu-id="5390f-160">Un comparador de `OrdinalIgnoreCase` sigue funcionando carácter por carácter, pero elimina las diferencias entre mayúsculas y minúsculas mientras se realiza la operación.</span><span class="sxs-lookup"><span data-stu-id="5390f-160">An `OrdinalIgnoreCase` comparer still operates on a char-by-char basis, but it eliminates case differences while performing the operation.</span></span> <span data-ttu-id="5390f-161">En un comparador de `OrdinalIgnoreCase`, los pares de caracteres `'d'` y `'D'` se comparan como *iguales*, al igual que los pares de caracteres `'á'` y `'Á'`.</span><span class="sxs-lookup"><span data-stu-id="5390f-161">Under an `OrdinalIgnoreCase` comparer, the char pairs `'d'` and `'D'` compare as *equal*, as do the char pairs `'á'` and `'Á'`.</span></span> <span data-ttu-id="5390f-162">Pero el carácter sin acento `'a'` se compara como *no igual* al carácter acentuado `'á'`.</span><span class="sxs-lookup"><span data-stu-id="5390f-162">But the unaccented char `'a'` compares as *not equal* to the accented char `'á'`.</span></span>

<span data-ttu-id="5390f-163">En la tabla siguiente se proporcionan algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5390f-163">Some examples of this are provided in the following table:</span></span>

| <span data-ttu-id="5390f-164">cadena 1</span><span class="sxs-lookup"><span data-stu-id="5390f-164">String 1</span></span> | <span data-ttu-id="5390f-165">Cadena 2</span><span class="sxs-lookup"><span data-stu-id="5390f-165">String 2</span></span> | <span data-ttu-id="5390f-166">Comparación `Ordinal`</span><span class="sxs-lookup"><span data-stu-id="5390f-166">`Ordinal` comparison</span></span> | <span data-ttu-id="5390f-167">Comparación `OrdinalIgnoreCase`</span><span class="sxs-lookup"><span data-stu-id="5390f-167">`OrdinalIgnoreCase` comparison</span></span> |
|---|---|---|---|
| `"dog"` | `"dog"` | <span data-ttu-id="5390f-168">equal</span><span class="sxs-lookup"><span data-stu-id="5390f-168">equal</span></span> | <span data-ttu-id="5390f-169">equal</span><span class="sxs-lookup"><span data-stu-id="5390f-169">equal</span></span> |
| `"dog"` | `"Dog"` | <span data-ttu-id="5390f-170">no igual</span><span class="sxs-lookup"><span data-stu-id="5390f-170">not equal</span></span> | <span data-ttu-id="5390f-171">equal</span><span class="sxs-lookup"><span data-stu-id="5390f-171">equal</span></span> |
| `"resume"` | `"Resume"` | <span data-ttu-id="5390f-172">no igual</span><span class="sxs-lookup"><span data-stu-id="5390f-172">not equal</span></span> | <span data-ttu-id="5390f-173">equal</span><span class="sxs-lookup"><span data-stu-id="5390f-173">equal</span></span> |
| `"resume"` | `"résumé"` | <span data-ttu-id="5390f-174">no igual</span><span class="sxs-lookup"><span data-stu-id="5390f-174">not equal</span></span> | <span data-ttu-id="5390f-175">no igual</span><span class="sxs-lookup"><span data-stu-id="5390f-175">not equal</span></span> |

<span data-ttu-id="5390f-176">Unicode también permite que las cadenas tengan varias representaciones en memoria diferentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-176">Unicode also allows strings to have several different in-memory representations.</span></span> <span data-ttu-id="5390f-177">Por ejemplo, una e aguda (é) se puede representar de dos formas posibles:</span><span class="sxs-lookup"><span data-stu-id="5390f-177">For example, an e-acute (é) can be represented in two possible ways:</span></span>

* <span data-ttu-id="5390f-178">Un solo carácter `'é'` literal (también escrito como `'\u00E9'`).</span><span class="sxs-lookup"><span data-stu-id="5390f-178">A single literal `'é'` character (also written as `'\u00E9'`).</span></span>
* <span data-ttu-id="5390f-179">Un carácter `'e'` literal sin acento, seguido de un carácter modificador de acento de combinación `'\u0301'`.</span><span class="sxs-lookup"><span data-stu-id="5390f-179">A literal unaccented `'e'` character, followed by a combining accent modifier character `'\u0301'`.</span></span>

<span data-ttu-id="5390f-180">Esto significa que las siguientes _cuatro_ cadenas dan como resultado `"résumé"` cuando se muestran, aunque sus piezas constituyentes son diferentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-180">This means that the following _four_ strings all result in `"résumé"` when displayed, even though their constituent pieces are different.</span></span> <span data-ttu-id="5390f-181">Las cadenas usan una combinación de caracteres `'é'` literales o caracteres `'e'` literales no acentuados más el modificador de acento de combinación `'\u0301'`.</span><span class="sxs-lookup"><span data-stu-id="5390f-181">The strings use a combination of literal `'é'` characters or literal unaccented `'e'` characters plus the combining accent modifier `'\u0301'`.</span></span>

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

<span data-ttu-id="5390f-182">En un comparador ordinal, ninguna de estas cadenas resulta igual en la comparación con otra.</span><span class="sxs-lookup"><span data-stu-id="5390f-182">Under an ordinal comparer, none of these strings compare as equal to each other.</span></span> <span data-ttu-id="5390f-183">Esto se debe a que todas contienen secuencias de caracteres subyacentes diferentes, aunque cuando se representan en la pantalla, todas tienen el mismo aspecto.</span><span class="sxs-lookup"><span data-stu-id="5390f-183">This is because they all contain different underlying char sequences, even though when they're rendered to the screen, they all look the same.</span></span>

<span data-ttu-id="5390f-184">Al realizar una operación de `string.IndexOf(..., StringComparison.Ordinal)`, el tiempo de ejecución busca una coincidencia de subcadena exacta.</span><span class="sxs-lookup"><span data-stu-id="5390f-184">When performing a `string.IndexOf(..., StringComparison.Ordinal)` operation, the runtime looks for an exact substring match.</span></span> <span data-ttu-id="5390f-185">Los resultados son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="5390f-185">The results are as follows.</span></span>

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

<span data-ttu-id="5390f-186">Las rutinas de búsqueda y comparación ordinales nunca se ven afectadas por la configuración de referencia cultural del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="5390f-186">Ordinal search and comparison routines are never affected by the current thread's culture setting.</span></span>

<span data-ttu-id="5390f-187">Las rutinas de búsqueda y comparación *lingüísticas* descomponen una cadena en *elementos de intercalación* y realizan búsquedas o comparaciones en estos elementos.</span><span class="sxs-lookup"><span data-stu-id="5390f-187">*Linguistic* search and comparison routines decompose a string into *collation elements* and perform searches or comparisons on these elements.</span></span> <span data-ttu-id="5390f-188">No hay necesariamente una asignación de 1:1 entre los caracteres de una cadena y sus elementos de intercalación constituyentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-188">There's not necessarily a 1:1 mapping between a string's characters and its constituent collation elements.</span></span> <span data-ttu-id="5390f-189">Por ejemplo, una cadena de longitud 2 puede constar de un solo elemento de intercalación.</span><span class="sxs-lookup"><span data-stu-id="5390f-189">For example, a string of length 2 may consist of only a single collation element.</span></span> <span data-ttu-id="5390f-190">Cuando se comparan dos cadenas en modo lingüístico, el comparador comprueba si los elementos de intercalación de las dos cadenas tienen el mismo significado semántico, incluso si los caracteres literales de la cadena son diferentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-190">When two strings are compared in a linguistic-aware fashion, the comparer checks whether the two strings' collation elements have the same semantic meaning, even if the string's literal characters are different.</span></span>

<span data-ttu-id="5390f-191">Considere de nuevo la cadena `"résumé"` y sus cuatro representaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-191">Consider again the string `"résumé"` and its four different representations.</span></span> <span data-ttu-id="5390f-192">En la tabla siguiente se muestra cada representación dividida en sus elementos de intercalación.</span><span class="sxs-lookup"><span data-stu-id="5390f-192">The following table shows each representation broken down into its collation elements.</span></span>

| <span data-ttu-id="5390f-193">String</span><span class="sxs-lookup"><span data-stu-id="5390f-193">String</span></span> | <span data-ttu-id="5390f-194">Como elementos de intercalación</span><span class="sxs-lookup"><span data-stu-id="5390f-194">As collation elements</span></span> |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

<span data-ttu-id="5390f-195">Un elemento de intercalación se corresponde de forma flexible con lo que los lectores considerarían un solo carácter o un clúster de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5390f-195">A collation element corresponds loosely to what readers would think of as a single character or cluster of characters.</span></span> <span data-ttu-id="5390f-196">Es conceptualmente similar a un [grupo de grafemas](character-encoding-introduction.md#grapheme-clusters) pero engloba un paraguas algo más grande.</span><span class="sxs-lookup"><span data-stu-id="5390f-196">It's conceptually similar to a [grapheme cluster](character-encoding-introduction.md#grapheme-clusters) but encompasses a somewhat larger umbrella.</span></span>

<span data-ttu-id="5390f-197">En un comparador lingüístico, no es necesario realizar coincidencias exactas.</span><span class="sxs-lookup"><span data-stu-id="5390f-197">Under a linguistic comparer, exact matches aren't necessary.</span></span> <span data-ttu-id="5390f-198">En su lugar, los elementos de intercalación se comparan en función de su significado semántico.</span><span class="sxs-lookup"><span data-stu-id="5390f-198">Collation elements are instead compared based on their semantic meaning.</span></span> <span data-ttu-id="5390f-199">Por ejemplo, un comparador trata las subcadenas `"\u00E9"` y `"e\u0301"` como iguales, ya que ambas significan semánticamente "una e minúscula con un modificador de acento agudo".</span><span class="sxs-lookup"><span data-stu-id="5390f-199">For example, a linguistic comparer treats the substrings `"\u00E9"` and `"e\u0301"` as equal since they both semantically mean "a lowercase e with an acute accent modifier."</span></span> <span data-ttu-id="5390f-200">Esto permite que el método `IndexOf` coincida con la subcadena `"e\u0301"` dentro de una cadena más grande que contiene la subcadena semánticamente equivalente `"\u00E9"`, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5390f-200">This allows the `IndexOf` method to match the substring `"e\u0301"` within a larger string that contains the semantically equivalent substring `"\u00E9"`, as shown in the following code sample.</span></span>

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

<span data-ttu-id="5390f-201">Como consecuencia de esto, dos cadenas de longitudes diferentes pueden compararse como iguales si se utiliza una comparación lingüística.</span><span class="sxs-lookup"><span data-stu-id="5390f-201">As a consequence of this, two strings of different lengths may compare as equal if a linguistic comparison is used.</span></span> <span data-ttu-id="5390f-202">Los que llaman deben tener cuidado de no utilizar la lógica de casos especiales que se ocupa de la longitud de la cadena en tales escenarios.</span><span class="sxs-lookup"><span data-stu-id="5390f-202">Callers should take care not to special-case logic that deals with string length in such scenarios.</span></span>

<span data-ttu-id="5390f-203">Las rutinas de búsqueda y comparación *que tienen en cuenta la referencia cultural* son una forma especial de las rutinas de comparación y búsqueda lingüísticas.</span><span class="sxs-lookup"><span data-stu-id="5390f-203">*Culture-aware* search and comparison routines are a special form of linguistic search and comparison routines.</span></span> <span data-ttu-id="5390f-204">En un comparador que tiene en cuenta la referencia cultural, el concepto de elemento de intercalación se amplía para incluir información específica de la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="5390f-204">Under a culture-aware comparer, the concept of a collation element is extended to include information specific to the specified culture.</span></span>

<span data-ttu-id="5390f-205">Por ejemplo, [en el alfabeto húngaro](https://en.wikipedia.org/wiki/Hungarian_alphabet), cuando los dos caracteres \<dz\> aparecen uno junto al otro, se consideran una letra única distinta de \<d\> o \<z\>.</span><span class="sxs-lookup"><span data-stu-id="5390f-205">For example, [in the Hungarian alphabet](https://en.wikipedia.org/wiki/Hungarian_alphabet), when the two characters \<dz\> appear back-to-back, they are considered their own unique letter distinct from either \<d\> or \<z\>.</span></span> <span data-ttu-id="5390f-206">Esto significa que cuando se ve \<dz\> en una cadena, un comparador que conozca la cultura húngara lo trata como un único elemento de intercalación.</span><span class="sxs-lookup"><span data-stu-id="5390f-206">This means that when \<dz\> is seen in a string, a Hungarian culture-aware comparer treats it as a single collation element.</span></span>

| <span data-ttu-id="5390f-207">String</span><span class="sxs-lookup"><span data-stu-id="5390f-207">String</span></span> | <span data-ttu-id="5390f-208">Como elementos de intercalación</span><span class="sxs-lookup"><span data-stu-id="5390f-208">As collation elements</span></span> | <span data-ttu-id="5390f-209">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5390f-209">Remarks</span></span> |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | <span data-ttu-id="5390f-210">(mediante un comparador lingüístico estándar)</span><span class="sxs-lookup"><span data-stu-id="5390f-210">(using a standard linguistic comparer)</span></span> |
| `"endz"` | `"e" + "n" + "dz"` | <span data-ttu-id="5390f-211">(mediante un comparador consciente de la referencia cultural húngara)</span><span class="sxs-lookup"><span data-stu-id="5390f-211">(using a Hungarian culture-aware comparer)</span></span> |

<span data-ttu-id="5390f-212">Cuando se usa un comparador compatible con referencias culturales húngaras, que la cadena `"endz"` *no* termina con la subcadena `"z"`, ya que <\dz\> y <\z\> se consideran elementos de intercalación con un significado semántico diferente.</span><span class="sxs-lookup"><span data-stu-id="5390f-212">When using a Hungarian culture-aware comparer, this means that the string `"endz"` *does not* end with the substring `"z"`, as <\dz\> and <\z\> are considered collation elements with different semantic meaning.</span></span>

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - <span data-ttu-id="5390f-213">Comportamiento: Los comparadores lingüísticos y conocedores de las referencias culturales pueden someterse a ajustes de comportamiento de vez en cuando.</span><span class="sxs-lookup"><span data-stu-id="5390f-213">Behavior: Linguistic and culture-aware comparers can undergo behavioral adjustments from time to time.</span></span> <span data-ttu-id="5390f-214">Tanto ICU como la antigua instalación de Windows NLS se han actualizado para tener en cuenta cómo cambian los idiomas del mundo.</span><span class="sxs-lookup"><span data-stu-id="5390f-214">Both ICU and the older Windows NLS facility are updated to account for how world languages change.</span></span> <span data-ttu-id="5390f-215">Para obtener más información, consulte la entrada de blog [Actividad de datos de la configuración regional (cultura)](/archive/blogs/shawnste/locale-culture-data-churn).</span><span class="sxs-lookup"><span data-stu-id="5390f-215">For more information, see the blog post [Locale (culture) data churn](/archive/blogs/shawnste/locale-culture-data-churn).</span></span> <span data-ttu-id="5390f-216">El comportamiento del comparador *ordinal* nunca cambiará, ya que realiza una búsqueda y comparación bit a bit exacta.</span><span class="sxs-lookup"><span data-stu-id="5390f-216">The *Ordinal* comparer's behavior will never change since it performs exact bitwise searching and comparison.</span></span> <span data-ttu-id="5390f-217">Sin embargo, el comportamiento del comparador de *OrdinalIgnoreCase* puede cambiar a medida que Unicode crece para abarcar más conjuntos de caracteres y corrige las omisiones en los datos de mayúsculas y minúsculas existentes.</span><span class="sxs-lookup"><span data-stu-id="5390f-217">However, the *OrdinalIgnoreCase* comparer's behavior may change as Unicode grows to encompass more character sets and corrects omissions in existing casing data.</span></span>
> - <span data-ttu-id="5390f-218">Uso: Los comparadores `StringComparison.InvariantCulture` y `StringComparison.InvariantCultureIgnoreCase` son comparadores lingüísticos que no tienen en cuenta la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="5390f-218">Usage: The comparers `StringComparison.InvariantCulture` and `StringComparison.InvariantCultureIgnoreCase` are linguistic comparers that are not culture-aware.</span></span> <span data-ttu-id="5390f-219">Es decir, estos comparadores entienden conceptos como el carácter acentuado é que tiene varias representaciones subyacentes posibles y que todas esas representaciones deben tratarse igual.</span><span class="sxs-lookup"><span data-stu-id="5390f-219">That is, these comparers understand concepts such as the accented character é having multiple possible underlying representations, and that all such representations should be treated equal.</span></span> <span data-ttu-id="5390f-220">Sin embargo, los comparadores lingüísticos que no tienen en cuenta la referencia cultural no contendrán un tratamiento especial para \<dz\> como si fuera distinto de \<d\> o \<z\>, como se mostró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5390f-220">But non-culture-aware linguistic comparers won't contain special handling for \<dz\> as distinct from \<d\> or \<z\>, as shown above.</span></span> <span data-ttu-id="5390f-221">Tampoco se trata de caracteres especiales como el alemán Eszett (ß).</span><span class="sxs-lookup"><span data-stu-id="5390f-221">They also won't special-case characters like the German Eszett (ß).</span></span>

<span data-ttu-id="5390f-222">.NET también ofrece el *modo de globalización invariable*.</span><span class="sxs-lookup"><span data-stu-id="5390f-222">.NET also offers the *invariant globalization mode*.</span></span> <span data-ttu-id="5390f-223">Este modo de inclusión deshabilita las rutas de acceso al código que se ocupan de las rutinas de comparación y búsqueda lingüística.</span><span class="sxs-lookup"><span data-stu-id="5390f-223">This opt-in mode disables code paths that deal with linguistic search and comparison routines.</span></span> <span data-ttu-id="5390f-224">En este modo, todas las operaciones utilizan comportamientos *Ordinal* o *OrdinalIgnoreCase*, independientemente del argumento `CultureInfo` o `StringComparison` que proporcione el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5390f-224">In this mode, all operations use *Ordinal* or *OrdinalIgnoreCase* behaviors, regardless of what `CultureInfo` or `StringComparison` argument the caller provides.</span></span> <span data-ttu-id="5390f-225">Para obtener más información, vea [Opciones de configuración del entorno de ejecución para globalización](../../core/run-time-config/globalization.md) y [Modo invariable de globalización de .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5390f-225">For more information, see [Run-time configuration options for globalization](../../core/run-time-config/globalization.md) and [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

<span data-ttu-id="5390f-226">Para obtener más información, consulte [Procedimientos recomendados para la comparación de cadenas en .NET](best-practices-strings.md).</span><span class="sxs-lookup"><span data-stu-id="5390f-226">For more information, see [Best practices for comparing strings in .NET](best-practices-strings.md).</span></span>

## <a name="security-implications"></a><span data-ttu-id="5390f-227">Implicaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="5390f-227">Security implications</span></span>

<span data-ttu-id="5390f-228">Si la aplicación usa una API afectada para filtrar, se recomienda habilitar las reglas de análisis de código CA1307 y CA1309 para ayudar a ubicar los lugares en los que se puede haber usado una búsqueda lingüística involuntariamente en lugar de una búsqueda ordinal.</span><span class="sxs-lookup"><span data-stu-id="5390f-228">If your app uses an affected API for filtering, we recommend enabling the CA1307 and CA1309 code analysis rules to help locate places where a linguistic search may have inadvertently been used instead of an ordinal search.</span></span> <span data-ttu-id="5390f-229">Los patrones de código como los siguientes pueden ser susceptibles a vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5390f-229">Code patterns like the following may be susceptible to security exploits.</span></span>

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

<span data-ttu-id="5390f-230">Dado que el método `string.IndexOf(string)` utiliza una búsqueda lingüística de forma predeterminada, es posible que una cadena contenga un carácter `'<'` o `'&'` literal y que la rutina `string.IndexOf(string)` devuelva `-1`, lo que indica que no se encontró la subcadena de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5390f-230">Because the `string.IndexOf(string)` method uses a linguistic search by default, it's possible for a string to contain a literal `'<'` or `'&'` character and for the `string.IndexOf(string)` routine to return `-1`, indicating that the search substring was not found.</span></span> <span data-ttu-id="5390f-231">Las reglas de análisis de código CA1307 y CA1309 marcan estos sitios de llamada y alertan al desarrollador de que hay un posible problema.</span><span class="sxs-lookup"><span data-stu-id="5390f-231">Code analysis rules CA1307 and CA1309 flag such call sites and alert the developer that there's a potential problem.</span></span>

## <a name="default-search-and-comparison-types"></a><span data-ttu-id="5390f-232">Tipos de comparación y búsqueda predeterminados</span><span class="sxs-lookup"><span data-stu-id="5390f-232">Default search and comparison types</span></span>

<span data-ttu-id="5390f-233">En la tabla siguiente se enumeran los tipos de comparación y búsqueda predeterminados para varias API de cadena y con aspecto de cadena.</span><span class="sxs-lookup"><span data-stu-id="5390f-233">The following table lists the default search and comparison types for various string and string-like APIs.</span></span> <span data-ttu-id="5390f-234">Si el autor de la llamada proporciona un parámetro `CultureInfo` o `StringComparison` explícito, ese parámetro se respetará con cualquier valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5390f-234">If the caller provides an explicit `CultureInfo` or `StringComparison` parameter, that parameter will be honored over any default.</span></span>

| <span data-ttu-id="5390f-235">API</span><span class="sxs-lookup"><span data-stu-id="5390f-235">API</span></span> | <span data-ttu-id="5390f-236">Comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="5390f-236">Default behavior</span></span> | <span data-ttu-id="5390f-237">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5390f-237">Remarks</span></span> |
|---|---|---|
| `string.Compare` | <span data-ttu-id="5390f-238">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-238">CurrentCulture</span></span> | |
| `string.CompareTo` | <span data-ttu-id="5390f-239">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-239">CurrentCulture</span></span> | |
| `string.Contains` | <span data-ttu-id="5390f-240">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-240">Ordinal</span></span> | |
| `string.EndsWith` | <span data-ttu-id="5390f-241">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-241">Ordinal</span></span> | <span data-ttu-id="5390f-242">(cuando el primer parámetro es `char`)</span><span class="sxs-lookup"><span data-stu-id="5390f-242">(when the first parameter is a `char`)</span></span> |
| `string.EndsWith` | <span data-ttu-id="5390f-243">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-243">CurrentCulture</span></span> | <span data-ttu-id="5390f-244">(cuando el primer parámetro es `string`)</span><span class="sxs-lookup"><span data-stu-id="5390f-244">(when the first parameter is a `string`)</span></span> |
| `string.Equals` | <span data-ttu-id="5390f-245">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-245">Ordinal</span></span> | |
| `string.GetHashCode` | <span data-ttu-id="5390f-246">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-246">Ordinal</span></span> | |
| `string.IndexOf` | <span data-ttu-id="5390f-247">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-247">Ordinal</span></span> | <span data-ttu-id="5390f-248">(cuando el primer parámetro es `char`)</span><span class="sxs-lookup"><span data-stu-id="5390f-248">(when the first parameter is a `char`)</span></span> |
| `string.IndexOf` | <span data-ttu-id="5390f-249">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-249">CurrentCulture</span></span> | <span data-ttu-id="5390f-250">(cuando el primer parámetro es `string`)</span><span class="sxs-lookup"><span data-stu-id="5390f-250">(when the first parameter is a `string`)</span></span> |
| `string.IndexOfAny` | <span data-ttu-id="5390f-251">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-251">Ordinal</span></span> | |
| `string.LastIndexOf` | <span data-ttu-id="5390f-252">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-252">Ordinal</span></span> | <span data-ttu-id="5390f-253">(cuando el primer parámetro es `char`)</span><span class="sxs-lookup"><span data-stu-id="5390f-253">(when the first parameter is a `char`)</span></span> |
| `string.LastIndexOf` | <span data-ttu-id="5390f-254">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-254">CurrentCulture</span></span> | <span data-ttu-id="5390f-255">(cuando el primer parámetro es `string`)</span><span class="sxs-lookup"><span data-stu-id="5390f-255">(when the first parameter is a `string`)</span></span> |
| `string.LastIndexOfAny` | <span data-ttu-id="5390f-256">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-256">Ordinal</span></span> | |
| `string.Replace` | <span data-ttu-id="5390f-257">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-257">Ordinal</span></span> | |
| `string.Split` | <span data-ttu-id="5390f-258">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-258">Ordinal</span></span> | |
| `string.StartsWith` | <span data-ttu-id="5390f-259">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-259">Ordinal</span></span> | <span data-ttu-id="5390f-260">(cuando el primer parámetro es `char`)</span><span class="sxs-lookup"><span data-stu-id="5390f-260">(when the first parameter is a `char`)</span></span> |
| `string.StartsWith` | <span data-ttu-id="5390f-261">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-261">CurrentCulture</span></span> | <span data-ttu-id="5390f-262">(cuando el primer parámetro es `string`)</span><span class="sxs-lookup"><span data-stu-id="5390f-262">(when the first parameter is a `string`)</span></span> |
| `string.ToLower` | <span data-ttu-id="5390f-263">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-263">CurrentCulture</span></span> | |
| `string.ToLowerInvariant` | <span data-ttu-id="5390f-264">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-264">InvariantCulture</span></span> | |
| `string.ToUpper` | <span data-ttu-id="5390f-265">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-265">CurrentCulture</span></span> | |
| `string.ToUpperInvariant` | <span data-ttu-id="5390f-266">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-266">InvariantCulture</span></span> | |
| `string.Trim` | <span data-ttu-id="5390f-267">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-267">Ordinal</span></span> | |
| `string.TrimEnd` | <span data-ttu-id="5390f-268">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-268">Ordinal</span></span> | |
| `string.TrimStart` | <span data-ttu-id="5390f-269">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-269">Ordinal</span></span> | |
| `string == string` | <span data-ttu-id="5390f-270">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-270">Ordinal</span></span> | |
| `string != string` | <span data-ttu-id="5390f-271">Ordinal</span><span class="sxs-lookup"><span data-stu-id="5390f-271">Ordinal</span></span> | |

<span data-ttu-id="5390f-272">A diferencia de las API de `string`, todas las API de `MemoryExtensions` realizan búsquedas y comparaciones *ordinales* de forma predeterminada, con las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="5390f-272">Unlike `string` APIs, all `MemoryExtensions` APIs perform *Ordinal* searches and comparisons by default, with the following exceptions.</span></span>

| <span data-ttu-id="5390f-273">API</span><span class="sxs-lookup"><span data-stu-id="5390f-273">API</span></span> | <span data-ttu-id="5390f-274">Comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="5390f-274">Default behavior</span></span> | <span data-ttu-id="5390f-275">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5390f-275">Remarks</span></span> |
|---|---|---|
| `MemoryExtensions.ToLower` | <span data-ttu-id="5390f-276">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-276">CurrentCulture</span></span> | <span data-ttu-id="5390f-277">(cuando se pasa un argumento `CultureInfo` nulo)</span><span class="sxs-lookup"><span data-stu-id="5390f-277">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToLowerInvariant` | <span data-ttu-id="5390f-278">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-278">InvariantCulture</span></span> | |
| `MemoryExtensions.ToUpper` | <span data-ttu-id="5390f-279">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-279">CurrentCulture</span></span> | <span data-ttu-id="5390f-280">(cuando se pasa un argumento `CultureInfo` nulo)</span><span class="sxs-lookup"><span data-stu-id="5390f-280">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToUpperInvariant` | <span data-ttu-id="5390f-281">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="5390f-281">InvariantCulture</span></span> | |

<span data-ttu-id="5390f-282">Una consecuencia es que al convertir el código de consumir `string` a consumir `ReadOnlySpan<char>`, pueden introducirse cambios de comportamiento involuntariamente.</span><span class="sxs-lookup"><span data-stu-id="5390f-282">A consequence is that when converting code from consuming `string` to consuming `ReadOnlySpan<char>`, behavioral changes may be introduced inadvertently.</span></span> <span data-ttu-id="5390f-283">A continuación se muestra un ejemplo de ello.</span><span class="sxs-lookup"><span data-stu-id="5390f-283">An example of this follows.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

<span data-ttu-id="5390f-284">La manera recomendada de solucionarlo es pasar un parámetro `StringComparison` explícito a estas API.</span><span class="sxs-lookup"><span data-stu-id="5390f-284">The recommended way to address this is to pass an explicit `StringComparison` parameter to these APIs.</span></span> <span data-ttu-id="5390f-285">Las reglas de análisis de código CA1307 y CA1309 pueden ayudarle.</span><span class="sxs-lookup"><span data-stu-id="5390f-285">The code analysis rules CA1307 and CA1309 can assist with this.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a><span data-ttu-id="5390f-286">Vea también</span><span class="sxs-lookup"><span data-stu-id="5390f-286">See also</span></span>

- [<span data-ttu-id="5390f-287">Cambios importantes de la globalización</span><span class="sxs-lookup"><span data-stu-id="5390f-287">Globalization breaking changes</span></span>](../../core/compatibility/globalization.md)
- [<span data-ttu-id="5390f-288">Procedimientos recomendados para la comparación de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="5390f-288">Best practices for comparing strings in .NET</span></span>](best-practices-strings.md)
- [<span data-ttu-id="5390f-289">Comparación de cadenas en C#</span><span class="sxs-lookup"><span data-stu-id="5390f-289">How to compare strings in C#</span></span>](../../csharp/how-to/compare-strings.md)
- [<span data-ttu-id="5390f-290">Globalización de .NET e ICU</span><span class="sxs-lookup"><span data-stu-id="5390f-290">.NET globalization and ICU</span></span>](../globalization-localization/globalization-icu.md)
- [<span data-ttu-id="5390f-291">Operaciones de cadena que tienen en cuenta la referencia cultural frente a las ordinales</span><span class="sxs-lookup"><span data-stu-id="5390f-291">Ordinal vs. culture-sensitive string operations</span></span>](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [<span data-ttu-id="5390f-292">Información general sobre el análisis de código fuente de .NET</span><span class="sxs-lookup"><span data-stu-id="5390f-292">Overview of .NET source code analysis</span></span>](../../fundamentals/code-analysis/overview.md)
