---
ms.openlocfilehash: c1e85941c8c6c31c7d937d0671ad955fa6490783
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614653"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng ahora carga correctamente las claves RSA de tamaño de clave no estándar

#### <a name="details"></a>Detalles

En las versiones de .NET Framework anteriores a la 4.6.2, los clientes con tamaños de clave no estándar para los certificados RSA no podrán tener acceso a esas claves a través de los métodos de extensión <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> y <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName>.  Se iniciará una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> con el mensaje &quot;The requested key size is not supported&quot; (No se admite el tamaño de clave solicitado). Este problema se ha solucionado en .NET Framework 4.6.2. De forma similar, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> y <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> ahora funcionan con tamaños de clave no estándar sin iniciar una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Si no hay ninguna lógica de control de excepciones que se base en el comportamiento anterior en el que se inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> cuando se usan tamaños de clave no estándar, considere la posibilidad de quitar la lógica.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
