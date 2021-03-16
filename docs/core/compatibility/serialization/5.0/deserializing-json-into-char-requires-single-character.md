---
title: 'Cambio importante: Deserialize char necesita una cadena de un solo carácter'
description: Obtenga información sobre el cambio importante en .NET 5, por el que System.Text.Json requiere una cadena de un solo elemento char en JSON al realizar una deserialización a un destino de un carácter.
ms.date: 12/15/2020
ms.openlocfilehash: e901f8ee7e7521af948a3bcde5cf969640436f7f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256340"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a>System.Text.Json requiere una cadena de un solo elemento char para deserializar a un elemento char

Para deserializar correctamente un elemento <xref:System.Char> mediante <xref:System.Text.Json>, la cadena JSON debe contener un solo carácter.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, una cadena de varios elementos `char` en JSON se deserializaba correctamente en una propiedad o campo `char`. Solo se usa el primer elemento `char` de la cadena, como en el ejemplo siguiente:

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

En .NET 5 y versiones posteriores, si se pasa algo distinto a una cadena de un solo elemento `char`, se inicia una excepción <xref:System.Text.Json.JsonException> cuando el parámetro de tipo es un elemento `char`. La siguiente cadena de ejemplo se deserializa correctamente en todas las versiones de .NET:

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="reason-for-change"></a>Motivo del cambio

El análisis para la deserialización solo se realiza correctamente si la carga proporcionada es válida para el tipo de destino. Para un tipo `char`, la única carga válida es una cadena de un solo elemento `char`.

## <a name="recommended-action"></a>Acción recomendada

Al deserializar JSON en un destino `char`, asegúrese de que la cadena se compone de un solo elemento `char`.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
