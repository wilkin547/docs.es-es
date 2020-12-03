---
title: 'Cambio importante: Mejora del control de cadenas de búsqueda vacías por parte de LastIndexOf'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde LastIndexOf y las API relacionadas ahora devuelven valores correctos al buscar una subcadena de longitud cero.
ms.date: 11/01/2020
ms.openlocfilehash: 6d1a676eb2b9ed3de6a745db27d53bd43560a32f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760113"
---
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a>Mejora del control de cadenas de búsqueda vacías por parte de LastIndexOf

<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> y las API relacionadas ahora devuelven valores correctos al buscar una subcadena de longitud cero (o equivalente a longitud cero) dentro de una cadena más grande.

## <a name="change-description"></a>Descripción del cambio

En .NET Framework y .NET Core 1.0-3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> y las API relacionadas podrían devolver un valor incorrecto cuando el autor de la llamada busca una subcadena de longitud cero.

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

A partir de .NET 5.0, estas API devuelven el valor correcto para `LastIndexOf`.

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

En estos ejemplos, `5` es la respuesta correcta porque `"Hello".Substring(5)` y `"Hello".AsSpan().Slice(5)` generan una cadena vacía, que es trivialmente igual que la subcadena vacía que se busca.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio formaba parte de un esfuerzo general de corrección de errores relacionados con el control de cadenas para .NET 5. También ayuda a unificar el comportamiento entre las plataformas Windows y las que no son de Windows. Para obtener más información, vea [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) y [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

No tiene que realizar ninguna acción. El entorno de ejecución de .NET 5.0 proporciona los nuevos comportamientos de forma automática.

No hay ningún modificador de compatibilidad para restaurar el comportamiento anterior.

## <a name="affected-apis"></a>API afectadas

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->
