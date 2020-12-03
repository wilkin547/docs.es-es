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
# <a name="globalization-apis-use-icu-libraries-on-windows"></a>Las API de globalización usan bibliotecas de ICU en Windows

.NET 5.0 y versiones posteriores usan bibliotecas de [componentes internacionales para Unicode (ICU)](http://site.icu-project.org/home) para la funcionalidad de globalización cuando se ejecutan en la actualización de mayo de 2019 de Windows 10 o versiones posteriores.

## <a name="change-description"></a>Descripción del cambio

En .NET Core 1.0 a 3.1 y .NET Framework 4 y versiones posteriores, las bibliotecas de .NET usan las API de [compatibilidad con el idioma nacional (NLS)](/windows/win32/intl/national-language-support) para la funcionalidad de globalización en Windows. Por ejemplo, las funciones de NLS se usaban para comparar cadenas, obtener información de referencia cultural y aplicar mayúsculas y minúsculas en las cadenas en la referencia cultural adecuada.

A partir de .NET 5.0, si una aplicación se ejecuta en la actualización de mayo de 2019 de Windows 10 o posterior, las bibliotecas de .NET usan las API de globalización de [ICU](http://site.icu-project.org/home) de manera predeterminada.

> [!NOTE]
> Las versiones de la actualización de mayo de 2019 de Windows 10 o posteriores incluyen la biblioteca nativa de ICU. Si el tiempo de ejecución de .NET no puede cargar ICU, utilizará NLS en su lugar.

## <a name="behavioral-differences"></a>Diferencias de comportamiento

Es posible que vea cambios en la aplicación aunque no se dé cuenta de que usa las instalaciones de globalización. En esta sección se enumeran algunos de los cambios de comportamiento que podría ver, pero también hay otros.

### <a name="stringindexof"></a>String.IndexOf

Considere el código siguiente que llama a <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> para buscar el índice del carácter de nueva línea en una cadena.

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- En versiones anteriores de .NET en Windows, el fragmento de código imprime `6`.
- En .NET 5.0 y versiones posteriores en Windows 19H1 y versiones posteriores, el fragmento de código imprime `-1`.

Para corregir este código mediante la realización de una búsqueda ordinal en lugar de una búsqueda según la referencia cultural, llame a la sobrecarga <xref:System.String.IndexOf(System.String,System.StringComparison)> y pase <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> como argumento.

Puede ejecutar las reglas de análisis de código [CA1307: Especificar StringComparison para mayor claridad](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) y [CA1309: Usar StringComparison ordinal](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) para buscar estos sitios de llamada en el código.

Para más información, consulte [Cambios de comportamiento al comparar cadenas en .NET 5 +](../../../../standard/base-types/string-comparison-net-5-plus.md).

### <a name="currency-symbol"></a>Símbolo de moneda

Considere el código siguiente que da formato a una cadena con el especificador de formato de divisa `C`. La referencia cultural del subproceso actual se establece en una referencia cultural que solo incluye el idioma, no el país.

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- En versiones anteriores de .NET en Windows, el valor del texto es `"100,00 €"`.
- En .NET 5.0 y versiones posteriores en Windows 19H1 y versiones posteriores, el valor del texto es `"100,00 ¤"`, que usa el símbolo de moneda internacional en lugar del euro. En ICU, el diseño es que una moneda es una propiedad de un país o región, no un idioma.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio se presentó para unificar el comportamiento de globalización de .NET en todos los sistemas operativos compatibles. También ofrece la posibilidad de que las aplicaciones agrupen sus propias bibliotecas de globalización en lugar de depender de las bibliotecas integradas del sistema operativo.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador. Sin embargo, si desea seguir usando las API de globalización de NLS, puede establecer un [modificador en tiempo de ejecución](../../../run-time-config/globalization.md#nls) para revertir a ese comportamiento. Para más información sobre los modificadores disponibles, consulte el artículo [Globalización .NET e ICU](../../../../standard/globalization-localization/globalization-icu.md).

## <a name="affected-apis"></a>API afectadas

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- La mayoría de tipos del espacio de nombres <xref:System.Globalization?displayProperty=fullName>
- <xref:System.Array.Sort%2A?displayProperty=fullName> (al ordenar una matriz de cadenas)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (cuando los elementos de lista son cadenas)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (cuando las claves son cadenas)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (cuando las claves son cadenas)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (cuando el conjunto contiene cadenas)

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
