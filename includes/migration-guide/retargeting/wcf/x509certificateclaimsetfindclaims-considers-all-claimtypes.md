---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614737"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims considera todos los argumentos claimType

#### <a name="details"></a>Detalles

En las aplicaciones destinadas a .NET Framework 4.6.1, si un conjunto de notificaciones X509 se inicializó desde un certificado con varias entradas DNS en su campo SAN, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> trata de hacer coincidir el argumento claimType con todas las entradas DNS. En las aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> solo trata de hacer coincidir el argumento claimType con la última entrada DNS.

#### <a name="suggestion"></a>Sugerencia

Este cambio solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6.1. Este cambio puede deshabilitarse, o habilitarse si se establece como destino una versión anterior a la 4.6.1, con el modificador de compatibilidad [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
