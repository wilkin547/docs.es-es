---
title: Clase ControlBuilderInterceptor
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 0cd7409deb9cb84783cfa70600999fa4b2a2d2e2
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "88187984"
---
# <a name="controlbuilderinterceptor-class"></a>Clase ControlBuilderInterceptor

La `ControlBuilderInterceptor` clase permite personalizar o controlar el proceso de compilación.

## <a name="syntax"></a>Sintaxis

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> La `ControlBuilderInterceptor` clase es interna y no está diseñada para usarse directamente en el código.
>
> Tal y como se describe en la sección Comentarios, se puede comprobar la existencia de este tipo para determinar si la compatibilidad con el tipo de interceptor está presente. Microsoft no admite ningún otro uso de esta clase en una aplicación de producción bajo ninguna circunstancia.

## <a name="remarks"></a>Observaciones

En .NET Framework 2,0 y .NET Framework 3,5, las actualizaciones del [2020 de agosto](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) agregaron compatibilidad con el uso de un tipo de interceptor para personalizar o controlar el proceso de compilación. Puede determinar si esta compatibilidad está presente mediante <xref:System.Type.GetType?displayProperty=nameWithType> para comprobar la existencia del `ControlBuilderInterceptor` tipo, tal y como se muestra en el código siguiente.

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

Si el valor devuelto no es null, la compatibilidad con el interceptor está presente. Si el valor devuelto es `null` , o si se produce una excepción, no se han instalado las actualizaciones de agosto de 2020 y la compatibilidad con el interceptor está ausente.

Si la compatibilidad con el interceptor está presente, puede escribir y registrar un tipo de interceptor que interactúe con el proceso de compilación exactamente del mismo modo que lo <xref:System.Web.Compilation.ControlBuilderInterceptor> hace en versiones posteriores de .NET Framework. En .NET Framework 2,0 y .NET Framework 3,5, el tipo de interceptor puede ser cualquier clase que cumpla los requisitos siguientes:

* Tiene un constructor público sin parámetros.
* Tiene métodos públicos y no estáticos denominados `PreControlBuilderInit` y `OnProcessGeneratedCode` que tienen la misma firma y semántica que los <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> métodos y, que existen en versiones posteriores de .NET Framework.

Registre el tipo de interceptor mediante la `aspnet:20ControlBuilderInterceptor` clave en la configuración de la aplicación ASP.net ( `<appSettings>` ). Esta configuración de aplicación debe aparecer en el equipo o la aplicación *web.config* archivo. Especifique el tipo de interceptor usando su nombre de tipo calificado con el ensamblado. En el ejemplo siguiente se muestra cómo registrar un tipo de interceptor denominado `Fabrikam.Interceptor` .

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>
```

Para recuperar el nombre calificado con el ensamblado de un tipo, utilice la <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> propiedad, como se muestra en el código siguiente.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

Cuando existe compatibilidad con el interceptor, el proceso de compilación interactúa con el tipo enumerado de la manera descrita anteriormente. Cuando la compatibilidad con el interceptor está ausente, se omite la configuración de la aplicación y no tiene ningún efecto.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** System. Web. Compilation

**Ensamblado:** System. Web (en System.Web.dll)

**.NET Framework versiones:** 3,5, 2,0
