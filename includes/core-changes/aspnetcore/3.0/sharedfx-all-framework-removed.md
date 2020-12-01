---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032863"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a>Marco compartido: se ha eliminado Microsoft.AspNetCore.All

A partir de ASP.NET Core 3.0, ya no se generan el metapaquete `Microsoft.AspNetCore.All` y el marco compartido `Microsoft.AspNetCore.All` correspondiente. Este paquete está disponible en ASP.NET Core 2.2 y seguirá recibiendo actualizaciones de mantenimiento en ASP.NET Core 2.1.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las aplicaciones podían usar el metapaquete `Microsoft.AspNetCore.All` para seleccionar como destino el marco compartido `Microsoft.AspNetCore.All` en .NET Core.

#### <a name="new-behavior"></a>Comportamiento nuevo

En .NET Core 3.0 no se incluye un marco compartido `Microsoft.AspNetCore.All`.

#### <a name="reason-for-change"></a>Motivo del cambio

En el metapaquete `Microsoft.AspNetCore.All` se incluía un gran número de dependencias externas.

#### <a name="recommended-action"></a>Acción recomendada

Migre el proyecto para usar el marco `Microsoft.AspNetCore.App`. Los componentes que anteriormente estaban disponibles en `Microsoft.AspNetCore.All` lo siguen estando en NuGet. Ahora esos componentes se implementan con la aplicación en lugar de incluirse en el marco compartido.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
