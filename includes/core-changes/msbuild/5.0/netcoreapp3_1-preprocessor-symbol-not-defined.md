---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654748"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino

En .NET 5.0 RC2 y versiones posteriores, los proyectos ya no definen símbolos de preprocesador para versiones anteriores, sino solo la versión que tienen establecida como destino. Este comportamiento es el mismo que el de .NET Core 1.0 - 3.1.

#### <a name="version-introduced"></a>Versión introducida

5.0 RC2

#### <a name="change-description"></a>Descripción del cambio

En la versión preliminar 7 de .NET 5.0, hasta RC1, los proyectos que tienen `net5.0` como destino definen los dos símbolos de preprocesador `NETCOREAPP3_1` y `NET5_0`. La intención de aplicar este cambio de comportamiento era que, a partir de .NET 5.0, los [símbolos de compilación condicional fuesen acumulativos](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).

En .NET 5.0 RC2 y versiones posteriores, los proyectos solo definen símbolos para los monikers de la plataforma de destino (TFM) que tiene como destino y no para ninguna versión anterior.

#### <a name="reason-for-change"></a>Motivo del cambio

El cambio aplicado en la versión preliminar 7 se ha revertido debido a los comentarios de los clientes. La definición de símbolos para versiones anteriores sorprendía y confundía a los clientes, y algunos de ellos dedujeron que se trataba de un error del compilador de C#.

#### <a name="recommended-action"></a>Acción recomendada

Asegúrese de que la lógica de `#if` no deduce que se define `NETCOREAPP3_1` cuando el proyecto tiene como destino `net5.0` o una versión posterior. En su lugar, debe deducir que `NETCOREAPP3_1` solo se define cuando el proyecto tiene explícitamente establecido `netcoreapp3.1` como destino.

Por ejemplo, si su proyecto tiene establecidos varios destinos para .NET Core 2.1 y .NET Core 3.1, y usted llama a las API que se han introducido en .NET Core 3.1, la lógica de `#if` debe ser la siguiente:

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a>Categoría

MSBuild

#### <a name="affected-apis"></a>API afectadas

N/D

<!--

#### Affected APIs

Not detectable via API analysis.

-->
