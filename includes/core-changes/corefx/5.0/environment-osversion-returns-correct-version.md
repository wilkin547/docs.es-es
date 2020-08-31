---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558194"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion devuelve la versión correcta del sistema operativo

<xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve una versión del sistema operativo que puede ser incorrecta cuando una aplicación se ejecuta en modo de compatibilidad de Windows. Para más información, vea [Notas de la función GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).

A partir de .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo.

#### <a name="reason-for-change"></a>Motivo del cambio

Los usuarios de esta propiedad esperan que devuelva la versión real del sistema operativo. La mayoría de las aplicaciones .NET no especifican su versión compatible en el manifiesto de aplicación y, por tanto, obtienen la versión admitida predeterminada del host dotnet. Como resultado, la corrección de compatibilidad no suele ser significativa para la aplicación que se está ejecutando. Cuando Windows lanza una nueva versión y todavía se está usando un host dotnet anterior, estas aplicaciones pueden obtener una versión incorrecta del sistema operativo. La devolución de la versión real está más alineada con las expectativas de los desarrolladores de esta API.

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="recommended-action"></a>Acción recomendada

Revise y pruebe cualquier código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para asegurarse de que se comporta como espera.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
