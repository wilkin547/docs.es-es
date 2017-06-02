---
title: "&lt;applicationPool&gt; (Elemento) (Configuraci&#243;n web) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<applicationPool> (elemento)"
  - "applicationPool (elemento)"
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;applicationPool&gt; (Elemento) (Configuraci&#243;n web)
Especifica la configuración usada por ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación ASP.NET se está ejecutando en modo integrado en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o en una versión posterior.  
  
> [!IMPORTANT]
>  Este elemento y la característica que admite solo funcionan si su aplicación ASP.NET está hospedada en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o en versiones posteriores.  
  
## Sintaxis  
  
```  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Especifica cuántas solicitudes simultáneas permite ASP.NET por CPU.|  
|`maxConcurrentThreadsPerCPU`|Especifica cuántos subprocesos simultáneos se pueden estar ejecutando para un grupo de aplicaciones para cada CPU.  Esto proporciona una manera alternativa de controlar la simultaneidad de ASP.NET, ya que puede limitar el número de subprocesos administrados que se pueden usar por CPU para atender las solicitudes.  De forma predeterminada este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos de CLR también limita el número de subprocesos que se pueden crear.|  
|`requestQueueLimit`|Especifica el número máximo de solicitudes que se pueden poner en cola para ASP.NET en un único proceso.  Cuando dos o más aplicaciones ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación del grupo de aplicaciones está sujeto a este valor.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contiene información sobre cómo ASP.NET interactúa con una aplicación host.|  
  
## Comentarios  
 Cuando ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior en modo integrado, esta combinación de elementos permite configurar cómo administra ASP.NET los subprocesos y cómo pone en cola las solicitudes cuando la aplicación está hospedada en un grupo de aplicaciones de IIS.  Si ejecuta IIS 6 o [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en modo Clásico o en modo ISAPI, se pasa por alto esta configuración.  
  
 Los valores `applicationPool` se aplican a todos los grupos de aplicaciones que se ejecutan en una versión determinada de .NET Framework.  La configuración está contenida en un archivo aspnet.config.  Hay una versión de este archivo para las versiones 2.0 y 4 de .NET Framework. \(Las versiones 3.0 y 3.5 de .NET Framework comparten el archivo aspnet.config con la versión 2.0.\)  
  
> [!IMPORTANT]
>  Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en [!INCLUDE[win7](../../../../../includes/win7-md.md)], puede configurar un archivo aspnet.config diferente para cada grupo de aplicaciones.  Esto le permite adaptar el rendimiento de los subprocesos para cada grupo de aplicaciones.  
  
 Para el valor `maxConcurrentRequestsPerCPU`, el valor predeterminado de "5000" en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] desactiva la limitación de solicitudes controlada por ASP.NET, a menos que realmente tenga 5000 o más solicitudes por CPU.  La configuración predeterminada depende en su lugar del grupo de subprocesos de CLR para administrar automáticamente la simultaneidad por CPU.  Las aplicaciones que utilizan mucho procesamiento de solicitudes asincrónico, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en la E\/S de red, se beneficiarán del mayor límite predeterminado de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  Al establecer `maxConcurrentRequestsPerCPU` en cero se desactiva el uso de subprocesos administrados para procesar las solicitudes de ASP.NET.  Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de E\/S de IIS y, por tanto, la simultaneidad está limitada por la configuración de subprocesos de IIS.  
  
 El valor `requestQueueLimit` funciona de la misma manera que el atributo `requestQueueLimit` del elemento [processModel](http://msdn.microsoft.com/es-es/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d), que se establece en los archivos Web.config para las aplicaciones ASP.NET.  Sin embargo, el valor `requestQueueLimit` de un archivo aspnet.config invalida el valor `requestQueueLimit` de un archivo Web.config.  Es decir, si se establecen ambos atributos \(de forma predeterminada, esto es verdad\), el valor `requestQueueLimit` del archivo aspnet.config tiene prioridad.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo aspnet.config en las circunstancias siguientes:  
  
-   La aplicación está hospedada en un grupo de aplicaciones de [!INCLUDE[iisver](../../../../../includes/iisver-md.md)].  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] se está ejecutando en modo integrado.  
  
-   La aplicación está usando [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior.  
  
 Los valores de este ejemplo son los valores predeterminados.  
  
```  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres||  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## Vea también  
 [\<system.web\> \(Elemento\) \(Configuración web\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)