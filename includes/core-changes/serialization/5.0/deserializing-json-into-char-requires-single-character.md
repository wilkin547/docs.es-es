---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844516"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a>JsonSerializer.Deserialize requiere una cadena de un solo carácter

Cuando el parámetro de tipo es <xref:System.Char>, el argumento de cadena para <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> debe contener un solo carácter para que la deserialización se realice correctamente.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, si se pasa una cadena de varios caracteres a <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> y el parámetro de tipo es <xref:System.Char>, la deserialización se realiza correctamente y solo se deserializa el primer carácter.

En .NET 5.0 y versiones posteriores, cuando el parámetro de tipo es <xref:System.Char>, si se pasa algo distinto a una cadena de un solo carácter, se inicia una excepción <xref:System.Text.Json.JsonException>.

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="reason-for-change"></a>Motivo del cambio

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analiza el texto que representa un único valor JSON en una instancia del tipo especificado por el parámetro de tipo genérico. El análisis solo se realiza correctamente si la carga proporcionada es válida para el parámetro de tipo genérico especificado. Para un tipo de valor <xref:System.Char>, una carga válida es una cadena de un solo carácter.

#### <a name="recommended-action"></a>Acción recomendada

Al analizar una cadena en un tipo <xref:System.Char> mediante <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, asegúrese de que la cadena consta de un solo carácter.

#### <a name="category"></a>Categoría

Serialización

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
