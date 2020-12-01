---
title: Problemas de seguridad en la emisión de la reflexión
description: Conozca los problemas de seguridad de la emisión de la reflexión, que se realiza por medio de ensamblados dinámicos o métodos dinámicos conectados con ensamblados existentes u hospedados de forma anónima.
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- emitting dynamic assemblies, security
- reflection emit, security
- reflection emit, partial trust scenarios
- partial trust,emitting dynamic methods
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- dynamic assemblies, security
ms.assetid: 0f8bf8fa-b993-478f-87ab-1a1a7976d298
ms.openlocfilehash: 859c564e107fd3a9b219d71dc6ac5ccdf6e9d690
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259283"
---
# <a name="security-issues-in-reflection-emit"></a>Problemas de seguridad en la emisión de la reflexión

.NET Framework proporciona tres maneras para emitir Lenguaje Intermedio de Microsoft (MSIL), cada una con sus propios problemas de seguridad:  
  
- [Ensamblados dinámicos](#Dynamic_Assemblies)  
  
- [Métodos dinámicos hospedados de forma anónima](#Anonymously_Hosted_Dynamic_Methods)  
  
- [Métodos dinámicos asociados a ensamblados existentes](#Dynamic_Methods_Associated_with_Existing_Assemblies)  
  
 Independientemente de la manera en que se genere código dinámico, la ejecución del código generado exige todos los permisos requeridos por los tipos y métodos que usa el código generado.  
  
> [!NOTE]
> Los permisos necesarios para la reflexión en código y la emisión de código han cambiado en las sucesivas versiones de .NET Framework. Vea el apartado [Información de versión](#Version_Information) más adelante en este tema.  
  
<a name="Dynamic_Assemblies"></a>

## <a name="dynamic-assemblies"></a>Ensamblados dinámicos  

 Los ensamblados dinámicos se crean mediante sobrecargas del método <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>. La mayoría de las sobrecargas de este método quedaron obsoletas en .NET Framework 4 debido a la eliminación de la directiva de seguridad de toda la máquina. (Vea [Security Changes](/previous-versions/dotnet/framework/security/security-changes) (Cambios de seguridad)). Las sobrecargas restantes se pueden ejecutar con cualquier código, independientemente del nivel de confianza. Estas sobrecargas se dividen en dos grupos: las que especifican una lista de atributos que se aplican al ensamblado dinámico cuando este se crea y las que no lo hacen. Si no se especifica el modelo de transparencia para el ensamblado durante su creación, mediante la aplicación del atributo <xref:System.Security.SecurityRulesAttribute>, el modelo de transparencia se hereda del ensamblado emisor.  
  
> [!NOTE]
> Los atributos que se aplican al ensamblado dinámico después de crearlo —mediante el método <xref:System.Reflection.Emit.AssemblyBuilder.SetCustomAttribute%2A>— no serán efectivos hasta que el ensamblado se guarde en el disco y se vuelva a cargar en la memoria.  
  
 El código de un ensamblado dinámico puede tener acceso a los tipos visibles y a los miembros de otros ensamblados.  
  
> [!NOTE]
> Los ensamblados dinámicos no usan las marcas <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> y <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> que permiten a los métodos dinámicos tener acceso a los tipos y miembros.  
  
 Los ensamblados dinámicos transitorios se crean en la memoria y nunca se guardan en el disco, por lo que no requieren ningún permiso de acceso de archivo. Guardar un ensamblado dinámico en el disco requiere <xref:System.Security.Permissions.FileIOPermission> con las marcas apropiadas.  
  
### <a name="generating-dynamic-assemblies-from-partially-trusted-code"></a>Generación de ensamblados dinámicos a partir de código de confianza parcial  

 Tenga en cuenta las condiciones en las que un ensamblado con permisos de Internet puede generar un ensamblado dinámico transitorio y ejecutar su código:  
  
- El ensamblado dinámico solo usa miembros y tipos públicos de otros ensamblados.  
  
- Los permisos exigidos por esos tipos y miembros se incluyen en el conjunto de permisos del ensamblado de confianza parcial.  
  
- El ensamblado no se guarda en el disco.  
  
- Los símbolos de depuración no se generan. (Los conjuntos de permisos `Internet` y `LocalIntranet` no incluyen los permisos necesarios).  
  
<a name="Anonymously_Hosted_Dynamic_Methods"></a>

## <a name="anonymously-hosted-dynamic-methods"></a>Métodos dinámicos hospedados de forma anónima  

 Los métodos dinámicos hospedados de forma anónima se crean mediante los dos constructores <xref:System.Reflection.Emit.DynamicMethod> que no especifican un tipo o módulo asociado, <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%29> y <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29>. Estos constructores colocan los métodos dinámicos en un ensamblado proporcionado por el sistema, de plena confianza y seguridad transparente. No se requieren permisos para usar estos constructores o emitir código para los métodos dinámicos.  
  
 En su lugar, cuando se crea un método dinámico hospedado de forma anónima, se captura la pila de llamadas. Cuando se construye el método, las peticiones de seguridad se realizan en la pila de llamadas capturadas.  
  
> [!NOTE]
> Desde el punto de vista conceptual, las peticiones se hacen durante la construcción del método. Es decir, las peticiones se pueden realizar al emitirse cada instrucción MSIL. En la implementación actual, todas las solicitudes se realizan cuando se llama al método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A?displayProperty=nameWithType> o cuando se invoca el compilador Just-In-Time (JIT), si el método se invoca sin llamar a <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  
  
 Si el dominio de aplicación lo permite, los métodos dinámicos hospedados de forma anónima pueden omitir las comprobaciones de visibilidad de JIT, con la restricción siguiente: Los tipos y miembros no públicos a los que accede un método dinámico hospedado de forma anónima deben estar en ensamblados cuyos conjuntos de permisos sean iguales (o sean subconjuntos) al conjunto de permisos de la pila de llamadas emisora. Esta capacidad restringida para omitir las comprobaciones de visibilidad JIT está habilitada si el dominio de aplicación concede <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.  
  
- Si su método usa solo tipos y miembros públicos, no se requieren permisos durante la construcción.  
  
- Si especifica que las comprobaciones de visibilidad JIT deben omitirse, la petición que se realiza cuando se construye el método incluye <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> y el conjunto de permisos del ensamblado que contiene el miembro no público al que se tiene acceso.  
  
 Dado que se tiene en cuenta el conjunto de permisos del miembro no público, el código de confianza parcial al que se le ha concedido <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> no puede elevar sus privilegios mediante la ejecución de miembros no públicos de ensamblados de confianza.  
  
 Como con cualquier otro código emitido, la ejecución del método dinámico requiere los permisos exigidos por los métodos que usa el método dinámico.  
  
 El ensamblado de sistema que hospeda los métodos dinámicos hospedados de forma anónima usa el modelo de transparencia <xref:System.Security.SecurityRuleSet.Level1?displayProperty=nameWithType>, que es el que se utilizaba en .NET Framework antes de la versión .NET Framework 4.  
  
 Para obtener más información, vea la clase <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-anonymously-hosted-dynamic-methods-from-partially-trusted-code"></a>Generación de métodos dinámicos hospedados de forma anónima a partir de código de confianza parcial  

 Tenga en cuenta las condiciones en las que un ensamblado con permisos de Internet puede generar un método dinámico hospedado de forma anónima y ejecutarlo:  
  
- El método dinámico solo usa miembros y tipos públicos. Si su conjunto de permisos incluye <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>, puede usar los tipos y miembros no públicos de cualquier ensamblado cuyo conjunto de permisos sea igual al conjunto de permisos (o un subconjunto del mismo) del ensamblado emisor.  
  
- Los permisos requeridos por todos los tipos y miembros usados por el método dinámico se incluyen en el conjunto de permisos del ensamblado de confianza parcial.  
  
> [!NOTE]
> Los métodos dinámicos no admiten símbolos de depuración.  
  
<a name="Dynamic_Methods_Associated_with_Existing_Assemblies"></a>

## <a name="dynamic-methods-associated-with-existing-assemblies"></a>Métodos dinámicos asociados a ensamblados existentes  

 Para asociar un método dinámico con un tipo o módulo en un ensamblado existente, use cualquiera de los constructores <xref:System.Reflection.Emit.DynamicMethod> que especifican el tipo o módulo asociado. Los permisos necesarios para llamar a estos constructores varían, ya que al asociar un método dinámico con un tipo o módulo existente, el método dinámico obtiene acceso a los miembros y tipos no públicos:  
  
- Un método dinámico que está asociado a un tipo tiene acceso a todos los miembros de ese tipo, incluso a los miembros privados, y a todos los tipos y miembros internos del ensamblado que contiene el tipo asociado.  
  
- Un método dinámico que está asociado a un módulo tiene acceso a todos los tipos y miembros `internal` (`Friend` en Visual Basic, `assembly` en los metadatos de Common Language Runtime) del módulo.  
  
 Además, se puede usar un constructor que especifique la capacidad de omitir las comprobaciones de visibilidad del compilador JIT. De este modo, el método dinámico obtiene acceso a todos los tipos y miembros de todos los ensamblados, con independencia del nivel de acceso.  
  
 Los permisos exigidos por el constructor dependen del nivel de acceso que decida conceder al método dinámico:  
  
- Si su método solo usa miembros y tipos públicos y lo asocia con su propio tipo o su propio módulo, no se requiere ningún permiso.  
  
- Si especifica que se deben omitir las comprobaciones de visibilidad JIT, el constructor exige <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>.  
  
- Si asocia el método dinámico con otro tipo, incluso de su propio ensamblado, el constructor exige <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> y <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=nameWithType>.  
  
- Si asocia el método dinámico con un tipo o módulo de otro ensamblado, el constructor exige dos cosas: <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> y el conjunto de permisos del ensamblado que contiene el otro módulo. Es decir, la pila de llamadas debe incluir todos los permisos del conjunto de permisos del módulo de destino, además de <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.  
  
    > [!NOTE]
    > Por motivos de compatibilidad con versiones anteriores, si se produce un error en la petición del conjunto de permisos más <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>, el constructor exige <xref:System.Security.Permissions.SecurityPermission> con la marca <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=nameWithType>.  
  
 Aunque los elementos de esta lista se describen en términos del conjunto de permisos concedidos del ensamblado emisor, recuerde que las peticiones se realizan en la pila de llamadas completa, incluido el límite del dominio de aplicación.  
  
 Para obtener más información, vea la clase <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-dynamic-methods-from-partially-trusted-code"></a>Generación de métodos dinámicos a partir de código de confianza parcial  
  
> [!NOTE]
> La manera recomendada para generar métodos dinámicos a partir de código de confianza parcial es usar [métodos dinámicos hospedados de forma anónima](#Anonymously_Hosted_Dynamic_Methods).  
  
 Tenga en cuenta las condiciones en las que un ensamblado con permisos de Internet puede generar un método dinámico y ejecutarlo:  
  
- El método dinámico está asociado con el módulo o el tipo que lo emite, o su conjunto de permisos incluye <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> y está asociado con un módulo de un ensamblado cuyo conjunto de permisos es igual al conjunto de permisos del ensamblado emisor (o un subconjunto del mismo).  
  
- El método dinámico solo usa miembros y tipos públicos. Si su conjunto de permisos incluye <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> y está asociado con un módulo de un ensamblado cuyo conjunto de permisos es igual al conjunto de permisos del ensamblado emisor (o un subconjunto del mismo), puede usar tipos y miembros marcados `internal` (`Friend` en Visual Basic, `assembly` en los metadatos de Common Language Runtime) en el módulo asociado.  
  
- Los permisos exigidos por todos los tipos y miembros usados por el método dinámico se incluyen en el conjunto de permisos del ensamblado de confianza parcial.  
  
- El método dinámico no omite las comprobaciones de visibilidad JIT.  
  
> [!NOTE]
> Los métodos dinámicos no admiten símbolos de depuración.  
  
<a name="Version_Information"></a>

## <a name="version-information"></a>Información de versión  

 A partir de .NET Framework 4, se elimina la directiva de seguridad de todo el equipo y la transparencia en seguridad se convierte en el mecanismo de cumplimiento predeterminado. Vea [Security Changes](/previous-versions/dotnet/framework/security/security-changes) (Cambios de seguridad).  
  
 A partir de .NET Framework 2.0 Service Pack 1, ya no es obligatorio usar <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType> al emitir ensamblados y métodos dinámicos. Esta marca es necesaria en todas las versiones anteriores de .NET Framework.  
  
> [!NOTE]
> <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType> se incluye de forma predeterminada en los conjuntos de permisos `FullTrust` y `LocalIntranet`, pero no en el conjunto de permisos `Internet`. Por consiguiente, en versiones anteriores de .NET Framework se puede usar una biblioteca con permisos de Internet, pero solo si ejecuta un <xref:System.Security.PermissionSet.Assert%2A> para <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Estas bibliotecas requieren una revisión cuidadosa de la seguridad porque los errores de codificación pueden provocar vulnerabilidades de seguridad. .NET Framework 2.0 SP1 permite emitir código en escenarios de confianza parcial sin emitir ninguna petición de seguridad, porque la generación de código no es en sí una operación que requiera privilegios. Es decir, el código generado no tiene más permisos que el ensamblado que lo emite. Esto permite que las bibliotecas que emiten código sean transparentes en seguridad y elimina la necesidad de declarar <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, lo que simplifica la tarea de escribir una biblioteca segura.  
  
 Además, .NET Framework 2.0 SP1 presenta la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> para el acceso a los tipos y miembros no públicos desde métodos dinámicos de confianza parcial. Las versiones anteriores de .NET Framework requieren la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> para los métodos dinámicos que acceden a tipos y miembros no públicos; es un permiso que nunca debe concederse al código de confianza parcial.  
  
 Por último, .NET Framework 2.0 SP1 presenta métodos hospedados de forma anónima.  
  
### <a name="obtaining-information-on-types-and-members"></a>Obtener información sobre tipos y miembros  

 A partir de .NET Framework 2.0, no se requieren permisos para obtener información sobre tipos y miembros no públicos. A fin de obtener la información necesaria para emitir métodos dinámicos, se usa la reflexión. Por ejemplo, los objetos <xref:System.Reflection.MethodInfo> se usan para emitir llamadas a métodos. Las versiones anteriores de .NET Framework requieren <xref:System.Security.Permissions.ReflectionPermission> con la marca <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=nameWithType>. Para obtener más información, vea el artículo sobre [consideraciones de seguridad sobre la reflexión](security-considerations-for-reflection.md).  
  
## <a name="see-also"></a>Vea también

- [Consideraciones de seguridad sobre la reflexión](security-considerations-for-reflection.md)
- [Emitir métodos y ensamblados dinámicos](emitting-dynamic-methods-and-assemblies.md)
