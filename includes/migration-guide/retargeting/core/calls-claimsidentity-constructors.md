---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614641"
---
### <a name="calls-to-claimsidentity-constructors"></a>Llamadas a los constructores de ClaimsIdentity

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6.2, hay un cambio en el modo en que los constructores <xref:System.Security.Claims.ClaimsIdentity> con un parámetro <xref:System.Security.Principal.IIdentity?displayProperty=fullName> establecen la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>. Si el argumento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> es un objeto <xref:System.Security.Claims.ClaimsIdentity> y la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> de ese objeto <xref:System.Security.Claims.ClaimsIdentity> no es `null`, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> se conecta mediante el método <xref:System.Security.Claims.ClaimsIdentity.Clone>. En .NET Framework 4.6.1 y versiones anteriores, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> se adjuntaba como una referencia existente. Debido a este cambio, a partir de .NET Framework 4.6.2, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> del nuevo objeto <xref:System.Security.Claims.ClaimsIdentity> no es igual que la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> del argumento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> del constructor. En .NET Framework 4.6.1 y versiones anteriores, es igual.

#### <a name="suggestion"></a>Sugerencia

Si no desea este comportamiento, puede restaurar el comportamiento anterior si establece el modificador `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` en el archivo de configuración de la aplicación en `true`. Para ello, es necesario agregar lo siguiente a la sección `<runtime>` del archivo web.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
