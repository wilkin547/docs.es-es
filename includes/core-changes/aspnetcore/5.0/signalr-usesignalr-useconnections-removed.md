---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291643"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>SignalR: los métodos UseSignalR y UseConnections se han quitado

En ASP.NET Core 3.0, SignalR adoptó el enrutamiento de puntos de conexión. Como parte de ese cambio, <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> y algunos métodos relacionados se marcaron como obsoletos. En ASP.NET Core 5.0, se quitaron los métodos obsoletos. Para ver la lista completa de métodos, consulte [API afectadas](#affected-apis).

Para obtener información sobre esta incidencia, consulte [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 3)

#### <a name="old-behavior"></a>Comportamiento anterior

Los controladores de conexión y concentradores de SignalR podrían registrarse en la canalización de software intermedio mediante los métodos `UseSignalR` o `UseConnections`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los controladores de conexión y concentradores de SignalR deben registrarse en <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> mediante los métodos de extensión <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> y <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> de <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.

#### <a name="reason-for-change"></a>Motivo del cambio

Los métodos anteriores tenían una lógica de enrutamiento personalizado que no interactuaba con otros componentes de enrutamiento en ASP.NET Core. En ASP.NET Core 3.0, se presentó un nuevo sistema de enrutamiento de uso general, llamado enrutamiento de puntos de conexión. El enrutamiento de puntos de conexión habilitó SignalR para interactuar con otros componentes de enrutamiento. Cambiar a este modelo permite a los usuarios comprender todos los beneficios del enrutamiento de puntos de conexión. Por consiguiente, se han quitado los métodos anteriores.

#### <a name="recommended-action"></a>Acción recomendada

Quite el código que llama a `UseSignalR` o `UseConnections` desde el método `Startup.Configure` del proyecto. Reemplácelo por llamadas a `MapHub` o `MapConnectionHandler`, respectivamente, en el cuerpo de una llamada a `UseEndpoints`. Por ejemplo:

**Código anterior:**

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

**Código nuevo:**

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

En general, sus llamadas `MapHub` y `MapConnectionHandler` anteriores pueden transferirse directamente desde el cuerpo de `UseSignalR` y `UseConnections` a `UseEndpoints` sin que sean necesarios muchos cambios (o ninguno).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
