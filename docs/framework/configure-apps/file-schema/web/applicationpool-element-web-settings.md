---
title: Elemento <applicationPool> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152859"
---
# <a name="applicationpool-element-web-settings"></a>\<Elemento applicationPool> (configuración web)
Especifica los valores de configuración que usa ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación de ASP.NET se ejecuta en modo integrado en IIS 7.0 o una versión posterior.  
  
> [!IMPORTANT]
> Este elemento y la característica que admite solo funcionan si la aplicación ASP.NET se hospeda en IIS 7.0 o versiones posteriores.  
  
[**\<configuración>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Especifica cuántas solicitudes simultáneas ASP.NET permite por CPU.|  
|`maxConcurrentThreadsPerCPU`|Especifica cuántos subprocesos simultáneos se pueden ejecutar para un grupo de aplicaciones para cada CPU. Esto proporciona una forma alternativa de controlar ASP.NET simultaneidad, ya que puede limitar el número de subprocesos administrados que se pueden usar por CPU para atender solicitudes. De forma predeterminada, esta configuración es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos CLR también limita el número de subprocesos que se pueden crear.|  
|`requestQueueLimit`|Especifica el número máximo de solicitudes que se pueden poner en cola para ASP.NET en un único proceso. Cuando dos o más aplicaciones ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación del grupo de aplicaciones está sujeto a esta configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Contiene información sobre cómo ASP.NET interactúa con una aplicación host.|  
  
## <a name="remarks"></a>Observaciones  

Al ejecutar IIS 7.0 o una versión posterior en modo integrado, esta combinación de elementos le permite configurar cómo ASP.NET administra las solicitudes de subprocesos y colas cuando la aplicación se hospeda en un grupo de aplicaciones IIS. Si ejecuta IIS 6 o ejecuta IIS 7.0 en modo clásico o en modo ISAPI, se omite esta configuración.  
  
La `applicationPool` configuración se aplica a todos los grupos de aplicaciones que se ejecutan en una versión determinada de .NET Framework. La configuración se encuentra en un archivo aspnet.config. Hay una versión de este archivo para las versiones 2.0 y 4.0 de .NET Framework. (Las versiones 3.0 y 3.5 de .NET Framework comparten el archivo aspnet.config con la versión 2.0.)  
  
> [!IMPORTANT]
> Si ejecuta IIS 7.0 en Windows 7, puede configurar un archivo aspnet.config independiente para cada grupo de aplicaciones. Esto le permite adaptar el rendimiento de los subprocesos para cada grupo de aplicaciones.  
  
Para `maxConcurrentRequestsPerCPU` la configuración, la configuración predeterminada de "5000" en .NET Framework 4 desactiva eficazmente la limitación de solicitudes controlada por ASP.NET, a menos que realmente tenga 5000 o más solicitudes por CPU. La configuración predeterminada depende en su lugar del grupo de subprocesos CLR para administrar automáticamente la simultaneidad por CPU. Las aplicaciones que hacen un uso extensivo del procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en E/S de red, se beneficiarán del aumento del límite predeterminado en .NET Framework 4. Establecer `maxConcurrentRequestsPerCPU` en cero desactiva el uso de subprocesos administrados para procesar solicitudes ASP.NET. Cuando una aplicación se ejecuta en un grupo de aplicaciones IIS, las solicitudes permanecen en el subproceso de E/S de IIS y, por lo tanto, la configuración del subproceso de IIS limita la simultaneidad.  
  
La `requestQueueLimit` configuración funciona de `requestQueueLimit` la misma manera que el atributo del elemento [processModel,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) que se establece en los archivos Web.config para ASP.NET aplicaciones. Sin `requestQueueLimit` embargo, la configuración de un `requestQueueLimit` archivo aspnet.config reemplaza la configuración de un archivo Web.config. En otras palabras, si se establecen ambos atributos (de forma predeterminada, esto es true), la configuración del `requestQueueLimit` archivo aspnet.config tiene prioridad.  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo configurar ASP.NET comportamiento de todo el proceso en el archivo aspnet.config en las siguientes circunstancias:  
  
- La aplicación se hospeda en un grupo de aplicaciones iIS 7.0.  
  
- IIS 7.0 se ejecuta en modo integrado.  
  
- La aplicación usa .NET Framework 3.5 SP1 o una versión posterior.  
  
Los valores del ejemplo son los valores predeterminados.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres||  
|Nombre del esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Consulte también

- [\<system.web> Element (Configuración web)](system-web-element-web-settings.md)
