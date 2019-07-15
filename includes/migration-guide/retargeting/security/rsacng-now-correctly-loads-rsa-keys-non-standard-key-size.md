---
ms.openlocfilehash: 6d9f4b630e95d9a63393da3ae0ecd83c2b994712
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859252"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng ahora carga correctamente las claves RSA de tamaño de clave no estándar

|   |   |
|---|---|
|Detalles|En las versiones de .NET Framework anteriores a la 4.6.2, los clientes con tamaños de clave no estándar para los certificados RSA no podrán tener acceso a esas claves a través de los métodos de extensión <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> y <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name>.  Se iniciará una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> con el mensaje &quot;The requested key size is not supported&quot; (No se admite el tamaño de clave solicitado). Este problema se ha solucionado en .NET Framework 4.6.2. De forma similar, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> y <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> ahora funcionan con tamaños de clave no estándar sin iniciar una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>.|
|Sugerencia|Si no hay ninguna lógica de control de excepciones que se base en el comportamiento anterior en el que se inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> cuando se usan tamaños de clave no estándar, considere la posibilidad de quitar la lógica.|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|

