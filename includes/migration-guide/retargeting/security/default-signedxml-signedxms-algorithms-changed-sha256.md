---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614813"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Los algoritmos SignedXML y SignedXMS predeterminados se han cambiado a SHA256

#### <a name="details"></a>Detalles

En .NET Framework 4.7 y versiones anteriores, SignedXML y SignedCMS usaban SHA1 de forma predeterminada para algunas operaciones. A partir de .NET Framework 4.7.1, SHA256 está habilitado de forma predeterminada para estas operaciones. Este cambio es necesario porque SHA1 ya no se considera seguro.

#### <a name="suggestion"></a>Sugerencia

Hay dos valores de modificador de contexto nuevos para controlar si se usa SHA1 (no seguro) o SHA256 de forma predeterminada:

- Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms
- Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms. Para las aplicaciones destinadas a .NET Framework 4.7.1 y versiones posteriores, si no se quiere usar SHA256, se puede restaurar el valor predeterminado a SHA1 si se agrega el conmutador de configuración siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

Para las aplicaciones destinadas a .NET Framework 4.7 y versiones posteriores, se puede permitir este cambio si se agrega el conmutador de configuración siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
