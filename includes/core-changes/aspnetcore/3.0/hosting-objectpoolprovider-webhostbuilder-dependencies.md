---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393935"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder

Para aumentar la naturaleza de pago por uso de ASP.NET Core, se ha quitado `ObjectPoolProvider` del conjunto principal de dependencias. Ahora componentes específicos que dependen de `ObjectPoolProvider` lo agregan por sí mismos.

Para obtener información, vea [aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

`WebHostBuilder` proporciona `ObjectPoolProvider` de forma predeterminada en el contenedor de DI.

#### <a name="new-behavior"></a>Comportamiento nuevo

`WebHostBuilder` ya no proporciona `ObjectPoolProvider` de forma predeterminada en el contenedor de DI.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha realizado para aumentar la naturaleza de pago por uso de ASP.NET Core.

#### <a name="recommended-action"></a>Acción recomendada

Si el componente requiere `ObjectPoolProvider`, tendrá que agregarlo a las dependencias mediante `IServiceCollection`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
