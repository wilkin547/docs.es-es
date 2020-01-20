---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901636"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel: se han quitado los adaptadores de conexión

Como parte de la migración de las API de "pubternal" a `public`, se ha quitado de Kestrel el concepto de un elemento `IConnectionAdapter`. Los adaptadores de conexión se han reemplazado por el middleware de conexión, que es similar al middleware HTTP en la canalización de ASP.NET Core, pero para conexiones de nivel inferior. HTTPS y el registro de conexiones se han movido de los adaptadores de conexión al middleware de conexión. Estos métodos de extensión deberían seguir funcionando sin problemas, pero los detalles de implementación han cambiado.

Para obtener más información, vea [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412). Para obtener información, vea [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Los componentes de extensibilidad de Kestrel se creaban mediante el uso de `IConnectionAdapter`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los componentes de extensibilidad de Kestrel se crean como [middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio está pensado para proporcionar una arquitectura de extensibilidad más flexible.

#### <a name="recommended-action"></a>Acción recomendada

Convierta las implementaciones de `IConnectionAdapter` para usar el nuevo patrón de middleware, tal como se muestra [aquí](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
