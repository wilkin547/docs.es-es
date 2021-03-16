---
title: 'Cambio importante: Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino'
description: Obtenga información sobre el cambio importante en .NET 5 por el que los proyectos ya no definen símbolos de preprocesador para versiones anteriores.
ms.date: 09/17/2020
ms.openlocfilehash: 390c8f5af97510db4652f3f42db577e6de158020
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256535"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino

En .NET 5 RC2 y versiones posteriores, los proyectos ya no definen símbolos de preprocesador para versiones anteriores, sino solo la versión que tienen establecida como destino. Este comportamiento es el mismo que el de .NET Core 1.0 - 3.1.

## <a name="version-introduced"></a>Versión introducida

5.0 RC2

## <a name="change-description"></a>Descripción del cambio

En la versión preliminar 7 de .NET 5, hasta RC1, los proyectos que tienen `net5.0` como destino definen los dos símbolos de preprocesador `NETCOREAPP3_1` y `NET5_0`. La intención de aplicar este cambio de comportamiento era que, a partir de .NET 5, los [símbolos de compilación condicional fuesen acumulativos](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).

En .NET 5 RC2 y versiones posteriores, los proyectos solo definen símbolos para los monikers de la plataforma de destino (TFM) que tiene como destino y no para ninguna versión anterior.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio aplicado en la versión preliminar 7 se ha revertido debido a los comentarios de los clientes. La definición de símbolos para versiones anteriores sorprendía y confundía a los clientes, y algunos de ellos dedujeron que se trataba de un error del compilador de C#.

## <a name="recommended-action"></a>Acción recomendada

Asegúrese de que la lógica de `#if` no deduce que se define `NETCOREAPP3_1` cuando el proyecto tiene como destino `net5.0` o una versión posterior. En su lugar, debe deducir que `NETCOREAPP3_1` solo se define cuando el proyecto tiene explícitamente establecido `netcoreapp3.1` como destino.

Por ejemplo, si su proyecto tiene establecidos varios destinos para .NET Core 2.1 y .NET Core 3.1, y usted llama a las API que se han introducido en .NET Core 3.1, la lógica de `#if` debe ser la siguiente:

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a>API afectadas

N/D

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
