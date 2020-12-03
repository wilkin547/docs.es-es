---
title: 'Cambio importante: Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760163"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: Migración de la característica ProtectedBrowserStorage a una plataforma compartida

Como parte de la versión ASP.NET Core 5.0 RC2, la característica `ProtectedBrowserStorage` ha migrado a la plataforma compartida de ASP.NET Core.

## <a name="version-introduced"></a>Versión introducida

5.0 RC2

## <a name="old-behavior"></a>Comportamiento anterior

En la versión preliminar 8 de ASP.NET Core 5.0, la característica está disponible como parte del paquete [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions), pero solo se puede usar en Blazor WebAssembly.

En ASP.NET Core 5.0 RC1, la característica está disponible como parte del paquete [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage), que hace referencia a la plataforma compartida de `Microsoft.AspNetCore.App`.

## <a name="new-behavior"></a>Comportamiento nuevo

En ASP.NET Core 5.0 RC2, ya no se necesita una referencia de paquete NuGet para hacer referencia a la característica y usarla.

## <a name="reason-for-change"></a>Motivo del cambio

La migración a la plataforma compartida es más adecuada para la experiencia de usuario que esperan los clientes.

## <a name="recommended-action"></a>Acción recomendada

Si va a realizar la actualización desde ASP.NET Core 5.0 RC1, complete estos pasos:

1. Quite la referencia al paquete `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` del proyecto.
1. Reemplace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. Quite la llamada a `AddProtectedBrowserStorage` de la clase `Startup`.

Si va a actualizar desde la versión preliminar 8 de ASP.NET Core 5.0, complete estos pasos:

1. Quite la referencia al paquete `Microsoft.AspNetCore.Components.Web.Extensions` del proyecto.
1. Reemplace `using Microsoft.AspNetCore.Components.Web.Extensions;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. Quite la llamada a `AddProtectedBrowserStorage` de la clase `Startup`.

## <a name="affected-apis"></a>API afectadas

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
