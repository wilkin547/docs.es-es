---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616097"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey devuelve RSACng en net462 (o Lightup) sin cambios de redestinación

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6.2, se ha cambiado (sin peculiaridades) el tipo concreto del objeto devuelto por el método <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> de una implementación de CryptoServiceProvider a una implementación de Cng. Esto se debe a que la implementación ha pasado de usar `certificate.PublicKey.Key` a usar la `certificate.GetAnyPublicKey` interna que reenvía a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.

#### <a name="suggestion"></a>Sugerencia

A partir de las aplicaciones que se ejecutan en .NET Framework 4.7.1, se puede usar la implementación de CryptoServiceProvider que se usa de forma predeterminada en .NET Framework 4.6.1 y versiones anteriores mediante la adición del conmutador siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
