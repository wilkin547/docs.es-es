---
title: "&lt;applicationPool&gt; elemento (configuración Web)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d75e9eedf42523301b3c1745c05d90bcdafbdbf5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;applicationPool&gt; elemento (configuración Web)
Especifica la configuración que usa ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación ASP.NET se ejecuta en modo integrado en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior.  
  
> [!IMPORTANT]
>  Este elemento y la característica que admite solo funcionan si la aplicación ASP.NET se hospeda en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores.  
  
 \<configuration>  
\<System.Web > elemento (configuración Web)  
\<applicationPool > elemento (configuración Web)  
  
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
|`maxConcurrentRequestsPerCPU`|Especifica cuántas solicitudes simultáneas permite ASP.NET por CPU.|  
|`maxConcurrentThreadsPerCPU`|Especifica cuántos subprocesos simultáneos pueden estar en ejecución para un grupo de aplicaciones para cada CPU. Esto proporciona una manera alternativa para controlar la simultaneidad ASP.NET, ya que permite limitar el número de subprocesos administrados que se puede usar por CPU para atender las solicitudes. De forma predeterminada este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos CLR también limita el número de subprocesos que se pueden crear.|  
|`requestQueueLimit`|Especifica el número máximo de solicitudes que pueden poner en cola para ASP.NET en un único proceso. Cuando dos o más aplicaciones de ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación en el grupo de aplicaciones está sujeto a esta configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contiene información sobre cómo ASP.NET interactúa con una aplicación host.|  
  
## <a name="remarks"></a>Comentarios  
 Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior en el modo integrado, esta combinación de elementos permite configurar cómo administra ASP.NET los subprocesos y las colas de solicitudes cuando la aplicación se hospeda en un grupo de aplicaciones de IIS. Si ejecuta IIS 6 o ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en modo clásico o en modo ISAPI, estos valores se omiten.  
  
 El `applicationPool` configuración se aplica a todos los grupos de aplicaciones que se ejecutan en una versión concreta de .NET Framework. La configuración se encuentra en un archivo aspnet.config. Hay una versión de este archivo para las versiones 2.0 y 4.0 de .NET Framework. (Las versiones 3.0 y 3.5 de .NET Framework comparten el archivo aspnet.config con la versión 2.0.)  
  
> [!IMPORTANT]
>  Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en [!INCLUDE[win7](../../../../../includes/win7-md.md)], puede configurar un archivo aspnet.config diferente para cada grupo de aplicaciones. Esto le permite adaptar el rendimiento de los subprocesos para cada grupo de aplicaciones.  
  
 Para el `maxConcurrentRequestsPerCPU` configuración, el valor predeterminado de "5000" la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] eficazmente desactiva la limitación de solicitudes controlada por ASP.NET, a menos que realmente tenga 5000 o más solicitudes por CPU. La configuración predeterminada depende en su lugar, el grupo de subprocesos CLR para administrar automáticamente la simultaneidad por CPU. Las aplicaciones que hacen un amplio uso de procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en E/S de red, puede beneficiarse de la mayor límite predeterminado de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]. Establecer `maxConcurrentRequestsPerCPU` en cero el uso de los subprocesos administrados se desactiva para procesar solicitudes ASP.NET. Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de E/S de IIS y, por tanto, la simultaneidad está limitada por la configuración de subprocesos IIS.  
  
 El `requestQueueLimit` configuración funciona del mismo modo que la `requestQueueLimit` atributo de la [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) elemento, que se establece en los archivos Web.config para las aplicaciones ASP.NET. Sin embargo, el `requestQueueLimit` configuración en un archivo aspnet.config invalida el `requestQueueLimit` en un archivo Web.config. En otras palabras, si se establecen ambos atributos (de forma predeterminada, esto es true), el `requestQueueLimit` configuración en el archivo aspnet.config tiene prioridad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config en las siguientes circunstancias:  
  
-   La aplicación se hospeda en un [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] grupo de aplicaciones.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]se está ejecutando en el modo integrado.  
  
-   La aplicación está utilizando el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior.  
  
 Los valores en el ejemplo son los valores predeterminados.  
  
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
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Vea también  
 [Elemento \<system.web> (configuración web)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
