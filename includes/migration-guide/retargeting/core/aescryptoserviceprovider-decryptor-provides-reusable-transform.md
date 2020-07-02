---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614656"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>El descifrador AesCryptoServiceProvider proporciona una transformación reutilizable

#### <a name="details"></a>Detalles

A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, el descifrador <xref:System.Security.Cryptography.AesCryptoServiceProvider> ofrece una transformación reutilizable. Después de llamar a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, la transformación se reinicializa y se puede reutilizar. Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, intentar volver a usar el descifrador mediante una llamada a <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> después de llamar a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> inicia una excepción <xref:System.Security.Cryptography.CryptographicException> o genera datos dañados.

#### <a name="suggestion"></a>Sugerencia

El impacto de este cambio debería ser mínimo, dado que es el comportamiento esperado. Las aplicaciones que dependen del comportamiento anterior pueden rechazar su uso si se agrega el ajuste de configuración siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

Además, las aplicaciones que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en una versión de .NET Framework a partir de la 4.6.2 pueden incluirse en este comportamiento si se agrega el ajuste de configuración siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
