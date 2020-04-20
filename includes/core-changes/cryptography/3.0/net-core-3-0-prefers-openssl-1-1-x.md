---
ms.openlocfilehash: 65d8ca480d41a3807473583355fe8be41e0e9701
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275419"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a>.NET Core 3.0 prefiere OpenSSL 1.1.x a OpenSSL 1.0.x

.NET Core para Linux, que funciona en varias distribuciones de Linux, puede admitir OpenSSL 1.0.x y OpenSSL 1.1.x.  .NET Core 2.1 y .NET Core 2.2 buscan 1.0.x primero y luego recurren a 1.1.x; .NET Core 3.0 busca 1.1.x primero. Este cambio se realizó para agregar compatibilidad con nuevos estándares criptográficos.

Este cambio puede afectar a las bibliotecas o aplicaciones que llevan a cabo la interoperabilidad de la plataforma con los tipos de interoperabilidad específicos de OpenSSL en .NET Core.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.2 y versiones anteriores, el runtime prefiere cargar OpenSSL 1.0.x a 1.1.x. Esto significa que los tipos <xref:System.IntPtr> y <xref:System.Runtime.InteropServices.SafeHandle> para la interoperabilidad con OpenSSL se usan, por orden de preferencia, con libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10.

A partir de .NET Core 3.0, el runtime prefiere cargar OpenSSL 1.1.x a OpenSSL 1.0.x, por lo que los tipos <xref:System.IntPtr> y <xref:System.Runtime.InteropServices.SafeHandle> para la interoperabilidad con OpenSSL se usan, por orden de preferencia, con libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1. Por consiguiente, las bibliotecas y aplicaciones que interactúan directamente con OpenSSL pueden tener punteros incompatibles con los valores expuestos en .NET Core cuando se actualiza desde .NET Core 2.1 o.NET Core 2.2.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Las bibliotecas y aplicaciones que realizan operaciones directas con OpenSSL deben tener cuidado de asegurarse de que usan la misma versión de OpenSSL que el runtime de .NET Core.

Todas las bibliotecas o aplicaciones que usan los valores <xref:System.IntPtr> o <xref:System.Runtime.InteropServices.SafeHandle> de los tipos criptográficos de .NET Core directamente con OpenSSL deben comparar la versión de la biblioteca que usan con la nueva propiedad <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> para asegurarse de que los punteros son compatible.

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
