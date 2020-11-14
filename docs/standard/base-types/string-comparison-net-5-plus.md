---
title: Cambios de comportamiento al comparar cadenas en .NET 5 +
description: Obtenga información sobre los cambios de comportamiento en la comparación de cadenas en .NET 5 y versiones posteriores en Windows.
ms.date: 11/04/2020
ms.openlocfilehash: 49be2169bb165b8fe0205800415542bea7bf9787
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403499"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a>Cambios de comportamiento al comparar cadenas en .NET 5 +

.NET 5.0 presenta un cambio de comportamiento en el entorno de ejecución por el que las API de globalización [ahora usan ICU de forma predeterminada](../../core/compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows) en todas las plataformas admitidas. Esto representa una divergencia respecto a versiones anteriores de .NET Core y .NET Framework, que usan la funcionalidad de compatibilidad con el idioma nacional (NLS) del sistema operativo cuando se ejecutan en Windows. Para obtener más información sobre estos cambios, incluidos los modificadores de compatibilidad que pueden revertir el cambio de comportamiento, vea [Globalización de .NET y ICU](../globalization-localization/globalization-icu.md).

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio se presentó para unificar el comportamiento de globalización de .NET en todos los sistemas operativos compatibles. También ofrece la posibilidad de que las aplicaciones agrupen sus propias bibliotecas de globalización en lugar de depender de las bibliotecas integradas del sistema operativo. Para obtener más información, vea [la notificación de cambio importante](../../core/compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).

## <a name="behavioral-differences"></a>Diferencias de comportamiento

Si usa funciones como `string.IndexOf(string)` sin llamar a la sobrecarga que toma un argumento <xref:System.StringComparison>, es posible que tenga la intención de realizar una búsqueda *ordinal* , pero en su lugar, toma involuntariamente una dependencia del comportamiento específico de la cultura. Dado que NLS y ICU implementan una lógica diferente en sus comparadores lingüísticos, los resultados de métodos como `string.IndexOf(string)` pueden devolver valores inesperados.

Esto puede manifestarse incluso en lugares donde no siempre se espera que las instalaciones de globalización estén activas. Por ejemplo, el código siguiente puede generar una respuesta diferente en función del entorno de ejecución actual.

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

## <a name="guard-against-unexpected-behavior"></a>Protección frente a un comportamiento inesperado

En esta sección se proporcionan dos opciones para tratar los cambios de comportamiento inesperados en .NET 5.0.

### <a name="enable-code-analyzers"></a>Habilitación de analizadores de código

Los [analizadores de código](../../fundamentals/code-analysis/overview.md) pueden detectar sitios de llamada posiblemente erróneos. Para protegerse contra cualquier comportamiento sorprendente, se recomienda instalar [el paquete NuGet __Microsoft. CodeAnalysis. FxCopAnalyzers__](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) en el proyecto. Este paquete incluye las reglas de análisis de código [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md) y [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md), que ayudan a marcar el código que podría estar utilizando un comparador lingüístico involuntariamente cuando estuviera previsto un comparador ordinal.

Por ejemplo:

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1307.
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

Del mismo modo, al crear una instancia de una colección ordenada de cadenas u ordenar una colección basada en cadenas existente, especifique un comparador explícito.

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

Para obtener más información sobre estas reglas del analizador de código, incluido cuándo podría ser adecuado suprimir estas reglas en su propia base de código, consulte los siguientes artículos:

* [CA1307: Especificar StringComparison para mayor claridad](../../fundamentals/code-analysis/quality-rules/ca1307.md)
* [CA1309: Utilizar StringComparison ordinal](../../fundamentals/code-analysis/quality-rules/ca1309.md)

### <a name="revert-back-to-nls-behaviors"></a>Reversión a los comportamientos de NLS

Para revertir las aplicaciones de .NET 5 a los comportamientos de NLS anteriores cuando se ejecutan en Windows, siga los pasos descritos en [Globalización de .NET e ICU](../globalization-localization/globalization-icu.md). Este modificador de compatibilidad para toda la aplicación debe establecerse en el nivel de aplicación. Las bibliotecas individuales no pueden aceptar este comportamiento ni excluirse de él.

> [!TIP]
> Le recomendamos encarecidamente que habilite las reglas de análisis de código [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md) y [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) para ayudar a mejorar la higiene del código y detectar los errores latentes existentes. Para obtener más información, vea [Habilitación de analizadores de código](#enable-code-analyzers).

## <a name="affected-apis"></a>API afectadas

La mayoría de las aplicaciones de .NET no encontrará ningún comportamiento inesperado provocado por los cambios en .NET 5.0. Sin embargo, debido al número de API afectadas y el grado en que estas API son fundamentales para el ecosistema de .NET más amplio, debe ser consciente del potencial de .NET 5.0 para introducir comportamientos no deseados o exponer errores latentes que ya existen en la aplicación.

Entre las API afectadas están las siguientes:

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <xref:System.Globalization.TextInfo?displayProperty=fullName> (la mayoría de los miembros)
- <xref:System.Globalization.CompareInfo?displayProperty=fullName> (la mayoría de los miembros)
- <xref:System.Array.Sort%2A?displayProperty=fullName> (al ordenar matrices de cadenas)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (cuando los elementos de lista son cadenas)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (cuando las claves son cadenas)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (cuando las claves son cadenas)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (cuando el conjunto contiene cadenas)

> [!NOTE]
> Esta no es una lista exhaustiva de las API afectadas.

Todas las API anteriores usan la búsqueda y comparación de cadenas *lingüística* con la [referencia cultural actual](xref:System.Threading.Thread.CurrentCulture) del subproceso, de forma predeterminada. Las diferencias entre la búsqueda y comparación *lingüística* y *ordinal* se mencionan en [Diferencias entre la búsqueda y comparación lingüística y ordinal](#ordinal-vs-linguistic-search-and-comparison).

Dado que ICU implementa comparaciones de cadenas lingüísticas de forma diferente a NLS, las aplicaciones basadas en Windows que se actualizan a .NET 5.0 desde una versión anterior de .NET Core o .NET Framework y que llaman a una de las API afectadas pueden observar que las API comienzan a presentar comportamientos diferentes.

### <a name="exceptions"></a>Excepciones

* Si una API acepta un parámetro explícito `StringComparison` o `CultureInfo`, ese parámetro invalida el comportamiento predeterminado de la API.
* Los miembros de `System.String` donde el primer parámetro es de tipo `char` (por ejemplo, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>) usan la búsqueda ordinal, a menos que el que llama pase un argumento `StringComparison` explícito que especifique `CurrentCulture[IgnoreCase]` o `InvariantCulture[IgnoreCase]`.

Para obtener un análisis más detallado del comportamiento predeterminado de cada API de <xref:System.String>, vea la sección [Tipos de comparación y búsqueda predeterminados](#default-search-and-comparison-types).

## <a name="ordinal-vs-linguistic-search-and-comparison"></a>Diferencias entre la búsqueda y comparación lingüística y ordinal

La búsqueda y comparación *ordinal* (también conocida como *no lingüística* ) descompone una cadena en sus elementos `char` individuales y realiza una búsqueda o comparación carácter por carácter. Por ejemplo, las cadenas `"dog"` y `"dog"` se comparan como *iguales* en un comparador de `Ordinal`, ya que las dos cadenas están compuestas de la misma secuencia de caracteres. Sin embargo, `"dog"` y `"Dog"` se comparan como *no iguales* en un comparador de `Ordinal`, porque no se componen de la misma secuencia de caracteres. Es decir, el punto de código de `'D'` en mayúsculas `U+0044` aparece antes del punto de código de `'d'` en minúsculas `U+0064`, lo que resulta en una clasificación `"dog"` antes de `"Dog"`.

Un comparador de `OrdinalIgnoreCase` sigue funcionando carácter por carácter, pero elimina las diferencias entre mayúsculas y minúsculas mientras se realiza la operación. En un comparador de `OrdinalIgnoreCase`, los pares de caracteres `'d'` y `'D'` se comparan como *iguales* , al igual que los pares de caracteres `'á'` y `'Á'`. Pero el carácter sin acento `'a'` se compara como *no igual* al carácter acentuado `'á'`.

En la tabla siguiente se proporcionan algunos ejemplos:

| cadena 1 | Cadena 2 | Comparación `Ordinal` | Comparación `OrdinalIgnoreCase` |
|---|---|---|---|
| `"dog"` | `"dog"` | equal | equal |
| `"dog"` | `"Dog"` | no igual | equal |
| `"resume"` | `"Resume"` | no igual | equal |
| `"resume"` | `"résumé"` | no igual | no igual |

Unicode también permite que las cadenas tengan varias representaciones en memoria diferentes. Por ejemplo, una e aguda (é) se puede representar de dos formas posibles:

* Un solo carácter `'é'` literal (también escrito como `'\u00E9'`).
* Un carácter `'e'` literal sin acento, seguido de un carácter modificador de acento de combinación `'\u0301'`.

Esto significa que las siguientes _cuatro_ cadenas dan como resultado `"résumé"` cuando se muestran, aunque sus piezas constituyentes son diferentes. Las cadenas usan una combinación de caracteres `'é'` literales o caracteres `'e'` literales no acentuados más el modificador de acento de combinación `'\u0301'`.

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

En un comparador ordinal, ninguna de estas cadenas resulta igual en la comparación con otra. Esto se debe a que todas contienen secuencias de caracteres subyacentes diferentes, aunque cuando se representan en la pantalla, todas tienen el mismo aspecto.

Al realizar una operación de `string.IndexOf(..., StringComparison.Ordinal)`, el tiempo de ejecución busca una coincidencia de subcadena exacta. Los resultados son los siguientes.

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

Las rutinas de búsqueda y comparación ordinales nunca se ven afectadas por la configuración de referencia cultural del subproceso actual.

Las rutinas de búsqueda y comparación *lingüísticas* descomponen una cadena en *elementos de intercalación* y realizan búsquedas o comparaciones en estos elementos. No hay necesariamente una asignación de 1:1 entre los caracteres de una cadena y sus elementos de intercalación constituyentes. Por ejemplo, una cadena de longitud 2 puede constar de un solo elemento de intercalación. Cuando se comparan dos cadenas en modo lingüístico, el comparador comprueba si los elementos de intercalación de las dos cadenas tienen el mismo significado semántico, incluso si los caracteres literales de la cadena son diferentes.

Considere de nuevo la cadena `"résumé"` y sus cuatro representaciones diferentes. En la tabla siguiente se muestra cada representación dividida en sus elementos de intercalación.

| String | Como elementos de intercalación |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

Un elemento de intercalación se corresponde de forma flexible con lo que los lectores considerarían un solo carácter o un clúster de caracteres. Es conceptualmente similar a un [grupo de grafemas](character-encoding-introduction.md#grapheme-clusters) pero engloba un paraguas algo más grande.

En un comparador lingüístico, no es necesario realizar coincidencias exactas. En su lugar, los elementos de intercalación se comparan en función de su significado semántico. Por ejemplo, un comparador trata las subcadenas `"\u00E9"` y `"e\u0301"` como iguales, ya que ambas significan semánticamente "una e minúscula con un modificador de acento agudo". Esto permite que el método `IndexOf` coincida con la subcadena `"e\u0301"` dentro de una cadena más grande que contiene la subcadena semánticamente equivalente `"\u00E9"`, tal y como se muestra en el ejemplo de código siguiente.

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

Como consecuencia de esto, dos cadenas de longitudes diferentes pueden compararse como iguales si se utiliza una comparación lingüística. Los que llaman deben tener cuidado de no utilizar la lógica de casos especiales que se ocupa de la longitud de la cadena en tales escenarios.

Las rutinas de búsqueda y comparación *que tienen en cuenta la referencia cultural* son una forma especial de las rutinas de comparación y búsqueda lingüísticas. En un comparador que tiene en cuenta la referencia cultural, el concepto de elemento de intercalación se amplía para incluir información específica de la referencia cultural especificada.

Por ejemplo, [en el alfabeto húngaro](https://en.wikipedia.org/wiki/Hungarian_alphabet), cuando los dos caracteres \<dz\> aparecen uno junto al otro, se consideran una letra única distinta de \<d\> o \<z\>. Esto significa que cuando se ve \<dz\> en una cadena, un comparador que conozca la cultura húngara lo trata como un único elemento de intercalación.

| String | Como elementos de intercalación | Comentarios |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | (mediante un comparador lingüístico estándar) |
| `"endz"` | `"e" + "n" + "dz"` | (mediante un comparador consciente de la referencia cultural húngara) |

Cuando se usa un comparador compatible con referencias culturales húngaras, que la cadena `"endz"` *no* termina con la subcadena `"z"`, ya que <\dz\> y <\z\> se consideran elementos de intercalación con un significado semántico diferente.

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
> - Comportamiento: Los comparadores lingüísticos y conocedores de las referencias culturales pueden someterse a ajustes de comportamiento de vez en cuando. Tanto ICU como la antigua instalación de Windows NLS se han actualizado para tener en cuenta cómo cambian los idiomas del mundo. Para obtener más información, consulte la entrada de blog [Actividad de datos de la configuración regional (cultura)](/archive/blogs/shawnste/locale-culture-data-churn). El comportamiento del comparador *ordinal* nunca cambiará, ya que realiza una búsqueda y comparación bit a bit exacta. Sin embargo, el comportamiento del comparador de *OrdinalIgnoreCase* puede cambiar a medida que Unicode crece para abarcar más conjuntos de caracteres y corrige las omisiones en los datos de mayúsculas y minúsculas existentes.
> - Uso: Los comparadores `StringComparison.InvariantCulture` y `StringComparison.InvariantCultureIgnoreCase` son comparadores lingüísticos que no tienen en cuenta la referencia cultural. Es decir, estos comparadores entienden conceptos como el carácter acentuado é que tiene varias representaciones subyacentes posibles y que todas esas representaciones deben tratarse igual. Sin embargo, los comparadores lingüísticos que no tienen en cuenta la referencia cultural no contendrán un tratamiento especial para \<dz\> como si fuera distinto de \<d\> o \<z\>, como se mostró anteriormente. Tampoco se trata de caracteres especiales como el alemán Eszett (ß).

.NET también ofrece el *modo de globalización invariable*. Este modo de inclusión deshabilita las rutas de acceso al código que se ocupan de las rutinas de comparación y búsqueda lingüística. En este modo, todas las operaciones utilizan comportamientos *Ordinal* o *OrdinalIgnoreCase* , independientemente del argumento `CultureInfo` o `StringComparison` que proporcione el autor de la llamada. Para obtener más información, vea [Opciones de configuración del entorno de ejecución para globalización](../../core/run-time-config/globalization.md) y [Modo invariable de globalización de .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

Para obtener más información, consulte [Procedimientos recomendados para la comparación de cadenas en .NET](best-practices-strings.md).

## <a name="security-implications"></a>Implicaciones de seguridad

Si la aplicación usa una API afectada para filtrar, se recomienda habilitar las reglas de análisis de código CA1307 y CA1309 para ayudar a ubicar los lugares en los que se puede haber usado una búsqueda lingüística involuntariamente en lugar de una búsqueda ordinal. Los patrones de código como los siguientes pueden ser susceptibles a vulnerabilidades de seguridad.

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

Dado que el método `string.IndexOf(string)` utiliza una búsqueda lingüística de forma predeterminada, es posible que una cadena contenga un carácter `'<'` o `'&'` literal y que la rutina `string.IndexOf(string)` devuelva `-1`, lo que indica que no se encontró la subcadena de búsqueda. Las reglas de análisis de código CA1307 y CA1309 marcan estos sitios de llamada y alertan al desarrollador de que hay un posible problema.

## <a name="default-search-and-comparison-types"></a>Tipos de comparación y búsqueda predeterminados

En la tabla siguiente se enumeran los tipos de comparación y búsqueda predeterminados para varias API de cadena y con aspecto de cadena. Si el autor de la llamada proporciona un parámetro `CultureInfo` o `StringComparison` explícito, ese parámetro se respetará con cualquier valor predeterminado.

| API | Comportamiento predeterminado | Comentarios |
|---|---|---|
| `string.Compare` | CurrentCulture | |
| `string.CompareTo` | CurrentCulture | |
| `string.Contains` | Ordinal | |
| `string.EndsWith` | Ordinal | (cuando el primer parámetro es `char`) |
| `string.EndsWith` | CurrentCulture | (cuando el primer parámetro es `string`) |
| `string.Equals` | Ordinal | |
| `string.GetHashCode` | Ordinal | |
| `string.IndexOf` | Ordinal | (cuando el primer parámetro es `char`) |
| `string.IndexOf` | CurrentCulture | (cuando el primer parámetro es `string`) |
| `string.IndexOfAny` | Ordinal | |
| `string.LastIndexOf` | Ordinal | (cuando el primer parámetro es `char`) |
| `string.LastIndexOf` | CurrentCulture | (cuando el primer parámetro es `string`) |
| `string.LastIndexOfAny` | Ordinal | |
| `string.Replace` | Ordinal | |
| `string.Split` | Ordinal | |
| `string.StartsWith` | Ordinal | (cuando el primer parámetro es `char`) |
| `string.StartsWith` | CurrentCulture | (cuando el primer parámetro es `string`) |
| `string.ToLower` | CurrentCulture | |
| `string.ToLowerInvariant` | InvariantCulture | |
| `string.ToUpper` | CurrentCulture | |
| `string.ToUpperInvariant` | InvariantCulture | |
| `string.Trim` | Ordinal | |
| `string.TrimEnd` | Ordinal | |
| `string.TrimStart` | Ordinal | |
| `string == string` | Ordinal | |
| `string != string` | Ordinal | |

A diferencia de las API de `string`, todas las API de `MemoryExtensions` realizan búsquedas y comparaciones *ordinales* de forma predeterminada, con las siguientes excepciones.

| API | Comportamiento predeterminado | Comentarios |
|---|---|---|
| `MemoryExtensions.ToLower` | CurrentCulture | (cuando se pasa un argumento `CultureInfo` nulo) |
| `MemoryExtensions.ToLowerInvariant` | InvariantCulture | |
| `MemoryExtensions.ToUpper` | CurrentCulture | (cuando se pasa un argumento `CultureInfo` nulo) |
| `MemoryExtensions.ToUpperInvariant` | InvariantCulture | |

Una consecuencia es que al convertir el código de consumir `string` a consumir `ReadOnlySpan<char>`, pueden introducirse cambios de comportamiento involuntariamente. A continuación se muestra un ejemplo de ello.

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

La manera recomendada de solucionarlo es pasar un parámetro `StringComparison` explícito a estas API. Las reglas de análisis de código CA1307 y CA1309 pueden ayudarle.

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a>Vea también

- [Cambios importantes de la globalización](../../core/compatibility/globalization.md)
- [Procedimientos recomendados para la comparación de cadenas en .NET](best-practices-strings.md)
- [Comparación de cadenas en C#](../../csharp/how-to/compare-strings.md)
- [Globalización de .NET e ICU](../globalization-localization/globalization-icu.md)
- [Operaciones de cadena que tienen en cuenta la referencia cultural frente a las ordinales](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [Información general sobre el análisis de código fuente de .NET](../../fundamentals/code-analysis/overview.md)
