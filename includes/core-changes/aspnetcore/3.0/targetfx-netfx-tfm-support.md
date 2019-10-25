---
ms.openlocfilehash: 4c676a185ff4a7a825acb059bf0a5842ca3922fc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393999"
---
### <a name="target-framework-net-framework-support-dropped"></a>Plataforma de destino: se ha quitado la compatibilidad con .NET Framework

A partir de ASP.NET Core 3.0, .NET Framework es un marco de destino que no se admite.

#### <a name="change-description"></a>Descripción del cambio

.NET Framework 4.8 es la última versión principal de .NET Framework. Las nuevas aplicaciones de ASP.NET Core se deben compilar en .NET Core. A partir de NET Core 3.0, puede considerar a ASP.NET Core 3.0 una parte de .NET Core.

Los clientes que usen ASP.NET Core con .NET Framework pueden continuar utilizando la [versión 2.1 LTS](https://www.microsoft.com/net/download/dotnet-core/2.1) de forma totalmente compatible. La compatibilidad y el servicio para la versión 2.1 continuarán hasta el 21 de agosto de 2021. Esta fecha es tres años posterior a la declaración de la versión LTS de acuerdo a la [Directiva de compatibilidad de .NET](https://www.microsoft.com/net/platform/support-policy). La compatibilidad con los paquetes de ASP.NET Core 2.1 **en .NET Framework** se extenderá indefinidamente, de forma similar a la [directiva de servicio para otros marcos de ASP.NET basados en paquetes](https://dotnet.microsoft.com/platform/support/policy/aspnet).

Para más información sobre cómo migrar de .NET Framework a .NET Core, vea [Portabilidad a .NET Core](~/docs/core/porting/index.md).

Los paquetes `Microsoft.Extensions` (como el registro, la inserción de dependencias y la configuración) y Entity Framework Core no se ven afectados. Seguirán admitiendo .NET Standard.

Para más información sobre la motivación de este cambio, vea [la entrada de blog original](https://blogs.msdn.microsoft.com/webdev/2018/10/29/a-first-look-at-changes-coming-in-asp-net-core-3-0).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las aplicaciones ASP.NET Core se podían ejecutar en .NET Core o .NET Framework.

#### <a name="new-behavior"></a>Comportamiento nuevo

Las aplicaciones ASP.NET Core solo se pueden ejecutar en .NET Core.

#### <a name="recommended-action"></a>Acción recomendada

Realice una de las siguientes acciones:

- Mantenga la aplicación en ASP.NET Core 2.1.
- Migre la aplicación y las dependencias a .NET Core.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
