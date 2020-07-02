---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616290"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a>Las clases de criptografía administradas no producen una excepción CryptographyException en el modo FIPS

#### <a name="details"></a>Detalles

En NET Framework 4.7.2 y versiones anteriores, las clases del proveedor de servicios criptográficos administrados, como <xref:System.Security.Cryptography.SHA256Managed>, producen una excepción <xref:System.Security.Cryptography.CryptographicException> cuando las bibliotecas criptográficas del sistema están configuradas en modo FIPS. Estas excepciones se producen porque las versiones administradas no han sometido al FIPS (Estándar federal de procesamiento de información) según la certificación 140-2, así como para bloquear los algoritmos criptográficos que no se consideran aprobados según las reglas FIPS.  Dado que pocos desarrolladores tienen sus equipos de desarrollo en el modo FIPS, estas excepciones se producen con frecuencia solo en sistemas de producción. Las aplicaciones que tienen como destino .NET Framework 4.8 y versiones posteriores cambian automáticamente a la directiva más reciente y menos estricta, para que ya no se produzca de forma predeterminada <xref:System.Security.Cryptography.CryptographicException> en estos casos. En su lugar, las clases de criptografía administradas redirigen las operaciones criptográficas a una biblioteca de criptografía del sistema. Este cambio de directiva elimina eficazmente una diferencia potencialmente confusa entre entornos de desarrollo y entornos de producción, y permite que componentes nativos y componentes administrados funcionen bajo la misma directiva criptográfica.

#### <a name="suggestion"></a>Sugerencia

Si no desea este comportamiento, puede dejar de participar en él y restaurar el comportamiento anterior hasta que se produzca <xref:System.Security.Cryptography.CryptographicException> en el modo FIPS agregando la opción de configuración [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

Si la aplicación tiene como destino .NET Framework 4.7.2 o versiones anteriores, se puede también participar en este cambio agregando la opción de configuración [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.8         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
