---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449416"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>UnauthorizedAccessException producida por FileSystemInfo.Attributes

En .NET Core, se produce una <xref:System.UnauthorizedAccessException> si el autor de la llamada intenta establecer un valor de atributo de archivo pero no tiene permiso de escritura.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, se produce una <xref:System.ArgumentException> si el autor de la llamada intenta establecer un valor de atributo de archivo en <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> pero no tiene permiso de escritura. En .NET Core, se produce una <xref:System.UnauthorizedAccessException> en su lugar. (En .NET Core, se sigue produciendo una <xref:System.ArgumentException> si el autor de la llamada intenta establecer un atributo de archivo no válido).

#### <a name="version-introduced"></a>Versión introducida

1.0

#### <a name="recommended-action"></a>Acción recomendada

Modifique las instrucciones `catch` para capturar una <xref:System.UnauthorizedAccessException> en lugar de una <xref:System.ArgumentException>, o además de esta, según sea necesario.

#### <a name="category"></a>Categoría

CoreFX

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
