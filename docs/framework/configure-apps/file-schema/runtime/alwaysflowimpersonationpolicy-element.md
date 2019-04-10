---
title: <alwaysFlowImpersonationPolicy> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec411039363cfb118fee06dff88daf50bbc97a86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314781"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy > elemento
Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.  
  
 \<configuration>  
\<runtime>  
\<alwaysFlowImpersonationPolicy>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si la identidad de Windows fluye por puntos asincrónicos.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La identidad no fluye por puntos asincrónicos, a menos que la suplantación se realiza a través de Windows administrado métodos como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>. Este es el valor predeterminado.|  
|`true`|La identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En las versiones 1.0 y 1.1 de .NET Framework, la identidad de Windows no fluye por puntos asincrónicos. En la versión 2.0 de .NET Framework, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso actualmente en ejecución y hace que fluya por puntos asincrónicos dentro de un dominio de aplicación. El <xref:System.Security.Principal.WindowsIdentity> también flujos como parte de la información que fluye a través de los puntos asincrónicos, siempre que la suplantación se logra mediante métodos administran como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> y no a través de otros medios como plataforma de invocación a métodos nativos. Este elemento se utiliza para especificar que la identidad de Windows fluye por puntos asincrónicos, independientemente de cómo se logró la suplantación.  
  
 Puede modificar este comportamiento predeterminado de dos formas:  
  
1. En el código administrado en una base por subproceso.  
  
     Puede suprimir el flujo por subproceso modificando el <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext> valores mediante el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> método.  
  
2. En la llamada a la interfaz de hospedaje no administrada para cargar common language runtime (CLR).  
  
     Si una interfaz de hospedaje no administrada (en lugar de un ejecutable simple administrado) se usa para cargar el CLR, puede especificar un marcador especial en la llamada a la [función CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) función. Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) a `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 En una aplicación de .NET Framework, este elemento se puede usar solo en el archivo de configuración de la aplicación.  
  
 Para una aplicación ASP.NET, el flujo de suplantación puede configurarse en el archivo aspnet.config se encuentra en la \<carpeta de Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.  
  
 ASP.NET de forma predeterminada, se deshabilita el flujo de suplantación en el archivo aspnet.config mediante el uso de las opciones de configuración siguientes:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe usar explícitamente la configuración siguiente:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar que la identidad de Windows fluye por puntos asincrónicos, incluso cuando la suplantación se logra a través de otros medios distintos métodos administrados.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<legacyImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
