---
title: 'Cambio importante: Cambio de TargetFramework de netcoreapp a net'
description: Obtenga información sobre el cambio importante en .NET 5 por el que el valor de la propiedad TargetFramework de MSBuild ha cambiado de netcoreapp3.1 a net5.0.
ms.date: 10/17/2020
ms.openlocfilehash: 88bfe7602c83f61b56f11c4e0336702571369e3c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256496"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a>Cambio de TargetFramework de netcoreapp a net

El valor de la propiedad `TargetFramework` de MSBuild ha cambiado de `netcoreapp3.1` a `net5.0`. Esto puede interrumpir el código que se basa en el análisis del valor de `TargetFramework`.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En .NET Core 1.0-3.1, el valor de la propiedad `TargetFramework` de MSBuild comienza con `netcoreapp`, por ejemplo, `netcoreapp3.1` para las aplicaciones destinadas a .NET Core 3.1. A partir de .NET 5, este valor se ha simplificado para que solo empiece por `net`, por ejemplo, `net5.0` para .NET 5.0.

Para obtener más información, vea [El futuro de .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) y [Nombres de plataforma de destino en .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).

## <a name="reason-for-change"></a>Motivo del cambio

- Simplifica el valor de `TargetFramework`.
- Permite a los proyectos incluir un objeto `TargetPlatform` en la propiedad `TargetFramework`.

## <a name="recommended-action"></a>Acción recomendada

Si tiene lógica que analiza el valor de `TargetFramework`, tendrá que actualizarla. Por ejemplo, la siguiente condición de MSBuild se basa en el valor de `TargetFramework`.

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

Para este requisito, puede actualizar el código a fin de comparar el identificador de la plataforma de destino.

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a>API afectadas

N/D

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
