---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887838"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash ahora devuelve False para los errores de comprobación

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6.2, este método devuelve **False** si la propia firma tiene un formato incorrecto. Ahora devuelve false para los errores de comprobación. En .NET Framework 4.6 y 4.6.1, el método inicia una excepción <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> si la propia firma tiene el formato incorrecto.|
|Sugerencia|Se debe ejecutar el código cuya ejecución dependa del control de <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> en lugar de ejecutarse si se produce un error en la validación y el método devuelve **False**.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
