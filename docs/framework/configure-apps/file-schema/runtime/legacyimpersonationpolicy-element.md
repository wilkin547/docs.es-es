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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154109"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy> (Elemento)
Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
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
|`enabled`|Atributo necesario.<br /><br /> Especifica que el no <xref:System.Security.Principal.WindowsIdentity> fluye por puntos asincrónicos, independientemente de la <xref:System.Threading.ExecutionContext> configuración de Flow en el subproceso actual.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>fluye a través de puntos asincrónicos en función de la <xref:System.Threading.ExecutionContext> configuración de flujo para el subproceso actual. Este es el valor predeterminado.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>no fluye por puntos asincrónicos, independientemente de la <xref:System.Threading.ExecutionContext> configuración de Flow en el subproceso actual.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En las .NET Framework versiones 1,0 y 1,1, no <xref:System.Security.Principal.WindowsIdentity> fluye por los puntos asincrónicos definidos por el usuario. A partir de la versión .NET Framework 2,0, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso que se está ejecutando actualmente y fluye a través de los puntos asincrónicos dentro de un dominio de aplicación. <xref:System.Security.Principal.WindowsIdentity>Se incluye en este contexto de ejecución y, por tanto, también fluye por los puntos asincrónicos, lo que significa que, si existe un contexto de suplantación, se producirá un flujo también.  
  
 A partir de la .NET Framework 2,0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos.  
  
> [!NOTE]
> El Common Language Runtime (CLR) es consciente de las operaciones de suplantación realizadas con solo código administrado, no de la suplantación realizada fuera del código administrado, como a través de la invocación de plataforma a código no administrado o a través de llamadas directas a funciones de Win32. Solo <xref:System.Security.Principal.WindowsIdentity> los objetos administrados pueden fluir por puntos asincrónicos, a menos que el elemento se haya `alwaysFlowImpersonationPolicy` establecido en true ( `<alwaysFlowImpersonationPolicy enabled="true"/>` ). Al establecer el `alwaysFlowImpersonationPolicy` elemento en true, se especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se haya realizado la suplantación. Para obtener más información sobre cómo fluir la suplantación no administrada a través de puntos asincrónicos, vea [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
 Puede modificar este comportamiento predeterminado de otras dos maneras:  
  
1. En código administrado para cada subproceso.  
  
     Puede suprimir el flujo por subproceso modificando la configuración de y mediante <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> método, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. En la llamada a la interfaz de hospedaje no administrada para cargar el Common Language Runtime (CLR).  
  
     Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la función de [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro de la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.  
  
 Para obtener más información, vea el [ \<alwaysFlowImpersonationPolicy> elemento](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Archivo de configuración  
 En una aplicación .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
 En el caso de una aplicación de ASP.NET, el flujo de suplantación se puede configurar en el archivo Aspnet. config que se encuentra en el \<Windows Folder> directorio \Microsoft.NET\Framework\vx.x.xxxx  
  
 De forma predeterminada, ASP.NET deshabilita el flujo de suplantación en el archivo Aspnet. config con las siguientes opciones de configuración:  
  
``` xml
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
 En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no transmite la identidad de Windows a través de puntos asincrónicos.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [\<alwaysFlowImpersonationPolicy>Element](alwaysflowimpersonationpolicy-element.md)
