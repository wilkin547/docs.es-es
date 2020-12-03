---
title: 'Cambio importante: Constructores no públicos sin parámetros que no se usan para la deserialización'
description: Obtenga información sobre el cambio importante en .NET 5.0 por el que los constructores no públicos y sin parámetros ya no se usan para la deserialización con JsonSerializer.
ms.date: 10/18/2020
ms.openlocfilehash: 6bdcc92c61008aa4ee27370bbac4dbf4ee3ef7c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760248"
---
# <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a>Constructores no públicos sin parámetros que no se usan para la deserialización

Para mantener la coherencia entre todos los monikers de la plataforma de destino (TFM) admitidos, de forma predeterminada ya no se usan para la deserialización con <xref:System.Text.Json.JsonSerializer> los constructores no públicos y sin parámetros.

## <a name="change-description"></a>Descripción del cambio

Los [paquetes NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json/) independientes que admiten .NET Standard 2.0 y versiones posteriores, es decir, las versiones 4.6.0-4.7.2, se comportan de manera incoherente con el comportamiento integrado en .NET Core 3.0 y 3.1. En .NET Core 3.x, se pueden usar constructores internos y privados para la deserialización. En los paquetes independientes, no se permiten constructores no públicos y se inicia una excepción <xref:System.MissingMethodException> si no se define ningún constructor público sin parámetros.

A partir de .NET 5.0 y del paquete NuGet System.Text.Json 5.0.0, el comportamiento es coherente entre el paquete NuGet y las API integradas. El serializador omite de forma predeterminada los constructores no públicos, incluidos los que no tienen parámetros. El serializador usa uno de los constructores siguientes para la deserialización:

- Constructor público anotado con <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.
- Constructor público sin parámetros.
- Constructor público con parámetros (si es el único constructor público presente).

Si ninguno de estos constructores está disponible, se inicia una excepción <xref:System.NotSupportedException> si intenta deserializar el tipo.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="reason-for-change"></a>Motivo del cambio

- Aplicar un comportamiento coherente entre todos los monikers de la plataforma de destino (TFM) para los que se compila <xref:System.Text.Json?displayProperty=fullName> (.NET Core 3.0 y versiones posteriores, y .NET Standard 2.0)
- <xref:System.Text.Json.JsonSerializer> no debe llamar al área expuesta no pública de un tipo, ya sea un constructor, una propiedad o un campo.

## <a name="recommended-action"></a>Acción recomendada

- Si es el propietario del tipo y es factible, convierta en público el constructor sin parámetros.
- De lo contrario, implemente un elemento `JsonConverter<T>` para el tipo y controle el comportamiento de la deserialización.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
