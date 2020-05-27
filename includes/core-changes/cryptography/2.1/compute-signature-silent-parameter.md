---
ms.openlocfilehash: b861dbaa02c97a03c015fdf4e63d25c40c90ea0a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720925"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>Se respeta el parámetro booleano de SignedCms.ComputeSignature

En .NET Core, se respeta el parámetro booleano `silent` del método <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>. No se muestra una solicitud de PIN si este parámetro se establece en `true`.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, se omite el parámetro `silent` del método <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> y siempre se muestra una solicitud de PIN si lo exige el proveedor. En .NET Core, se respeta el parámetro `silent` y, si se establece en `true`, nunca se muestra una solicitud de PIN, aunque lo exija el proveedor.

La compatibilidad con los mensajes CMS/PKCS #7 se presentó en .NET Core en la versión 2.1.

#### <a name="version-introduced"></a>Versión introducida

2.1

#### <a name="recommended-action"></a>Acción recomendada

Para asegurarse de que aparece una solicitud de PIN si esta se exige, las aplicaciones de escritorio deben llamar a <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> y establecer el parámetro booleano en `false`. El comportamiento resultante es el mismo que en .NET Framework independientemente de si el contexto silencioso está deshabilitado.

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
