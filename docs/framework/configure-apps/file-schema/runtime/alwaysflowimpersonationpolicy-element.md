---
title: <alwaysFlowImpersonationPolicy> (Elemento)
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
ms.openlocfilehash: 164492eb1abc7329481f158963118b47d2c4aebc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252860"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy >, elemento
Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy>** \  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si la identidad de Windows fluye a través de puntos asincrónicos.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`false`|La identidad de Windows no fluye por puntos asincrónicos, a menos que la suplantación se realice a través de <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>métodos administrados como. Este es el valor predeterminado.|  
|`true`|La identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se haya realizado la suplantación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En las versiones 1,0 y 1,1 de .NET Framework, la identidad de Windows no fluye a través de los puntos asincrónicos. En la versión .NET Framework 2,0, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso que se está ejecutando actualmente y lo transmite por puntos asincrónicos dentro de un dominio de aplicación. También fluye como parte de la información que fluye a través de los puntos asincrónicos, siempre que la suplantación se logra utilizando métodos administrados <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> como y no a través de otros medios, como la invocación de plataforma a métodos nativos. <xref:System.Security.Principal.WindowsIdentity> Este elemento se usa para especificar que la identidad de Windows se transmite por puntos asincrónicos, independientemente de cómo se haya conseguido la suplantación.  
  
 Puede modificar este comportamiento predeterminado de otras dos maneras:  
  
1. En código administrado para cada subproceso.  
  
     Puede suprimir el flujo por subproceso <xref:System.Threading.ExecutionContext> modificando la configuración de y <xref:System.Security.SecurityContext> mediante el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>método, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. En la llamada a la interfaz de hospedaje no administrada para cargar el Common Language Runtime (CLR).  
  
     Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la función de [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Para habilitar el modo de compatibilidad para todo el proceso, establezca `flags` el parámetro de la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 En una aplicación .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
 En el caso de una aplicación ASP.net, el flujo de suplantación se puede configurar en el archivo Aspnet. \<config que se encuentra en la carpeta Windows > directorio \Microsoft.NET\Framework\vx.x.xxxx  
  
 De forma predeterminada, ASP.NET deshabilita el flujo de suplantación en el archivo Aspnet. config con las siguientes opciones de configuración:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe usar explícitamente las siguientes opciones de configuración:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que la identidad de Windows fluye a través de puntos asincrónicos, incluso cuando la suplantación se logra a través de medios distintos de los métodos administrados.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [\<legacyImpersonationPolicy >, elemento](legacyimpersonationpolicy-element.md)
