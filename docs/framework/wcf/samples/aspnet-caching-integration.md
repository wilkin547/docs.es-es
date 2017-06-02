---
title: "Integraci&#243;n de almacenamiento en cach&#233; de ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Integraci&#243;n de almacenamiento en cach&#233; de ASP.NET
En este ejemplo se muestra cómo utilizar la memoria caché de resultados de ASP.NET con el modelo de programación HTTP wEB de WCF.  Vea el ejemplo de [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) para obtener una versión autohospedada de este escenario que explique la implementación del servicio a fondo.  Este tema se centra en la característica de integración de la memoria caché de resultados de ASP.NET.  
  
## Demostraciones  
 Integración con la memoria caché de resultados de ASP.NET  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## Explicación  
 En el ejemplo se utiliza <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> para utilizar el almacenamiento en la memoria caché de resultados de ASP.NET con el servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> se aplica a las operaciones de servicio y proporciona el nombre de un perfil de la memoria caché en un archivo de configuración que se debería aplicar a las respuestas de la operación dada.  
  
 En el archivo Service.cs del proyecto Servicio del ejemplo, ambas operaciones, `GetCustomers` y `GetCustomer`, se marcan con <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, que proporciona el nombre del perfil de la memoria caché "CacheFor60Seconds".  En el archivo Web.config del proyecto Servicio, el perfil de la memoria caché "CacheFor60Seconds" se proporciona bajo el elemento \<`caching`\> de \<`system.web`\>.  Para este perfil de la memoria caché, el valor del atributo `duration` es "60", de modo que las respuestas asociadas a este perfil están almacenadas en la memoria caché, en la caché de resultados de ASP.NET durante 60 segundos.  Además, para este perfil de la memoria caché, el atributo `varmByParam` se establece en "format" de modo que las solicitudes con valores diferentes para el parámetro de cadena de consulta `format` tengan sus respuestas almacenadas en memoria caché de forma independiente.  Por último, el atributo `varyByHeader` del perfil de la memoria caché se establece en "Accept", de modo que las solicitudes con diferentes valores de encabezado Accept tienen sus respuestas almacenadas en memoria caché separadamente.  
  
 Program.cs en el proyecto cliente muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>.  Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF.  También es posible tener acceso al servicio utilizando otras clases de .NET Framework como el generador de canales de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y <xref:System.Net.WebClient>.  Otros ejemplos del SDK \(como [Servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) y [Selección de formato automática](../../../../docs/framework/wcf/samples/automatic-format-selection.md)\) ilustran cómo utilizar estas clases para comunicarse con un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Para ejecutar el ejemplo  
 El ejemplo consta de tres proyectos:  
  
-   **Servicio**: proyecto de aplicación web que incluye un servicio HTTP WCF hospedado en ASP.NET.  
  
-   **Cliente**: proyecto de aplicación de consola que realiza las llamadas al servicio.  
  
-   **Común**: biblioteca compartida que contiene el tipo Customer utilizado por el cliente y el servicio.  
  
 Cuando se ejecuta la aplicación de consola Cliente, el cliente realiza las solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución para obtener el ejemplo de integración del almacenamiento en caché de ASP.NET.  
  
2.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
3.  Si no está abierta aún, presione CTRL\+W\+S para abrir la ventana del **Explorador de soluciones**.  
  
4.  En la ventana del  **Explorador de soluciones**, haga clic con el botón secundario en el proyecto **Servicio** y seleccione **Iniciar nueva instancia**.  De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5.  En la ventana del  **Explorador de soluciones**, haga clic con el botón secundario en el proyecto **Cliente** y seleccione **Iniciar nueva instancia**.  
  
6.  La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.  Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.  
  
7.  A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
8.  Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
9. Presione MAYÚS\+F5 para dejar de depurar el servicio.  
  
10. En el Área de notificación de Windows, haga clic con el botón secundario en el icono del servidor de desarrollo de ASP.NET y seleccione **Detener**.