---
ms.openlocfilehash: 49aa98edec8ed1ce35dd501c57aa82e4ca4cf286
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104879587"
---
### <a name="project-tools-now-included-in-sdk"></a>Herramientas de proyecto ahora incluidas en el SDK

El SDK de .NET Core 2.1 ahora incluye herramientas comunes de la CLI y ya no es necesario hacer referencia a estas herramientas desde el proyecto.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.0, los proyectos hacen referencia a herramientas de .NET externas con la opción de configuración `<DotNetCliToolReference>` del proyecto. En .NET Core 2.1, algunas de estas herramientas se incluyen en el SDK de .NET Core y esa configuración ya no es necesaria. Si incluye referencias a estas herramientas en el proyecto, recibirá un error parecido al siguiente: **La herramienta "Microsoft.EntityFrameworkCore.Tools.DotNet" se incluye ahora en el SDK de .NET Core**.

Herramientas ahora incluidas en el SDK de .NET Core 2.1:

| Valor de \<DotNetCliToolReference>                   | Herramienta                                                                                                            |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `Microsoft.DotNet.Watcher.Tools`               | `dotnet-watch`               |
| `Microsoft.Extensions.SecretManager.Tools`     | [dotnet-user-secrets](https://github.com/dotnet/aspnetcore/blob/main/src/Tools/dotnet-user-secrets/README.md) |
| `Microsoft.Extensions.Caching.SqlConfig.Tools` | [dotnet-sql-cache](https://github.com/dotnet/aspnetcore/blob/main/src/Tools/dotnet-sql-cache/README.md)       |
| `Microsoft.EntityFrameworkCore.Tools.DotNet`   | [dotnet-ef](/ef/core/miscellaneous/cli/dotnet)                                                                  |

#### <a name="version-introduced"></a>Versión introducida

SDK de .NET Core 2.1.300

#### <a name="recommended-action"></a>Acción recomendada

Quite la configuración `<DotNetCliToolReference>` del proyecto.

#### <a name="category"></a>Categoría

MSBuild

#### <a name="affected-apis"></a>API afectadas

N/D
