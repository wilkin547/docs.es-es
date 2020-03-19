---
ms.openlocfilehash: 6a5cd260a2820e2a81142f6d55e32e91173ca503
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147456"
---
### <a name="openssl-versions-on-macos"></a>Versiones de OpenSSL en macOS

Ahora, los runtime de .NET Core 3.0 y versiones posteriores en macOS prefieren las versiones de OpenSSL 1.1.x a las versiones de OpenSSL 1.0.x en los tipos <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> y <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.

Ahora, el runtime de .NET Core 2.1 es compatible con las versiones de OpenSSL 1.1.x, pero siguen siendo preferibles las versiones de OpenSSL 1.0.x.

#### <a name="change-description"></a>Descripción del cambio

Antes, el runtime de .NET Core usaba versiones de OpenSSL 1.0.x en macOS para en los tipos que interactúan con OpenSSL. La versión más reciente de OpenSSL 1.0.x, OpenSSL 1.0.2, ya no se admite. Para mantener los tipos que usan OpenSSL en versiones compatibles de OpenSSL, los runtime de .NET Core 3.0 y versiones posteriores usan ahora las versiones más recientes de OpenSSL en macOS.

Con este cambio, el comportamiento de los runtime de .NET Core en macOS es el siguiente:

- Los runtime de .NET Core 3.0 y versiones posteriores usan OpenSSL 1.1.x (si está disponible) y revierten a OpenSSL 1.0.x solo si no hay disponible ninguna versión 1.1.x.

  En el caso de los autores de llamada que usen los tipos de interoperabilidad de OpenSSL con P/Invoke personalizados, siga las instrucciones de los comentarios sobre <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>. La aplicación se puede bloquear si no se comprueba el valor de <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion>.

- Los runtime de .NET Core 2.1 usan OpenSSL 1.0.x (si está disponible) y revierten a OpenSSL 1.1.x si no hay disponible ninguna versión 1.0.x.

  El runtime 2.1 prefiere la versión anterior de OpenSSL porque la propiedad <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> no existe en .NET Core 2.1, por lo que la versión de OpenSSL no se puede determinar de forma confiable en tiempo de ejecución.

#### <a name="version-introduced"></a>Versión introducida

- .NET Core 2.1.16
- .NET Core 3.0.3
- .NET Core 3.1.2

#### <a name="recommended-action"></a>Acción recomendada

- Desinstale la versión 1.0.2 de OpenSSL si ya no la necesita.

- Instale OpenSSL 1.1.x si usa los tipos <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> o <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.

- Si usa los tipos de interoperabilidad de OpenSSL con P/Invoke personalizados, siga las instrucciones de los comentarios sobre <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

CoreFX

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
