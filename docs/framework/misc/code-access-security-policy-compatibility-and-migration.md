---
title: "Code Access Security Policy Compatibility and Migration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "policy migration, compatibility"
  - "CLR poliicy migration"
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Code Access Security Policy Compatibility and Migration
La parte de la directiva de seguridad de acceso del código \(CAS\) se ha quedado obsoleta en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].  Como resultado, puede encontrar advertencias de compilación y excepciones en tiempo de ejecución si se llama a los tipos y miembros obsoletos de la directiva [explícita](#explicit_use) o [implícitamente](#implicit_use) \(a través de otros tipos y miembros\).  
  
 Para los errores y advertencias:  
  
-   [Migre](#migration) a los sustitutos de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] para las llamadas obsoletas.  
  
     o bien  
  
-   Use el [elemento de configuración \<NetFx40\_LegacySecurityPolicy\>](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) para participar en el comportamiento de la directiva CAS heredada.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Uso explícito](#explicit_use)  
  
-   [Uso implícito](#implicit_use)  
  
-   [Errores y advertencias](#errors_and_warnings)  
  
-   [Migración: reemplazo para las llamadas obsoletas](#migration)  
  
-   [Compatibilidad: usar la opción de directiva CAS heredada](#compatibility)  
  
> [!CAUTION]
>  Seguridad de acceso del código y código de confianza parcial  
>   
>  .NET Framework proporciona seguridad de acceso del código \(CAS\), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.  La seguridad de acceso del código en .NET Framework no debe usarse como límite de seguridad para código de confianza parcial, especialmente si se trata de código de origen desconocido.  Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.  
>   
>  Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.  
  
<a name="explicit_use"></a>   
## Uso explícito  
 Los miembros que manipulan directamente directivas de seguridad o que necesitan la directiva CAS para el espacio aislado están obsoletos y generarán errores de forma predeterminada.  
  
 Algunos ejemplos son:  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=fullName>  
  
<a name="implicit_use"></a>   
## Uso implícito  
 Cuando varios ensamblados cargan sobrecargas se producen errores debido a su uso implícito de la directiva CAS.  Estas sobrecargas toman un parámetro <xref:System.Security.Policy.Evidence> que se usa para resolver la directiva CAS y proporcionar un conjunto de permisos concedidos a un ensamblado.  
  
 Estos son algunos ejemplos:  Las sobrecargas obsoletas son las que toman <xref:System.Security.Policy.Evidence> como parámetro:  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
<a name="errors_and_warnings"></a>   
## Errores y advertencias  
 Los tipos y miembros obsoletos generan los siguientes mensajes de error cuando se usan.  Tenga en cuenta que el tipo <xref:System.Security.Policy.Evidence?displayProperty=fullName> en sí no está obsoleto.  
  
 Advertencia en tiempo de compilación:  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework.  Please use <suggested alternate API>.  See <link> for more information.'`  
  
 Excepción de tiempo de ejecución:  
  
 <xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`  
  
<a name="migration"></a>   
## Migración: reemplazo para las llamadas obsoletas  
  
### Determinar el nivel de confianza de un ensamblado  
 La directiva CAS suele usarse para determinar el nivel de confianza o el conjunto de permisos concedidos a un ensamblado o dominio de aplicación.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] expone las siguientes propiedades útiles que no necesitan resolver la directiva de seguridad:  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=fullName>  
  
### Espacio aislado del dominio de aplicación  
 El método <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName> suele usarse para hospedar en un espacio aislado los ensamblados de un dominio de aplicación.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] expone miembros que no tienen que usar <xref:System.Security.Policy.PolicyLevel> con este fin. Para obtener más información, consulte [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
### Determinar el conjunto de permisos seguro o razonable para código de confianza parcial  
 Los hosts suelen necesitar determinar los permisos adecuados para el código hospedado en espacio aislado.  Antes de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], la directiva CAS proporcionaba una manera de hacerlo con el método <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName>.  Como reemplazo, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] proporciona el método <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName>, que devuelve un conjunto de permisos estándar y seguro para la evidencia proporcionada.  
  
### Escenarios sin espacio aislado: sobrecargas para cargas de ensamblado  
 La razón para usar una sobrecarga de carga de ensamblado puede ser usar parámetros que de otra forma no están disponibles, en lugar de hospedar el ensamblado en un espacio aislado.  A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], las sobrecargas de carga de ensamblado que no requieren un objeto <xref:System.Security.Policy.Evidence?displayProperty=fullName> como parámetro, por ejemplo, [AppDomain.ExecuteAssembly\(String, String\[\], Byte\<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=fullName>, habilitan este escenario.  
  
 Si quiere hospedar un ensamblado en un espacio aislado, use la sobrecarga [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName>.  
  
<a name="compatibility"></a>   
## Compatibilidad: usar la opción de directiva CAS heredada  
 El elemento de configuración [\<NetFx40\_LegacySecurityPolicy\>](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) permite especificar que un proceso o una biblioteca usa la directiva CAS heredada.  Cuando se habilita este elemento, las sobrecargas de directiva y de evidencia funcionarán igual que en versiones anteriores de Framework.  
  
> [!NOTE]
>  El comportamiento de la directiva CAS es específico de cada versión del tiempo de ejecución y por lo tanto, modificar la directiva CAS para una versión del tiempo de ejecución no afecta a la directiva CAS de otra versión.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)