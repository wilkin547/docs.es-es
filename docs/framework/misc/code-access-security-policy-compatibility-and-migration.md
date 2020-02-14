---
title: Compatibilidad con la directiva de seguridad de acceso del código y migración
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: 949739b3336a9182eef583cc405e60e09d7ec09d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217159"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a>Compatibilidad con la directiva de seguridad de acceso del código y migración

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

La parte de la Directiva de seguridad de acceso del código (CAS) se ha convertido en obsoleta en el .NET Framework 4. Como resultado, puede encontrar advertencias de compilación y excepciones en tiempo de ejecución si llama a los tipos y miembros obsoletos de la directiva [explícita](#explicit_use) o [implícitamente](#implicit_use) (a través de otros tipos y miembros).

Para los errores y advertencias:

- [Migrar](#migration) a los reemplazos .NET Framework 4 para las llamadas obsoletas.

   \- O bien

- Mediante el [\<NetFx40_LegacySecurityPolicy > elemento de configuración](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) para participar en el comportamiento de la Directiva CAS heredada.

Este tema contiene las siguientes secciones:

- [Uso explícito](#explicit_use)

- [Uso implícito](#implicit_use)

- [Errores y advertencias](#errors_and_warnings)

- [Migración: reemplazo de llamadas obsoletas](#migration)

- [Compatibilidad: uso de la opción heredado de directiva CAS](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a>Uso explícito

Los miembros que manipulan directamente directivas de seguridad o que necesitan la directiva CAS para el espacio aislado están obsoletos y generarán errores de forma predeterminada.

Por ejemplo:

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a>Uso implícito

Cuando varios ensamblados cargan sobrecargas se producen errores debido a su uso implícito de la directiva CAS. Estas sobrecargas toman un parámetro <xref:System.Security.Policy.Evidence> que se usa para resolver la directiva CAS y proporcionar un conjunto de permisos concedidos a un ensamblado.

Estos son algunos ejemplos. Las sobrecargas obsoletas son las que toman <xref:System.Security.Policy.Evidence> como parámetro:

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a>Errores y advertencias

Los tipos y miembros obsoletos generan los siguientes mensajes de error cuando se usan. Tenga en cuenta que el tipo <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> en sí no está obsoleto.

Advertencia en tiempo de compilación:

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

Excepción de tiempo de ejecución:

<xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a>Migración: reemplazo para las llamadas obsoletas

### <a name="determining-an-assemblys-trust-level"></a>Determinar el nivel de confianza de un ensamblado

La directiva CAS suele usarse para determinar el nivel de confianza o el conjunto de permisos concedidos a un ensamblado o dominio de aplicación. El .NET Framework 4 expone las siguientes propiedades útiles que no necesitan resolver la Directiva de seguridad:

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a>Espacio aislado del dominio de aplicación

El método <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> suele usarse para hospedar en un espacio aislado los ensamblados de un dominio de aplicación. El .NET Framework 4 expone los miembros que no tienen que usar <xref:System.Security.Policy.PolicyLevel> para este fin. Para obtener más información, consulte [Cómo: ejecutar código de confianza parcial en un espacio aislado](how-to-run-partially-trusted-code-in-a-sandbox.md).

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a>Determinar el conjunto de permisos seguro o razonable para código de confianza parcial

Los hosts suelen necesitar determinar los permisos adecuados para el código hospedado en espacio aislado. Antes de la .NET Framework 4, la Directiva de CAS proporcionaba una forma de hacerlo con el método <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>. Como reemplazo, .NET Framework 4 proporciona el método <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType>, que devuelve un conjunto de permisos estándar seguro para la evidencia proporcionada.

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a>Escenarios sin espacio aislado: sobrecargas para cargas de ensamblado

La razón para usar una sobrecarga de carga de ensamblado puede ser usar parámetros que de otra forma no están disponibles, en lugar de hospedar el ensamblado en un espacio aislado. A partir de la .NET Framework 4, las sobrecargas de carga de ensamblados que no requieren un objeto <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> como parámetro, por ejemplo, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, habilitan este escenario.

Si quiere hospedar un ensamblado en un espacio aislado, use la sobrecarga <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a>Compatibilidad: usar la opción de directiva CAS heredada

El [\<NetFx40_LegacySecurityPolicy > elemento de configuración](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) permite especificar que un proceso o una biblioteca utiliza una directiva CAS heredada. Cuando se habilita este elemento, las sobrecargas de directiva y de evidencia funcionarán igual que en versiones anteriores de Framework.

> [!NOTE]
> El comportamiento de la directiva CAS es específico de cada versión del tiempo de ejecución y por lo tanto, modificar la directiva CAS para una versión del tiempo de ejecución no afecta a la directiva CAS de otra versión.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Consulte también

- [Cómo: Ejecutar código de confianza parcial en un espacio aislado](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
