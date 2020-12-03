---
title: 'Cambio importante: Blazor: Plataforma de destino de paquetes NuGet cambiada'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Plataforma de destino de paquetes NuGet cambiada'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 5515edc66ff9786f0d8f7e24e5fc28c71502567b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760164"
---
# <a name="blazor-target-framework-of-nuget-packages-changed"></a>Blazor: Plataforma de destino de paquetes NuGet cambiada

Los proyectos WebAssembly de Blazor 3.2 se han compilado para tener como destino .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`). En ASP.NET Core 5.0, los proyectos de Blazor Server y Blazor WebAssembly tienen como destino .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`). Para alinearse mejor con el cambio de la plataforma de destino, los siguientes paquetes de Blazor ya no tienen como destino .NET Standard 2.1:

* [Microsoft.AspNetCore.Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [Microsoft.AspNetCore.Components.Authorization](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [Microsoft.AspNetCore.Components.Forms](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [Microsoft.AspNetCore.Components.Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [Microsoft.AspNetCore.Components.WebAssembly](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [Microsoft.AspNetCore.Components.WebAssembly.Authentication](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [Microsoft.JSInterop](https://www.nuget.org/packages/Microsoft.JSInterop)
* [Microsoft.JSInterop.WebAssembly](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [Microsoft.Authentication.WebAssembly.Msal](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 7)

## <a name="old-behavior"></a>Comportamiento anterior

En Blazor 3.1 y 3.2, los paquetes tienen como destino .NET Standard 2.1 y .NET Core 3.1.

## <a name="new-behavior"></a>Comportamiento nuevo

En ASP.NET Core 5.0, los paquetes tienen como destino .NET 5.0.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio se ha realizado para una mejor alineación con los requisitos de plataforma de destino de .NET.

## <a name="recommended-action"></a>Acción recomendada

Los proyectos WebAssembly de Blazor 3.2 deben tener como destino .NET 5.0 como parte de la actualización de las referencias de paquete a 5.x.x. Las bibliotecas que hacen referencia a uno de estos paquetes pueden tener como destino .NET 5.0 o varios destinos, en función de sus requisitos.

## <a name="affected-apis"></a>API afectadas

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
