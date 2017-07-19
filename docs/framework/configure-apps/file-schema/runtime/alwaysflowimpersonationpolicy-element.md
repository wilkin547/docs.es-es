---
title: "&lt;alwaysFlowImpersonationPolicy&gt; (Elemento) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<alwaysFlowImpersonationPolicy> (elemento)"
  - "alwaysFlowImpersonationPolicy (elemento)"
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;alwaysFlowImpersonationPolicy&gt; (Elemento)
Especifica que la identidad de Windows siempre fluye por los puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación.  
  
## Sintaxis  
  
```  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si la identidad de Windows fluye por los puntos asincrónicos.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La identidad de Windows no fluye por los puntos asincrónicos, a menos que la suplantación se realice a través de métodos administrados, como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.  Éste es el valor predeterminado.|  
|`true`|La identidad de Windows siempre fluye por los puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 En las versiones 1.0 y 1.1 de .NET Framework, la identidad de Windows no fluye por los puntos asincrónicos.  En la versión 2.0 de .NET Framework, hay un objeto <xref:System.Threading.ExecutionContext> que contiene información sobre el subproceso que se está ejecutando y lo hace fluir por los puntos asincrónicos de un dominio de aplicación.  La <xref:System.Security.Principal.WindowsIdentity> también fluye como parte de la información que pasa por los puntos asincrónicos, siempre que se consiguiera la suplantación mediante métodos administrados como, por ejemplo, <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> y no a través de invocaciones de plataforma a métodos nativos.  Este elemento se utiliza para especificar que la identidad de Windows fluye por los puntos asincrónicos, independientemente de cómo se logró la suplantación.  
  
 Puede modificar este comportamiento predeterminado de otras dos maneras:  
  
1.  En código administrado, subproceso a subproceso.  
  
     Puede suprimir el flujo subproceso a subproceso modificando la configuración de <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext>, utilizando el método <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName>.  
  
2.  En la llamada a la interfaz de hospedaje no administrada para cargar Common Language Runtime \(CLR\).  
  
     Si se utiliza una interfaz de hospedaje no administrada \(en lugar de un ejecutable simple administrado\) para cargar el CLR, puede especificar un marcador especial en la llamada a la función [CorBindToRuntimeEx \(Función\)](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).  Para habilitar el modo de compatibilidad para todo proceso, establezca el parámetro `flags` de [CorBindToRuntimeEx \(Función\)](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP\_ALWAYSFLOW\_IMPERSONATION.  
  
## Archivo de configuración  
 Este elemento sólo puede utilizarse en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo especificar que la identidad de Windows fluye por los puntos asincrónicos, incluso aunque la suplantación se logre por medios distintos a los métodos administrados.  
  
```  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<legacyImpersonationPolicy\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)