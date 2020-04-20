---
ms.openlocfilehash: b5b724afefcce69df706f2bea0b1612db653af03
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275250"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>Ha aumentado el tamaño mínimo de la generación de claves RSAOpenSsl

El tamaño mínimo para generar nuevas claves RSA en Linux ha aumentado de 384 bits a 512 bits.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0, el tamaño mínimo de clave permitido que notifica la propiedad `LegalKeySizes` en instancias de RSA desde <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A> y <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> en Linux ha aumentado de 384 a 512.

Por consiguiente, .NET Core 2.2 y versiones anteriores, una llamada de método como `RSA.Create(384)` se realiza correctamente. En .NET Core 3.0 y versiones posteriores, la llamada de método `RSA.Create(384)` produce una excepción que indica que el tamaño es demasiado pequeño.

Este cambio se realizó porque OpenSSL, que realiza las operaciones criptográficas en Linux, ha aumentado su mínimo entre las versiones 1.0.2 y 1.1.0. .NET Core 3.0 prefiere OpenSSL 1.1. x a 1.0. x, y la versión mínima notificada se elevó para reflejar esta nueva limitación de dependencia más alta.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Si llama a cualquiera de las API afectadas, asegúrese de que el tamaño de las claves generadas no sea inferior al mínimo del proveedor.

> [!NOTE]
> El RSA de 384 bits ya se considera inseguro (al igual que el RSA de 512 bits). Las recomendaciones modernas, como [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), sugieren 2048 bits como tamaño mínimo para las claves recién generadas.

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
