---
ms.openlocfilehash: 8c739d8f355ffa6a6e09cbe4c531b188acede5bd
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720313"
---
### <a name="osplatform-attributes-renamed-or-removed"></a>Atributos de OSPlatform que se han cambiado de nombre o se han quitado

Los atributos siguientes que se presentaron en .NET 5.0 Preview 8 se han quitado o se les ha cambiado el nombre: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute` y `ObsoletedInOSPlatformAttribute`.

#### <a name="change-description"></a>Descripción del cambio

En .NET 5.0 Preview 8 se han presentado los siguientes atributos en el espacio de nombres <xref:System.Runtime.Versioning>:

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

En .NET 5.0 Preview 8, cuando un proyecto tiene como destino un tipo específico del sistema operativo de .NET 5 mediante un [moniker de la plataforma de destino](../../../../docs/standard/frameworks.md) como `net5.0-windows`, la compilación agrega un atributo `System.Runtime.Versioning.MinimumOSPlatformAttribute` de nivel de ensamblado.

En .NET 5.0 RC1, se ha quitado `ObsoletedInOSPlatformAttribute`, y se ha cambiado el nombre de `MinimumOSPlatformAttribute` y `RemovedInOSPlatformAttribute` de la siguiente manera:

| Nombre en Preview 8 | Nombre en RC1 y versiones posteriores |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

En .NET 5.0 RC1 y versiones posteriores, cuando un proyecto tiene como destino un tipo específico del sistema operativo de .NET 5 mediante un [moniker de la plataforma de destino](../../../../docs/standard/frameworks.md) como `net5.0-windows`, la compilación agrega un atributo <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> de nivel de ensamblado.

#### <a name="reason-for-change"></a>Motivo del cambio

En .NET 5.0 Preview 8 se han presentado atributos en <xref:System.Runtime.Versioning> para especificar las plataformas admitidas para las API. Los atributos los consume el [analizador de compatibilidad de la plataforma](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) para generar advertencias de compilación cuando se consumen API específicas de la plataforma en plataformas que no admiten esas API.

Para .NET 5.0 RC1, se ha agregado una característica adicional al analizador de compatibilidad de la plataforma para la exclusión de plataformas. La característica permite que las API se marquen como totalmente no compatibles en plataformas de sistema operativo. Esta característica ha solicitado cambios en los atributos, incluido el uso de nombres más adecuados. Se ha quitado `ObsoletedInOSPlatformAttribute` porque ya no era necesario.

#### <a name="version-introduced"></a>Versión introducida

5.0 RC1

#### <a name="recommended-action"></a>Acción recomendada

Al redestinar el proyecto de .NET 5.0 Preview 8 a .NET 5.0 RC1, se pueden producir errores en tiempo de compilación o ejecución debido a estos cambios. Por ejemplo, es probable que el cambio de nombre de `MinimumOSPlatformAttribute` produzca errores, porque el atributo se aplica a ensamblados específicos de la plataforma en tiempo de compilación y los artefactos de compilación antiguos seguirán haciendo referencia al antiguo nombre de API.

Ejemplo de errores en tiempo de compilación:

- **Error CS0246: No se ha encontrado el tipo o el nombre del espacio de nombres "MinimumOSPlatformAttribute" (¿falta una directiva "using" o una referencia de ensamblado?)**
- **Error CS0246: No se ha encontrado el tipo o el nombre del espacio de nombres "RemovedInOSPlatformAttribute" (¿falta una directiva "using" o una referencia de ensamblado?)**
- **Error CS0246: No se ha encontrado el tipo o el nombre del espacio de nombres "ObsoletedInOSPlatformAttribute" (¿falta una directiva "using" o una referencia de ensamblado?)**

Ejemplo de error en tiempo de ejecución:

**Excepción no controlada. System.TypeLoadException: No se pudo cargar el tipo "System.Runtime.Versioning.MinimumOSPlatformAttribute" desde el ensamblado "System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".**

Para resolver estos errores:

- Actualice todas las referencias de `MinimumOSPlatformAttribute` a <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.
- Actualice todas las referencias de `RemovedInOSPlatformAttribute` a <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.
- Quite todas las referencias a `ObsoletedInOSPlatformAttribute`.
- Recompile el proyecto (o realice una operación de limpieza y compilación) para eliminar los artefactos de compilación anteriores.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

#### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
