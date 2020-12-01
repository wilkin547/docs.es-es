---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032757"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder

Para aumentar la naturaleza de pago por uso de ASP.NET Core, se ha quitado `ObjectPoolProvider` del conjunto principal de dependencias. Ahora componentes específicos que dependen de `ObjectPoolProvider` lo agregan por sí mismos.

Para obtener información, vea [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).

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
