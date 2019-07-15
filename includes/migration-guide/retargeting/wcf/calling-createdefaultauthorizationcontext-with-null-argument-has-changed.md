---
ms.openlocfilehash: a29f0ca6d235250ac1f41e686178b2d6affcd8a0
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804569"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>La llamada a CreateDefaultAuthorizationContext con un argumento NULL ha cambiado

|   |   |
|---|---|
|Detalles|La implementación del elemento <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=name> devuelto por una llamada a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=name> con un argumento authorizationPolicies nulo ha cambiado su implementación en .NET Framework 4.6.|
|Sugerencia|En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento. En estos casos, es posible restaurar el comportamiento anterior de dos maneras:<ol><li>Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6. Para los servicios hospedados en IIS, use el elemento &lt;httpRuntime plataformaDestino=&quot;x.x&quot; /&gt; para establecer como destino una versión anterior de .NET Framework.</li><li>Agregue la siguiente línea a la sección <code>&lt;appSettings&gt;</code> del archivo app.config: <code>&lt;add key=&quot;appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext&quot; value=&quot;true&quot; /&gt;</code>.</li></ol>|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType></li></ul>|

