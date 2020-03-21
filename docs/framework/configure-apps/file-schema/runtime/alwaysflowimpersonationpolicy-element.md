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
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154488"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy> Element
Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
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
|`enabled`|Atributo necesario.<br /><br /> Indica si la identidad de Windows fluye a través de puntos asincrónicos.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|La identidad de Windows no fluye a través de puntos <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>asincrónicos, a menos que la suplantación se realice a través de métodos administrados como . Este es el valor predeterminado.|  
|`true`|La identidad de Windows siempre fluye a través de puntos asincrónicos, independientemente de cómo se realizó la suplantación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  
 En las versiones 1.0 y 1.1 de .NET Framework, la identidad de Windows no fluye entre puntos asincrónicos. En la versión 2.0 de <xref:System.Threading.ExecutionContext> .NET Framework, hay un objeto que contiene información sobre el subproceso que se está ejecutando actualmente y lo fluye a través de puntos asincrónicos dentro de un dominio de aplicación. También <xref:System.Security.Principal.WindowsIdentity> fluye como parte de la información que fluye a través de los puntos asincrónicos, siempre que la suplantación se logra mediante métodos administrados como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> y no a través de otros medios, como la invocación de plataforma a métodos nativos. Este elemento se utiliza para especificar que la identidad de Windows fluye a través de puntos asincrónicos, independientemente de cómo se logró la suplantación.  
  
 Puede modificar este comportamiento predeterminado de otras dos maneras:  
  
1. En código administrado por subproceso.  
  
     Puede suprimir el flujo por subproceso modificando <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> la configuración <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>y <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>mediante <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> el método , , o .  
  
2. En la llamada a la interfaz de hospedaje no administrada para cargar Common Language Runtime (CLR).  
  
     Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la [función Función CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Para habilitar el modo de compatibilidad para `flags` todo el proceso, establezca `STARTUP_ALWAYSFLOW_IMPERSONATION`el parámetro [corBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en .  
  
## <a name="configuration-file"></a>Archivo de configuración  
 En una aplicación de .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
 Para una aplicación ASP.NET, el flujo de suplantación se puede \<configurar en el archivo aspnet.config que se encuentra en el directorio de carpetas de Windows>.  
  
 ASP.NET deshabilita de forma predeterminada el flujo de suplantación en el archivo aspnet.config mediante los siguientes valores de configuración:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe utilizar explícitamente los siguientes valores de configuración:  
  
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
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
- [\<legacyImpersonationPolicy> Element](legacyimpersonationpolicy-element.md)
