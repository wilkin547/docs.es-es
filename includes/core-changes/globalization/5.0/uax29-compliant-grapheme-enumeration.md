---
ms.openlocfilehash: 70b71fc55f76514dd17e5b9ba0e76151a966eebb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539483"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a>StringInfo y TextElementEnumerator ahora son compatibles con UAX29

Antes de este cambio, <xref:System.Globalization.StringInfo?displayProperty=fullName> y <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> no trataban correctamente todos los clústeres de grafemas. Algunos grafemas se dividieron en sus componentes constituyentes en lugar de mantenerse juntos. Ahora, <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> procesan los clústeres de grafemas de acuerdo con la versión más reciente del estándar Unicode.

Además, el método <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>, que invierte los caracteres de una cadena en Visual Basic, ahora también sigue el estándar Unicode para los clústeres de grafemas.

#### <a name="change-description"></a>Descripción del cambio

Un [grafema](https://www.unicode.org/glossary/#grapheme) o [clúster de grafemas ampliado](https://www.unicode.org/glossary/#extended_grapheme_cluster) es un único carácter que percibe el usuario y que puede estar formado por varios puntos de código Unicode. Por ejemplo, la cadena que contiene el carácter tailandés "kam" (:::no-loc text="กำ":::) consta de los dos caracteres siguientes:

- :::no-loc text="ก"::: (= '\u0e01') CARÁCTER TAILANDÉS KO KAI
- :::no-loc text=" ำ"::: (= '\u0e33') CARÁCTER TAILANDÉS SARA AM

Cuando se muestra al usuario, el sistema operativo combina los dos caracteres para formar el único carácter de presentación (o grafema) "kam" o :::no-loc text="กำ":::. El emoji también puede constar de varios caracteres que se combinan para mostrarse de forma similar.

> [!TIP]
> En ocasiones, la documentación de .NET usa el término "elemento de texto" al hacer referencia a un grafema.

Las clases <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> inspeccionan las cadenas y devuelven información sobre los grafemas que contienen. En .NET Framework (todas las versiones) y .NET Core 3.x y versiones anteriores, estas dos clases usan una lógica personalizada que controla algunas clases de combinación, pero no cumple totalmente con el [estándar Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries). Por ejemplo, las clases <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> dividen incorrectamente el carácter tailandés "kam" de nuevo en sus componentes constituyentes en lugar de mantenerlos juntos. Estas clases también dividen incorrectamente el carácter "🤷🏽 ♀️" de emoji en cuatro clústeres (persona encogiéndose de hombros, modificador del tono de piel, modificador de género y un combinador invisible) en lugar de mantenerlos juntos como un único clúster de grafemas.

A partir de .NET 5, las clases <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> implementan el estándar Unicode, tal y como se define en el [anexo del estándar Unicode \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html). En concreto, ahora devuelven [clústeres de grafemas ampliados](https://www.unicode.org/glossary/#extended_grapheme_cluster) para todas las clases que se combinan.

Observe el código C# siguiente:

```csharp
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

En .NET Framework y .NET Core 3.x y versiones anteriores, los grafemas se dividen y el resultado de la consola es el siguiente:

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

En .NET 5 y versiones posteriores, los grafemas se mantienen juntos y el resultado de la consola es el siguiente:

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

Además, a partir de .NET 5, el método <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>, que invierte los caracteres de una cadena en Visual Basic, ahora también sigue el estándar Unicode para los clústeres de grafemas.

Estos cambios forman parte de un conjunto más amplio de mejoras de Unicode y UTF-8 en .NET, incluida una API de enumeración de clústeres extendidos de grafemas para complementar las API de enumeración de valores escalares de Unicode que se introdujeron con el tipo de <xref:System.Text.Rune?displayProperty=fullName> en .NET Core 3.0.

#### <a name="version-introduced"></a>Versión introducida

.NET 5.0 (versión preliminar 1)

#### <a name="recommended-action"></a>Acción recomendada

No tiene que realizar ninguna acción. Las aplicaciones se comportarán automáticamente de forma más conforme a los estándares en diversos escenarios relacionados con la globalización.

#### <a name="category"></a>Categoría

Globalización

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
