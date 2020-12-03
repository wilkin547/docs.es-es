---
title: 'Cambio importante: Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760101"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a>Blazor: Los campos públicos RenderTreeFrame de solo lectura se han convertido en propiedades

En ASP.NET Core 3.0 y 3.1, la estructura <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> expone varios campos de `readonly public`, como <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> y otros. En ASP.NET Core 5.0 RC1 y versiones posteriores, todos los campos de `readonly public` se han cambiado por propiedades `readonly public`.

Este cambio no afectará a muchos desarrolladores porque:

* Cualquier aplicación o biblioteca que simplemente use archivos `.razor` (o incluso llamadas a <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> manuales) para definir sus componentes no hará referencia directamente a este tipo.
* El propio tipo `RenderTreeFrame` se considera un detalle de implementación; no está diseñado para usarlo fuera del marco. En ASP.NET Core 3.0 y versiones posteriores se incluye un analizador que emite advertencias del compilador si el tipo se usa de forma directa.
* Incluso si hace referencia a `RenderTreeFrame` de forma directa, este cambio afectará a los binarios, no al código fuente. Es decir, el código fuente existente se compilará y se comportará de manera correcta. Solo se producirá una incidencia si se compila en un marco de trabajo de .NET Core 3.x y luego esos archivos binarios se ejecutan en .NET 5.0 RC1 y versiones posteriores.

Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).

## <a name="version-introduced"></a>Versión introducida

5.0 RC1

## <a name="old-behavior"></a>Comportamiento anterior

Los miembros públicos de `RenderTreeFrame` se definen como campos. Por ejemplo, `renderTreeFrame.Sequence` y `renderTreeFrame.ElementName`.

## <a name="new-behavior"></a>Comportamiento nuevo

Los miembros públicos de `RenderTreeFrame` se definen como propiedades con los mismos nombres que antes. Por ejemplo, `renderTreeFrame.Sequence` y `renderTreeFrame.ElementName`.

Si el código precompilado anterior no se ha vuelto a compilar desde este cambio, es posible que inicie una excepción similar a *MissingFieldException: Campo no encontrado: "Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType"* .

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio era necesario para implementar mejoras de rendimiento de alto impacto en la representación de componentes de Blazor en ASP.NET Core 5.0. Se mantienen los mismos niveles de seguridad y encapsulación.

## <a name="recommended-action"></a>Acción recomendada

A la mayoría de los desarrolladores de Blazor no les afectará este cambio. Es más probable que el cambio afecte a los creadores de bibliotecas y paquetes, pero solo en determinadas ocasiones. En concreto, si se desarrolla:

* Una aplicación y se usa ASP.NET Core 3.x o se actualiza a 5.0 RC1 o una versión posterior, no es necesario cambiar el código propio. Pero si depende de una biblioteca actualizada para tener en cuenta este cambio, tendrá que actualizar a una versión más reciente de esa biblioteca.
* Una biblioteca y solo quiere admitir ASP.NET Core 5.0 RC1 o posterior, no es necesario realizar ninguna acción. Solo tiene que asegurarse de que el archivo del proyecto declara un valor `<TargetFramework>` de `net5.0` o una versión posterior.
* Una biblioteca y quiere admitir ASP.NET Core 3.x *y* 5.0, determine si el código lee miembros de `RenderTreeFrame`. Por ejemplo, la evaluación de `someRenderTreeFrame.FrameType`.
  * La mayoría de las bibliotecas no leerán miembros `RenderTreeFrame`, incluidas las que contienen componentes de `.razor`. En este caso, no es necesario realizar ninguna acción.
  * Pero si la biblioteca lo hace, necesitará varios destinos para admitir `netstandard2.1` y `net5.0`. Aplique los cambios siguientes en el archivo del proyecto:
    * Reemplace el elemento `<TargetFramework>` existente por `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.
    * Use una referencia de paquete `Microsoft.AspNetCore.Components` condicional para tener en cuenta las dos versiones que quiera admitir. Por ejemplo:

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

Para una mayor aclaración, vea estas [diferencias en las que se muestra cómo @jsakamoto ya ha actualizado la biblioteca `Toolbelt.Blazor.HeadElement`](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
