---
ms.openlocfilehash: 6ffd4147a99a59d0a2e50d3f88279608e286aed1
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90680019"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a>Transformación del bloque final solo durante el proceso de escritura mediante CryptoStream.Dispose

El método <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>, que se usa para finalizar operaciones `CryptoStream`, ya no intenta transformar el bloque final durante la lectura.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, si un usuario realizaba una lectura incompleta al usar <xref:System.Security.Cryptography.CryptoStream> en el modo <xref:System.Security.Cryptography.CryptoStreamMode.Read>, el método <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> podía producir una excepción (por ejemplo, al usar AES con espaciado interno). Se producía la excepción porque se intentaba transformar el bloque final, pero los datos estaban incompletos.

En .NET Core 3.0 y versiones posteriores, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> ya no intenta transformar el bloque final durante la lectura, lo que permite hacer lecturas incompletas.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio permite las lecturas incompletas de la secuencia de cifrado cuando se cancela una operación de red, sin necesidad de capturar una excepción.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

La mayoría de las aplicaciones no se verán afectadas por este cambio.

Si su aplicación detectaba anteriormente una excepción en caso de una lectura incompleta, puede eliminar ese bloque `catch`.
Si su aplicación usaba la transformación del bloque final en operaciones hash, puede que tenga que asegurarse de que se lee toda la secuencia antes de eliminar el bloque.

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
