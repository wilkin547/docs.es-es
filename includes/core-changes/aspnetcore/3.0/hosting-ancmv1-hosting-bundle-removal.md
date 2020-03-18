---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901937"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Hospedaje: AspNetCoreModule V1 se ha quitado del conjunto de hospedaje de Windows

A partir de ASP.NET Core 3.0, el conjunto de hospedaje de Windows no incluirá AspNetCoreModule (ANCM) V1.

ANCM V2 es compatible con las versiones anteriores de ANCM OutOfProcess y se recomienda para su uso con aplicaciones de ASP.NET Core 3.0.

Para obtener información, vea [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

ANCM V1 está incluido en el conjunto de hospedaje de Windows.

#### <a name="new-behavior"></a>Comportamiento nuevo

ANCM V1 no está incluido en el conjunto de hospedaje de Windows.

#### <a name="reason-for-change"></a>Motivo del cambio

ANCM V2 es compatible con las versiones anteriores de ANCM OutOfProcess y se recomienda para su uso con aplicaciones de ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Acción recomendada

Use ANCM V2 con aplicaciones de ASP.NET Core 3.0.

Si se requiere ANCM V1, se puede instalar mediante el conjunto de hospedaje de Windows ASP.NET Core 2.1 o 2.2.

Este cambio interrumpirá las aplicaciones de ASP.NET Core 3.0 que:

- Participen del uso de ANCM V1 con `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.
- Tengan un archivo *web.config* personalizado con `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
