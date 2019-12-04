---
title: Elemento <applicationPool> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 9783844ff0fe719b0581c1c9e1fb96eb31933b89
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801872"
---
# <a name="applicationpool-element-web-settings"></a>Elemento \<applicationPool > (configuración Web)
Especifica los valores de configuración que usa ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación ASP.NET se ejecuta en modo integrado en IIS 7,0 o una versión posterior.  
  
> [!IMPORTANT]
> Este elemento y la característica que admite solo funcionan si la aplicación ASP.NET se hospeda en IIS 7,0 o versiones posteriores.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. Web >** ](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<applicationPool >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Especifica cuántas solicitudes simultáneas ASP.NET permite por CPU.|  
|`maxConcurrentThreadsPerCPU`|Especifica el número de subprocesos simultáneos que se pueden ejecutar para un grupo de aplicaciones para cada CPU. Esto proporciona una manera alternativa de controlar la simultaneidad de ASP.NET, ya que puede limitar el número de subprocesos administrados que se pueden usar por CPU para atender las solicitudes. De forma predeterminada, este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos de CLR también limita el número de subprocesos que se pueden crear.|  
|`requestQueueLimit`|Especifica el número máximo de solicitudes que se pueden poner en cola para ASP.NET en un único proceso. Cuando dos o más aplicaciones ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación en el grupo de aplicaciones está sujeto a esta configuración.|  
  
### <a name="child-elements"></a>Elemento secundario  
 Ninguna.  
  
### <a name="parent-elements"></a>Elemento principal  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Contiene información sobre cómo interactúa ASP.NET con una aplicación host.|  
  
## <a name="remarks"></a>Notas  

Al ejecutar IIS 7,0 o una versión posterior en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y pone en cola las solicitudes cuando la aplicación se hospeda en un grupo de aplicaciones de IIS. Si ejecuta IIS 6 o ejecuta IIS 7,0 en modo clásico o en modo ISAPI, se omite esta configuración.  
  
La configuración de `applicationPool` se aplica a todos los grupos de aplicaciones que se ejecutan en una versión determinada de la .NET Framework. La configuración se encuentra en un archivo Aspnet. config. Hay una versión de este archivo para las versiones 2,0 y 4,0 del .NET Framework. (Las versiones 3,0 y 3,5 del .NET Framework compartir el archivo Aspnet. config con la versión 2,0).  
  
> [!IMPORTANT]
> Si ejecuta IIS 7,0 en Windows 7, puede configurar un archivo Aspnet. config independiente para cada grupo de aplicaciones. Esto le permite adaptar el rendimiento de los subprocesos de cada grupo de aplicaciones.  
  
En el caso de la configuración `maxConcurrentRequestsPerCPU`, el valor predeterminado de "5000" en el .NET Framework 4 desactiva eficazmente la limitación de solicitudes controlada por ASP.NET, a menos que realmente tenga 5000 o más solicitudes por CPU. La configuración predeterminada depende en su lugar del grupo de subprocesos de CLR para administrar automáticamente la simultaneidad por CPU. Las aplicaciones que hacen un uso intensivo del procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en e/s de red, se beneficiarán del aumento del límite predeterminado en el .NET Framework 4. Si se establece `maxConcurrentRequestsPerCPU` en cero, se desactiva el uso de subprocesos administrados para procesar solicitudes ASP.NET. Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de e/s de IIS y, por lo tanto, la simultaneidad se limita mediante la configuración del subproceso de IIS.  
  
La configuración `requestQueueLimit` funciona de la misma manera que el atributo `requestQueueLimit` del elemento [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , que se establece en los archivos Web. config para las aplicaciones de ASP.net. Sin embargo, el valor de `requestQueueLimit` en un archivo Aspnet. config invalida el valor de `requestQueueLimit` en un archivo Web. config. En otras palabras, si se establecen ambos atributos (de forma predeterminada, es true), el valor de `requestQueueLimit` en el archivo Aspnet. config tiene prioridad.  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo Aspnet. config en las siguientes circunstancias:  
  
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
  
## <a name="element-information"></a>Información del elemento  
  
|||  
|-|-|  
|Espacio de nombres||  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Vea también

- [Elemento \<system.web> (configuración web)](system-web-element-web-settings.md)
