---
title: 'Cambio importante: Environment.OSVersion devuelve la versión correcta del sistema operativo'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde Environment.OSVersion devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.
ms.date: 11/01/2020
ms.openlocfilehash: c810d9a7a028a0c60c30d69e78a9b9c695d933ef
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009526"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion devuelve la versión correcta del sistema operativo

<xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve una versión del sistema operativo que puede ser incorrecta cuando una aplicación se ejecuta en modo de compatibilidad de Windows. Para más información, vea [Notas de la función GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks). En macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión subyacente del kernel de Darwin.

A partir de .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo para Windows y macOS.

En la tabla siguiente se muestra la diferencia en el comportamiento.

|  | Versiones anteriores de .NET | .NET 5 y versiones posteriores |
|--|------------------------|---------|
| Windows | 6.2.9200.0 | 10.0.19042.0 |
| macOS | 19.6.0.0 | 10.15.7 |

## <a name="reason-for-change"></a>Motivo del cambio

Los usuarios de esta propiedad esperan que devuelva la versión real del sistema operativo. La mayoría de las aplicaciones .NET no especifican su versión compatible en el manifiesto de aplicación y, por tanto, obtienen la versión admitida predeterminada del host dotnet. Como resultado, la corrección de compatibilidad no suele ser significativa para la aplicación que se está ejecutando. Cuando Windows lanza una nueva versión y todavía se está usando un host dotnet anterior, estas aplicaciones pueden obtener una versión incorrecta del sistema operativo. La devolución de la versión real está más alineada con las expectativas de los desarrolladores de esta API.

Con la introducción de <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType> y <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> en .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> ha cambiado a fin de ser coherente para Windows y macOS.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Revise y pruebe cualquier código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para asegurarse de que se comporta como espera.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
