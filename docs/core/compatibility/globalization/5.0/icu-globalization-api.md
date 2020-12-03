---
title: 'Cambio importante: Las API de globalización usan bibliotecas de ICU en Windows'
description: Obtenga información sobre el cambio importante de globalización en .NET 5.0, donde se usan las bibliotecas de ICU para la funcionalidad de globalización en lugar de NLS.
ms.date: 05/19/2020
ms.openlocfilehash: efc20e21969ea4a83c9122e40b262e1dc38e6770
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760277"
---
# <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="83a26-103">Las API de globalización usan bibliotecas de ICU en Windows</span><span class="sxs-lookup"><span data-stu-id="83a26-103">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="83a26-104">.NET 5.0 y versiones posteriores usan bibliotecas de [componentes internacionales para Unicode (ICU)](http://site.icu-project.org/home) para la funcionalidad de globalización cuando se ejecutan en la actualización de mayo de 2019 de Windows 10 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="83a26-104">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

## <a name="change-description"></a><span data-ttu-id="83a26-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="83a26-105">Change description</span></span>

<span data-ttu-id="83a26-106">En .NET Core 1.0 a 3.1 y .NET Framework 4 y versiones posteriores, las bibliotecas de .NET usan las API de [compatibilidad con el idioma nacional (NLS)](/windows/win32/intl/national-language-support) para la funcionalidad de globalización en Windows.</span><span class="sxs-lookup"><span data-stu-id="83a26-106">In .NET Core 1.0 - 3.1 and .NET Framework 4 and later, .NET libraries use [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality on Windows.</span></span> <span data-ttu-id="83a26-107">Por ejemplo, las funciones de NLS se usaban para comparar cadenas, obtener información de referencia cultural y aplicar mayúsculas y minúsculas en las cadenas en la referencia cultural adecuada.</span><span class="sxs-lookup"><span data-stu-id="83a26-107">For example, NLS functions were used to compare strings, get culture information, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="83a26-108">A partir de .NET 5.0, si una aplicación se ejecuta en la actualización de mayo de 2019 de Windows 10 o posterior, las bibliotecas de .NET usan las API de globalización de [ICU](http://site.icu-project.org/home) de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="83a26-108">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs, by default.</span></span>

> [!NOTE]
> <span data-ttu-id="83a26-109">Las versiones de la actualización de mayo de 2019 de Windows 10 o posteriores incluyen la biblioteca nativa de ICU.</span><span class="sxs-lookup"><span data-stu-id="83a26-109">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="83a26-110">Si el tiempo de ejecución de .NET no puede cargar ICU, utilizará NLS en su lugar.</span><span class="sxs-lookup"><span data-stu-id="83a26-110">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="83a26-111">Diferencias de comportamiento</span><span class="sxs-lookup"><span data-stu-id="83a26-111">Behavioral differences</span></span>

<span data-ttu-id="83a26-112">Es posible que vea cambios en la aplicación aunque no se dé cuenta de que usa las instalaciones de globalización.</span><span class="sxs-lookup"><span data-stu-id="83a26-112">You might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="83a26-113">En esta sección se enumeran algunos de los cambios de comportamiento que podría ver, pero también hay otros.</span><span class="sxs-lookup"><span data-stu-id="83a26-113">This section lists a couple of the behavioral changes you might see, but there are others too.</span></span>

### <a name="stringindexof"></a><span data-ttu-id="83a26-114">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="83a26-114">String.IndexOf</span></span>

<span data-ttu-id="83a26-115">Considere el código siguiente que llama a <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> para buscar el índice del carácter de nueva línea en una cadena.</span><span class="sxs-lookup"><span data-stu-id="83a26-115">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="83a26-116">En versiones anteriores de .NET en Windows, el fragmento de código imprime `6`.</span><span class="sxs-lookup"><span data-stu-id="83a26-116">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="83a26-117">En .NET 5.0 y versiones posteriores en Windows 19H1 y versiones posteriores, el fragmento de código imprime `-1`.</span><span class="sxs-lookup"><span data-stu-id="83a26-117">In .NET 5.0 and later versions on Windows 19H1 and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="83a26-118">Para corregir este código mediante la realización de una búsqueda ordinal en lugar de una búsqueda según la referencia cultural, llame a la sobrecarga <xref:System.String.IndexOf(System.String,System.StringComparison)> y pase <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> como argumento.</span><span class="sxs-lookup"><span data-stu-id="83a26-118">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="83a26-119">Puede ejecutar las reglas de análisis de código [CA1307: Especificar StringComparison para mayor claridad](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) y [CA1309: Usar StringComparison ordinal](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) para buscar estos sitios de llamada en el código.</span><span class="sxs-lookup"><span data-stu-id="83a26-119">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="83a26-120">Para más información, consulte [Cambios de comportamiento al comparar cadenas en .NET 5 +](../../../../standard/base-types/string-comparison-net-5-plus.md).</span><span class="sxs-lookup"><span data-stu-id="83a26-120">For more information, see [Behavior changes when comparing strings on .NET 5+](../../../../standard/base-types/string-comparison-net-5-plus.md).</span></span>

### <a name="currency-symbol"></a><span data-ttu-id="83a26-121">Símbolo de moneda</span><span class="sxs-lookup"><span data-stu-id="83a26-121">Currency symbol</span></span>

<span data-ttu-id="83a26-122">Considere el código siguiente que da formato a una cadena con el especificador de formato de divisa `C`.</span><span class="sxs-lookup"><span data-stu-id="83a26-122">Consider the following code that formats a string using the currency format specifier `C`.</span></span> <span data-ttu-id="83a26-123">La referencia cultural del subproceso actual se establece en una referencia cultural que solo incluye el idioma, no el país.</span><span class="sxs-lookup"><span data-stu-id="83a26-123">The current thread's culture is set to a culture that includes only the language and not the country.</span></span>

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- <span data-ttu-id="83a26-124">En versiones anteriores de .NET en Windows, el valor del texto es `"100,00 €"`.</span><span class="sxs-lookup"><span data-stu-id="83a26-124">In previous versions of .NET on Windows, the value of text is `"100,00 €"`.</span></span>
- <span data-ttu-id="83a26-125">En .NET 5.0 y versiones posteriores en Windows 19H1 y versiones posteriores, el valor del texto es `"100,00 ¤"`, que usa el símbolo de moneda internacional en lugar del euro.</span><span class="sxs-lookup"><span data-stu-id="83a26-125">In .NET 5.0 and later versions on Windows 19H1 and later versions, the value of text is `"100,00 ¤"`, which uses the international currency symbol instead of the euro.</span></span> <span data-ttu-id="83a26-126">En ICU, el diseño es que una moneda es una propiedad de un país o región, no un idioma.</span><span class="sxs-lookup"><span data-stu-id="83a26-126">In ICU, the design is that a currency is a property of a country or region, not a language.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="83a26-127">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="83a26-127">Reason for change</span></span>

<span data-ttu-id="83a26-128">Este cambio se presentó para unificar el comportamiento de globalización de .NET en todos los sistemas operativos compatibles.</span><span class="sxs-lookup"><span data-stu-id="83a26-128">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="83a26-129">También ofrece la posibilidad de que las aplicaciones agrupen sus propias bibliotecas de globalización en lugar de depender de las bibliotecas integradas del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="83a26-129">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the operating system's built-in libraries.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="83a26-130">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="83a26-130">Version introduced</span></span>

<span data-ttu-id="83a26-131">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="83a26-131">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="83a26-132">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="83a26-132">Recommended action</span></span>

<span data-ttu-id="83a26-133">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="83a26-133">No action is required on the part of the developer.</span></span> <span data-ttu-id="83a26-134">Sin embargo, si desea seguir usando las API de globalización de NLS, puede establecer un [modificador en tiempo de ejecución](../../../run-time-config/globalization.md#nls) para revertir a ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="83a26-134">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="83a26-135">Para más información sobre los modificadores disponibles, consulte el artículo [Globalización .NET e ICU](../../../../standard/globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="83a26-135">For more information about the available switches, see the [.NET globalization and ICU](../../../../standard/globalization-localization/globalization-icu.md) article.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="83a26-136">API afectadas</span><span class="sxs-lookup"><span data-stu-id="83a26-136">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="83a26-137">La mayoría de tipos del espacio de nombres <xref:System.Globalization?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="83a26-137">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>
- <span data-ttu-id="83a26-138"><xref:System.Array.Sort%2A?displayProperty=fullName> (al ordenar una matriz de cadenas)</span><span class="sxs-lookup"><span data-stu-id="83a26-138"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting an array of strings)</span></span>
- <span data-ttu-id="83a26-139"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (cuando los elementos de lista son cadenas)</span><span class="sxs-lookup"><span data-stu-id="83a26-139"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="83a26-140"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (cuando las claves son cadenas)</span><span class="sxs-lookup"><span data-stu-id="83a26-140"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="83a26-141"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (cuando las claves son cadenas)</span><span class="sxs-lookup"><span data-stu-id="83a26-141"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="83a26-142"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (cuando el conjunto contiene cadenas)</span><span class="sxs-lookup"><span data-stu-id="83a26-142"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

<!--

### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

### Category

- Core .NET libraries
- Globalization

-->
