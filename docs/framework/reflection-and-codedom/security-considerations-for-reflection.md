---
title: Consideraciones de seguridad sobre la reflexión
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], reflection
- MethodInfo parameters
- reflection, security
- partial trust,reflection
- nonpublic members
- reflection,partial trust
- link demands
ms.assetid: 42d9dc2a-8fcc-4ff3-b002-4ff260ef3dc5
ms.openlocfilehash: 1bdaf3abd39797274236ace4cb2967d2e7d199b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644188"
---
# <a name="security-considerations-for-reflection"></a>Consideraciones de seguridad sobre la reflexión

La reflexión proporciona la capacidad de obtener información sobre tipos y miembros, así como de obtener acceso a miembros (es decir, para llamar a métodos y constructores, obtener y establecer valores de propiedades, agregar y quitar controladores de eventos etc.). No hay restricciones en el uso de la reflexión para obtener información sobre tipos y miembros. Todo el código puede usar la reflexión para realizar las siguientes tareas:

- Enumerar tipos y miembros y examinar sus metadatos.

- Enumerar y examinar los ensamblados y módulos.

Por el contrario, el uso de la reflexión para obtener acceso a miembros está sujeto a restricciones. A partir de .NET Framework 4, solo el código de confianza puede usar la reflexión para obtener acceso a los miembros críticos para la seguridad. Además, solo el código de confianza puede usar la reflexión para obtener acceso a miembros no públicos a los que no tendría acceso directo el código compilado. Por último, el código que usa la reflexión para tener acceso a un miembro crítico para la seguridad debe tener los permisos que exija el miembro crítico para la seguridad, al igual que con el código compilado.

En función de los permisos necesarios, el código puede usar la reflexión para realizar los siguientes tipos de acceso:

- Acceso a miembros públicos que no son críticos para la seguridad.

- Acceso a miembros no públicos accesibles para el código compilado, si esos miembros no son críticos para la seguridad. Algunos ejemplos de estos miembros no públicos son:

  - Miembros protegidos de clases base del código de llamada. (En la reflexión, esto se conoce como acceso de nivel familiar).

  - Miembros `internal` (`Friend` en Visual Basic) del ensamblado del código de llamada. (En la reflexión, esto se conoce como acceso de nivel de ensamblado).

  - Miembros privados de otras instancias de la clase que contiene el código de llamada.

Por ejemplo, el código que se ejecuta en un dominio de aplicación en espacio aislado se limita al acceso descrito en esta lista, a menos que el dominio de aplicación conceda permisos adicionales.

A partir de .NET Framework 2.0 Service Pack 1, si se intenta tener acceso a los miembros que no suelen estar accesibles, se genera una petición para el conjunto de permisos del objeto de destino más <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>. El código que se ejecuta con plena confianza (por ejemplo, el código de una aplicación que se inicia desde la línea de comandos) siempre puede satisfacer estos permisos. (Esto está sujeto a las limitaciones de acceso a miembros críticos para la seguridad, como se describe más adelante en este artículo).

Si quiere, un dominio de aplicación en espacio aislado puede conceder <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>, tal como se describe en la sección [Acceso a miembros que suelen ser inaccesibles](#accessingNormallyInaccessible), más adelante en este artículo.

<a name="accessingSecurityCritical"></a>

## <a name="accessing-security-critical-members"></a>Acceso a miembros críticos para la seguridad

Un miembro es crítico para la seguridad si tiene el <xref:System.Security.SecurityCriticalAttribute>, si pertenece a un tipo que tiene el <xref:System.Security.SecurityCriticalAttribute>, o si se encuentra en un ensamblado crítico para la seguridad. A partir de .NET Framework 4, las reglas para tener acceso a los miembros críticos para la seguridad son los siguientes:

- El código transparente no puede usar la reflexión para tener acceso a miembros críticos para la seguridad, incluso si el código es de plena confianza. Se produce un <xref:System.MethodAccessException>, <xref:System.FieldAccessException> o <xref:System.TypeAccessException>.

- El código que se ejecuta con confianza parcial se trata como transparente.

Estas reglas son las mismas independientemente de si el código compilado accede directamente al miembro crítico para la seguridad, o si se accede a ese miembro él mediante reflexión.

El código de aplicación que se ejecuta desde la línea de comandos se ejecuta con plena confianza. Siempre y cuando no esté marcado como transparente, puede usar la reflexión para obtener acceso a los miembros críticos para la seguridad. Cuando se ejecuta el mismo código con confianza parcial (por ejemplo, en un dominio de aplicación en el espacio aislado), el nivel de confianza del ensamblado determina si puede acceder a código crítico para la seguridad: si el ensamblado tiene un nombre seguro y se instala en la caché global de ensamblados, es un ensamblado de confianza y puede llamar a miembros críticos para la seguridad. Si no es de confianza, se vuelve transparente aunque no esté marcado como tal y no tiene acceso a los miembros críticos para la seguridad.

Para obtener más información sobre el modelo de seguridad en .NET Framework 4, consulte [Cambios en la seguridad](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).

## <a name="reflection-and-transparency"></a>Reflexión y transparencia

A partir de .NET Framework 4, Common Language Runtime determina el nivel de transparencia de un tipo o miembro de varios factores, como el nivel de confianza del ensamblado y el nivel de confianza del dominio de aplicación. La reflexión proporciona las propiedades <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Type.IsSecuritySafeCritical%2A> y <xref:System.Type.IsSecurityTransparent%2A> para que pueda detectar el nivel de transparencia de un tipo. En la tabla siguiente se muestran las combinaciones válidas de estas propiedades.

|Nivel de seguridad|IsSecurityCritical|IsSecuritySafeCritical|IsSecurityTransparent|
|--------------------|------------------------|----------------------------|---------------------------|
|Crítico|`true`|`false`|`false`|
|Crítico para la seguridad|`true`|`true`|`false`|
|Transparente|`false`|`false`|`true`|

Usar estas propiedades es mucho más fácil que examinar las anotaciones de seguridad de un ensamblado y sus tipos, comprobar el nivel de confianza actual e intentar duplicar las reglas del runtime. Por ejemplo, el mismo tipo puede ser crítico para la seguridad cuando se ejecuta desde la línea de comandos o transparente en seguridad cuando se ejecuta en un dominio de aplicación en espacio aislado.

Hay propiedades similares las clases <xref:System.Reflection.MethodBase>, <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.Emit.TypeBuilder>, <xref:System.Reflection.Emit.MethodBuilder> y <xref:System.Reflection.Emit.DynamicMethod>. (Para otras abstracciones de reflexión y emisión de la reflexión, los atributos de seguridad se aplican a los métodos asociados; por ejemplo, en el caso de las propiedades se aplican a los descriptores de acceso de propiedad).

<a name="accessingNormallyInaccessible"></a>

## <a name="accessing-members-that-are-normally-inaccessible"></a>Acceso a miembros que suelen ser inaccesibles

Para usar la reflexión para invocar a los miembros que son inaccesibles según las reglas de accesibilidad de Common Language Runtime, el código debe disponer de uno de los siguientes permisos:

- Para permitir que el código invoque miembros no públicos: el código debe tener concedido <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>.

  > [!NOTE]
  > De forma predeterminada, la directiva de seguridad deniega este permiso al código que se origina desde Internet. Este permiso nunca debe concederse al código que se origina desde Internet.

- Para permitir que el código invoque miembros no públicos, siempre que el conjunto de permisos del ensamblado que contiene el miembro invocado sea igual (o un subconjunto) al conjunto de permisos del código del ensamblado que contiene la llamada: el código debe tener concedido <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.

Por ejemplo, suponga que concede a un dominio de aplicación permisos de Internet más <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> y, a continuación, ejecuta una aplicación de Internet con dos ensamblados, A y B.

- En ensamblado A puede usar la reflexión para obtener acceso a los miembros privados del ensamblado B, ya que el conjunto de permisos del ensamblado B no incluye los permisos que no se han concedido al A.

- El ensamblado A no puede usar la reflexión para acceder a los miembros privados de ensamblados de .NET Framework, como mscorlib.dll, ya que mscorlib.dll es de plena confianza y, por tanto, tiene permisos que no se han concedido al ensamblado A. Cuando la seguridad de acceso del código recorre la pila en tiempo de ejecución, se produce una <xref:System.MemberAccessException>.

## <a name="serialization"></a>Serialización

Para la serialización, <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A?displayProperty=nameWithType> proporciona la capacidad de obtener y establecer miembros de tipos serializables, independientemente de la accesibilidad. Este permiso permite al código descubrir y cambiar el estado privado de una instancia. (Además de tener concedidos los permisos adecuados, el tipo debe estar [marcado](../../standard/attributes/applying-attributes.md) como serializable en los metadatos).

## <a name="parameters-of-type-methodinfo"></a>Parámetros de tipo MethodInfo

Evite escribir miembros públicos que toman parámetros <xref:System.Reflection.MethodInfo>, especialmente para código de confianza. Estos miembros podrían ser más vulnerables al código malintencionado. Por ejemplo, imagine un miembro público en código de plena confianza que toma un parámetro <xref:System.Reflection.MethodInfo>. Suponga que el miembro público llama indirectamente al método <xref:System.Reflection.MethodBase.Invoke%2A> en el parámetro proporcionado. Si el miembro público no realiza las comprobaciones de permiso necesarias, la llamada al método <xref:System.Reflection.MethodBase.Invoke%2A> siempre se realizará correctamente porque el sistema de seguridad determina que el llamador es de gran confianza. Incluso si el código malintencionado no tiene permiso para invocar directamente al método, podrá hacerlo indirectamente mediante una llamada al miembro público.

## <a name="version-information"></a>Información de versión

- A partir de .NET Framework 4, el código transparente no puede usar la reflexión para obtener acceso a los miembros críticos para la seguridad.

- La marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> se introdujo en .NET Framework 2.0 Service Pack 1. Las versiones anteriores de .NET Framework requieren la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> en el código que usa la reflexión para acceder a miembros no públicos. Se trata de un permiso que nunca debe concederse al código de confianza parcial.

- A partir de .NET Framework 2.0, el uso de la reflexión para obtener información sobre tipos y miembros no públicos no requiere ningún permiso. En versiones anteriores, se requiere <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.ReflectionPermissionFlag>
- <xref:System.Security.Permissions.ReflectionPermission>
- <xref:System.Security.Permissions.SecurityPermission>
- [Cambios de seguridad](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
- [Seguridad de acceso del código](../misc/code-access-security.md)
- [Problemas de seguridad en la emisión de la reflexión](security-issues-in-reflection-emit.md)
- [Ver información tipos](viewing-type-information.md)
- [Aplicar atributos](../../standard/attributes/applying-attributes.md)
- [Acceso a atributos personalizados](accessing-custom-attributes.md)
