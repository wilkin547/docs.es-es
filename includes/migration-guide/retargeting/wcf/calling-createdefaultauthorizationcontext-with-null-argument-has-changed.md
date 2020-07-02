---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615768"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>La llamada a CreateDefaultAuthorizationContext con un argumento NULL ha cambiado

#### <a name="details"></a>Detalles

La implementación del elemento <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> devuelto por una llamada a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> con un argumento authorizationPolicies nulo ha cambiado su implementación en .NET Framework 4.6.

#### <a name="suggestion"></a>Sugerencia

En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento. En estos casos, es posible restaurar el comportamiento anterior de dos maneras:

- Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6. Para los servicios hospedados en IIS, use el elemento `<httpRuntime targetFramework="x.x">` para que se dirija a una versión anterior de .NET Framework.
- Agregue la siguiente línea a la sección `<appSettings>` del archivo app.config:

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
