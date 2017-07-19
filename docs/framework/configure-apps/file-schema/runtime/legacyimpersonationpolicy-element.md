---
title: "&lt;legacyImpersonationPolicy&gt; (Elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<legacyImpersonationPolicy> (elemento)"
  - "legacyImpersonationPolicy (elemento)"
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# &lt;legacyImpersonationPolicy&gt; (Elemento)
Especifica que la identidad de Windows no pasa por puntos asincrónicos, sin tener en cuenta la configuración de flujo para el contexto de ejecución del subproceso actual.  
  
## Sintaxis  
  
```  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que <xref:System.Security.Principal.WindowsIdentity> no fluye por los puntos asincrónicos, sin tener en cuenta la configuración de flujo del <xref:System.Threading.ExecutionContext> del subproceso actual.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> fluye por puntos asincrónicos que dependen de la configuración de flujo de <xref:System.Threading.ExecutionContext> para el subproceso actual.  Éste es el valor predeterminado.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> no fluye por los puntos asincrónicos, sin tener en cuenta la configuración de flujo de <xref:System.Threading.ExecutionContext> en el subproceso actual.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 En las versiones 1.0 y 1.1 de .NET Framework, <xref:System.Security.Principal.WindowsIdentity> no fluye por ningún punto asincrónico definido por el usuario.  En la versión 2.0 de .NET Framework, hay un objeto <xref:System.Threading.ExecutionContext> que contiene información sobre el subproceso que se está ejecutando y lo hace fluir por los puntos asincrónicos de un dominio de aplicación.  <xref:System.Security.Principal.WindowsIdentity> también fluye como parte de la información que pasa por los puntos asincrónicos, lo que significa que si existe un contexto de suplantación, también fluirá.  Este elemento se utiliza para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye por los puntos asincrónicos.  
  
> [!NOTE]
>  Common Language Runtime \(CLR\) tiene en cuenta las operaciones de suplantación realizadas sólo con código administrado, no de suplantación realizada fuera del código administrado, como por ejemplo mediante la invocación de plataforma a código no administrado o mediante llamadas directas a funciones de Win32.  Sólo los objetos <xref:System.Security.Principal.WindowsIdentity> administrados pueden fluir por los puntos asincrónicos, a menos que el elemento `alwaysFlowImpersonationPolicy` se haya establecido en verdadero \(`<alwaysFlowImpersonationPolicy enabled="true"/>`\).  Establecer el elemento `alwaysFlowImpersonationPolicy` en verdadero especifica que la identidad de Windows siempre fluye por los puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación.  Para obtener más información sobre suplantación no administrada que fluye por puntos asincrónicos, vea [\<alwaysFlowImpersonationPolicy\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Este elemento sólo puede utilizarse en el archivo de configuración de la aplicación.  
  
 Puede modificar este comportamiento predeterminado de otras dos maneras:  
  
1.  En código administrado, subproceso a subproceso.  
  
     Puede suprimir el flujo subproceso a subproceso modificando la configuración de <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext> utilizando el método <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName>.  
  
2.  En la llamada a la interfaz de hospedaje no administrada para cargar Common Language Runtime \(CLR\).  
  
     Si se utiliza una interfaz de hospedaje no administrada \(en lugar de un ejecutable simple administrado\) para cargar el CLR, puede especificar un marcador especial en la llamada a la función [CorBindToRuntimeEx \(Función\)](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).  Para habilitar el modo de compatibilidad para todo proceso, establezca el parámetro `flags` de [CorBindToRuntimeEx \(Función\)](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP\_LEGACY\_IMPERSONATION.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo especificar el comportamiento heredado que no hace fluir la identidad de Windows por los puntos asincrónicos.  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)