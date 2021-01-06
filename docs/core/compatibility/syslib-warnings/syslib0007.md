---
title: Advertencia SYSLIB0007
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0007.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: c011340665a0c53172bf5b23e032d78301b3cd72
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596410"
---
# <a name="syslib0007-default-implementations-of-cryptography-algorithms-not-supported"></a>SYSLIB0007: implementaciones predeterminadas de algoritmos de criptografía no compatibles

El sistema de configuración de criptografía de .NET Framework no permite la agilidad criptográfica adecuada y no está presente en .NET Core ni .NET 5+. Los requisitos de compatibilidad con versiones anteriores de .NET también impiden que el marco actualice determinadas API criptográficas para mantenerse al día de los avances en la criptografía. Como resultado, las siguientes API se han marcado como obsoletas a partir de .NET 5.0. El uso de estas API genera una advertencia `SYSLIB0007` en tiempo de compilación.

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

## <a name="workarounds"></a>Soluciones alternativas

- La acción recomendada consiste en reemplazar las llamadas a las API que ahora son obsoletas por llamadas a métodos de generador para algoritmos específicos, como por ejemplo <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>. Esto le proporciona control total sobre los algoritmos de los que se crean instancias.

- Si tiene que mantener la compatibilidad con cargas existentes generadas por aplicaciones de .NET Framework en las que se usan las API obsoletas, use los reemplazos sugeridos en la tabla siguiente. En la tabla se proporciona una asignación de los algoritmos predeterminados de .NET Framework a sus equivalentes de .NET 5+.

  | .NET Framework | Reemplazo compatible con .NET Core / .NET 5.0+ | Comentarios |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | El algoritmo SHA-1 se considera interrumpido. Considere la posibilidad de usar un algoritmo más seguro si es posible. Consulte con el asesor de seguridad para obtener más información. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | El algoritmo HMACSHA1 no se recomienda para la mayoría de las aplicaciones modernas. Considere la posibilidad de usar un algoritmo más seguro si es posible. Consulte con el asesor de seguridad para obtener más información. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | El algoritmo HMACSHA1 no se recomienda para la mayoría de las aplicaciones modernas. Considere la posibilidad de usar un algoritmo más seguro si es posible. Consulte con el asesor de seguridad para obtener más información. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Vea también

- [No se admite la creación de instancias de implementaciones predeterminadas de las abstracciones criptográficas](../cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)
