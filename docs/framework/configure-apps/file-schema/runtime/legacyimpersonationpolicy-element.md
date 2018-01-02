---
title: '&lt;legacyImpersonationPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caeede11d8128af00beb5b1b3426e8c4a5406520
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a>&lt;legacyImpersonationPolicy&gt; elemento
Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<legacyImpersonationPolicy >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que la <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos, sin tener en cuenta el <xref:System.Threading.ExecutionContext> flujo de configuración en el subproceso actual.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>fluye por puntos asincrónicos según el <xref:System.Threading.ExecutionContext> flujo de configuración para el subproceso actual. Este es el valor predeterminado.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>no fluye por puntos asincrónicos, sin tener en cuenta el <xref:System.Threading.ExecutionContext> flujo de configuración en el subproceso actual.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En las versiones de .NET Framework 1.0 y 1.1, la <xref:System.Security.Principal.WindowsIdentity> no fluye por ningún punto asincrónico definido por el usuario. A partir de la versión 2.0 de .NET Framework, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso actualmente en ejecución y fluye por puntos asincrónicos dentro de un dominio de aplicación. El <xref:System.Security.Principal.WindowsIdentity> se incluye en este contexto de ejecución y, por tanto, también fluye por los puntos asincrónicos, lo que significa que si existe un contexto de suplantación, se desplazarán así.  
  
 A partir de .NET Framework 2.0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos.  
  
> [!NOTE]
>  Common language runtime (CLR) es consciente de suplantación invocación de operaciones realizadas sólo con código administrado, no de suplantación realizada fuera del código administrado, como a través de la plataforma a código no administrado o mediante llamadas directas a funciones de Win32. Solo se ocupaba de <xref:System.Security.Principal.WindowsIdentity> objetos pueden fluir por puntos asincrónicos, a menos que la `alwaysFlowImpersonationPolicy` elemento se ha establecido en true (`<alwaysFlowImpersonationPolicy enabled="true"/>`). Establecer el `alwaysFlowImpersonationPolicy` elemento a true especifica que la identidad de Windows siempre fluye por puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación. Para obtener más información en la que fluyen suplantación no administrada por puntos asincrónicos, vea [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Puede modificar este comportamiento predeterminado de dos formas:  
  
1.  En el código administrado en una base por subproceso.  
  
     Puede suprimir el flujo por subproceso modificando la <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext> configuración mediante el uso de la <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> método.  
  
2.  En la llamada a la interfaz de hospedaje no administrada para cargar common language runtime (CLR).  
  
     Si una interfaz de hospedaje no administrada (en lugar de un simple archivo ejecutable administrado) se usa para cargar CLR, puede especificar una marca especial en la llamada a la [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (función). Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.  
  
 Para obtener más información, consulte el [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Archivo de configuración  
 En una aplicación de .NET Framework, este elemento se puede usar únicamente en el archivo de configuración de aplicación.  
  
 Para una aplicación ASP.NET, se puede configurar el flujo de suplantación en el archivo aspnet.config se encuentra en la \<carpeta Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.  
  
 ASP.NET de forma predeterminada, se deshabilita el flujo de suplantación en el archivo aspnet.config mediante las siguientes opciones de configuración:  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe utilizar explícitamente los valores de configuración siguientes:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no fluye la identidad de Windows por puntos asincrónicos.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
