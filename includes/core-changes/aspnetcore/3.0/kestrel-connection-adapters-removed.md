---
ms.openlocfilehash: a916af91670dc9c5ceb2ff759cd8ae308fb2c2dc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394135"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel: se han quitado los adaptadores de conexión

Como parte de la migración de las API de "pubternal" a `public`, se ha quitado de Kestrel el concepto de un elemento `IConnectionAdapter`. Los adaptadores de conexión se han reemplazado por el middleware de conexión, que es similar al middleware HTTP en la canalización de ASP.NET Core, pero para conexiones de nivel inferior. HTTPS y el registro de conexiones se han movido de los adaptadores de conexión al middleware de conexión. Estos métodos de extensión deberían seguir funcionando sin problemas, pero los detalles de implementación han cambiado.

Para obtener más información, vea [aspnet/AspNetCore#11412](https://github.com/aspnet/AspNetCore/pull/11412). También puede consultar [aspnet/AspNetCore#11475](https://github.com/aspnet/AspNetCore/issues/11475).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Los componentes de extensibilidad de Kestrel se creaban mediante el uso de `IConnectionAdapter`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los componentes de extensibilidad de Kestrel se crean como [middleware](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio está pensado para proporcionar una arquitectura de extensibilidad más flexible.

#### <a name="recommended-action"></a>Acción recomendada

Convierta las implementaciones de `IConnectionAdapter` para usar el nuevo patrón de middleware, tal como se muestra [aquí](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
