---
title: Elemento <applicationPool> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 963b25e57ae8c2cc59dcc3e50ae2a52cc04f54a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185644"
---
# <a name="applicationpool-element-web-settings"></a>Elemento \<applicationPool> (configuración web)

Especifica los valores de configuración que usa ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación ASP.NET se ejecuta en modo integrado en IIS 7,0 o una versión posterior.  
  
> [!IMPORTANT]
> Este elemento y la característica que admite solo funcionan si la aplicación ASP.NET se hospeda en IIS 7,0 o versiones posteriores.  
  
[**\<configuration>**](../configuration-element.md)  
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
|`maxConcurrentThreadsPerCPU`|Especifica el número de subprocesos simultáneos que se pueden ejecutar para un grupo de aplicaciones para cada CPU. Esto proporciona una manera alternativa de controlar la simultaneidad de ASP.NET, ya que puede limitar el número de subprocesos administrados que se pueden usar por CPU para atender las solicitudes. De forma predeterminada, este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos de CLR también limita el número de subprocesos que se pueden crear.|  
|`requestQueueLimit`|Especifica el número máximo de solicitudes que se pueden poner en cola para ASP.NET en un único proceso. Cuando dos o más aplicaciones ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación en el grupo de aplicaciones está sujeto a esta configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Contiene información sobre cómo interactúa ASP.NET con una aplicación host.|  
  
## <a name="remarks"></a>Observaciones  

Al ejecutar IIS 7,0 o una versión posterior en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y pone en cola las solicitudes cuando la aplicación se hospeda en un grupo de aplicaciones de IIS. Si ejecuta IIS 6 o ejecuta IIS 7,0 en modo clásico o en modo ISAPI, se omite esta configuración.  
  
La `applicationPool` configuración se aplica a todos los grupos de aplicaciones que se ejecutan en una versión determinada del .NET Framework. La configuración se encuentra en un archivo de aspnet.config. Hay una versión de este archivo para las versiones 2,0 y 4,0 del .NET Framework. (Las versiones 3,0 y 3,5 del .NET Framework compartir el archivo de aspnet.config con la versión 2,0).  
  
> [!IMPORTANT]
> Si ejecuta IIS 7,0 en Windows 7, puede configurar un archivo de aspnet.config independiente para cada grupo de aplicaciones. Esto le permite adaptar el rendimiento de los subprocesos de cada grupo de aplicaciones.  
  
En el caso de la `maxConcurrentRequestsPerCPU` configuración, el valor predeterminado de "5000" en el .NET Framework 4 desactiva eficazmente la limitación de solicitudes que está controlada por ASP.net, a menos que tenga en realidad 5000 o más solicitudes por CPU. La configuración predeterminada depende en su lugar del grupo de subprocesos de CLR para administrar automáticamente la simultaneidad por CPU. Las aplicaciones que hacen un uso intensivo del procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en e/s de red, se beneficiarán del aumento del límite predeterminado en el .NET Framework 4. Si `maxConcurrentRequestsPerCPU` se establece en cero, se desactiva el uso de subprocesos administrados para procesar solicitudes ASP.net. Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de e/s de IIS y, por lo tanto, la simultaneidad se limita mediante la configuración del subproceso de IIS.  
  
La `requestQueueLimit` configuración funciona de la misma manera que el `requestQueueLimit` atributo del elemento [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , que se establece en la Web.config archivos para las aplicaciones ASP.net. Sin embargo, la `requestQueueLimit` configuración de un archivo de aspnet.config invalida la `requestQueueLimit` configuración de un archivo de Web.config. En otras palabras, si se establecen ambos atributos (de forma predeterminada, es true), la `requestQueueLimit` configuración del archivo aspnet.config tiene prioridad.  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo aspnet.config en las siguientes circunstancias:  
  
- La aplicación se hospeda en un grupo de aplicaciones de IIS 7,0.  
  
- IIS 7,0 se está ejecutando en modo integrado.  
  
- La aplicación está usando .NET Framework 3,5 SP1 o una versión posterior.  
  
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

- [\<system.web> (Elemento, configuración Web)](system-web-element-web-settings.md)
