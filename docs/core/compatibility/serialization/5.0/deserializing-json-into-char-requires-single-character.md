---
title: 'Cambio importante: Deserialize char necesita una cadena de un solo carácter'
description: Obtenga información sobre el cambio importante en .NET 5.0, por el que System.Text.Json requiere una cadena de un solo elemento char en JSON al realizar una deserialización a un destino de un carácter.
ms.date: 12/15/2020
ms.openlocfilehash: 39a2d25b00bf8855cfbf46a4d78b8545052703e5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633876"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a>System.Text.Json requiere una cadena de un solo elemento char para deserializar a un elemento char

Para deserializar correctamente un elemento <xref:System.Char> mediante <xref:System.Text.Json>, la cadena JSON debe contener un solo carácter.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, una cadena de varios elementos `char` en JSON se deserializaba correctamente en una propiedad o campo `char`. Solo se usa el primer elemento `char` de la cadena, como en el ejemplo siguiente:

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

En .NET 5.0 y versiones posteriores, si se pasa algo distinto a una cadena de un solo elemento `char`, se inicia una excepción <xref:System.Text.Json.JsonException> cuando el parámetro de tipo es un elemento `char`. La siguiente cadena de ejemplo se deserializa correctamente en todas las versiones de .NET:

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
