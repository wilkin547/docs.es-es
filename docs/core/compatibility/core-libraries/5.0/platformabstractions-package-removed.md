---
title: 'Cambio importante: Retirada del paquete Microsoft.DotNet.PlatformAbstractions'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET en las que se ha quitado el paquete Microsoft.DotNet.PlatformAbstractions.
ms.date: 11/01/2020
ms.openlocfilehash: aff7be816815b016e3ce694c4e9a97410538c08d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257250"
---
# <a name="microsoftdotnetplatformabstractions-package-removed"></a>Retirada del paquete Microsoft.DotNet.PlatformAbstractions

No se crearán nuevas versiones del [paquete Microsoft.DotNet.PlatformAbstractions de NuGet](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/).

## <a name="change-description"></a>Descripción del cambio

Anteriormente, junto a las nuevas versiones de .NET Core, también se producían nuevas versiones de la biblioteca <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>. En el futuro, no se agregarán funcionalidades nuevas a la biblioteca ni se publicarán nuevas versiones principales. No obstante, las versiones existentes de la biblioteca seguirán funcionando y recibirán mantenimiento.

La biblioteca <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> se superpone a las API que ya están establecidas en los espacios de nombres System.\* Además, algunas API <xref:Microsoft.DotNet.PlatformAbstractions> no se diseñaron con el mismo nivel de escrutinio y compatibilidad a largo plazo que el resto de las API System.\* . Por ejemplo, <xref:Microsoft.DotNet.PlatformAbstractions> usa la enumeración `Platform` para describir la plataforma actual del sistema operativo. Este diseño de enumeración se rechazó explícitamente cuando se diseñó la API <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> con el fin de admitir plataformas nuevas y favorecer la flexibilidad en el futuro.

Los escenarios habilitados por la biblioteca <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> ahora son posibles sin la enumeración. Las versiones existentes seguirán funcionando, incluso en .NET 5 y versiones posteriores, y recibirán mantenimiento junto con las versiones anteriores de .NET Core. No obstante, no se agregarán nuevas funcionalidades a la biblioteca. En cambio, las otras bibliotecas y API sí recibirán nuevas funcionalidades.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Puede seguir usando versiones anteriores de la biblioteca si cumplen sus requisitos.

- En caso de que las versiones anteriores no satisfagan sus necesidades, reemplace los usos de las API `PlatformAbstractions` por las opciones de reemplazo recomendadas.

  | API `PlatformAbstractions` | Reemplazo recomendado |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> y <xref:System.Environment.OSVersion?displayProperty=nameWithType> |

  > [!NOTE]
  > La finalidad de la mayoría de los casos de uso de `RuntimeEnvironment.OperatingSystem` y `RuntimeEnvironment.OperatingSystemVersion` es de visualización (por ejemplo, mostrar a un usuario el registro y la telemetría). No se recomienda tomar decisiones en tiempo de ejecución basadas en una versión del sistema operativo (SO). Ahora, <xref:System.Environment.OSVersion?displayProperty=nameWithType> [devuelve la versión correcta](environment-osversion-returns-correct-version.md) para los sistemas operativos Windows y macOS. En cambio, para la mayoría de las distribuciones de UNIX, no queda tan claro lo que se considera "versión del sistema operativo". Por ejemplo, podría ser la versión del kernel de Linux o podría ser la versión de distribución. En la mayoría de las plataformas UNIX, <xref:System.Environment.OSVersion?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> devuelven la versión devuelta por `uname`. Para obtener el nombre y la versión de la distribución de Linux, lo recomendado es leer el archivo */etc/os-release*.

## <a name="affected-apis"></a>API afectadas

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
