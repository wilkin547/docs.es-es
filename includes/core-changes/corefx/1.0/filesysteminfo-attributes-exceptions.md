---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021824"
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

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
