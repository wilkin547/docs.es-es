---
title: <legacyImpersonationPolicy> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154109"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy> Element
Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica que <xref:System.Security.Principal.WindowsIdentity> no fluye a través de <xref:System.Threading.ExecutionContext> puntos asincrónicos, independientemente de la configuración de flujo en el subproceso actual.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>fluye a través de <xref:System.Threading.ExecutionContext> puntos asincrónicos dependiendo de la configuración de flujo para el subproceso actual. Este es el valor predeterminado.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>no fluye a través de <xref:System.Threading.ExecutionContext> puntos asincrónicos, independientemente de la configuración de flujo en el subproceso actual.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  
 En las versiones 1.0 y 1.1 de .NET Framework, <xref:System.Security.Principal.WindowsIdentity> no fluye a través de ningún punto asincrónico definido por el usuario. A partir de la versión 2.0 <xref:System.Threading.ExecutionContext> de .NET Framework, hay un objeto que contiene información sobre el subproceso que se está ejecutando actualmente y fluye a través de puntos asincrónicos dentro de un dominio de aplicación. Se <xref:System.Security.Principal.WindowsIdentity> incluye en este contexto de ejecución y, por lo tanto, también fluye a través de los puntos asincrónicos, lo que significa que si existe un contexto de suplantación, también fluirá.  
  
 A partir de .NET Framework 2.0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye a través de puntos asincrónicos.  
  
> [!NOTE]
> Common Language Runtime (CLR) es consciente de las operaciones de suplantación realizadas solo con código administrado, no de la suplantación realizada fuera del código administrado, como a través de la invocación de plataforma en código no administrado o mediante llamadas directas a funciones Win32. Solo <xref:System.Security.Principal.WindowsIdentity> los objetos administrados pueden `alwaysFlowImpersonationPolicy` fluir a través`<alwaysFlowImpersonationPolicy enabled="true"/>`de puntos asincrónicos, a menos que el elemento se haya establecido en true ( ). Establecer `alwaysFlowImpersonationPolicy` el elemento en true especifica que la identidad de Windows siempre fluye a través de puntos asincrónicos, independientemente de cómo se realizó la suplantación. Para obtener más información sobre el flujo de suplantación no administrada entre puntos asincrónicos, vea [ \<AlwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
 Puede modificar este comportamiento predeterminado de otras dos maneras:  
  
1. En código administrado por subproceso.  
  
     Puede suprimir el flujo por subproceso modificando <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> la configuración <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>y <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> mediante el método , o .  
  
2. En la llamada a la interfaz de hospedaje no administrada para cargar Common Language Runtime (CLR).  
  
     Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la [función Función CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Para habilitar el modo de compatibilidad para `flags` todo el proceso, establezca el parámetro para [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.  
  
 Para obtener más información, vea [ \<el elemento alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Archivo de configuración  
 En una aplicación de .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
 Para una aplicación ASP.NET, el flujo de suplantación se puede \<configurar en el archivo aspnet.config que se encuentra en el directorio de carpetas de Windows>.  
  
 ASP.NET deshabilita de forma predeterminada el flujo de suplantación en el archivo aspnet.config mediante los siguientes valores de configuración:  
  
``` xml
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
 En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no fluye la identidad de Windows a través de puntos asincrónicos.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
- [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md)
