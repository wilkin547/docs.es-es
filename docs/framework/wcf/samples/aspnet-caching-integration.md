---
title: "Integración de almacenamiento en caché de ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d56c435088be383821d17250e230cae848d2bab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="aspnet-caching-integration"></a>Integración de almacenamiento en caché de ASP.NET
En este ejemplo se muestra cómo utilizar la memoria caché de resultados de ASP.NET con el modelo de programación HTTP wEB de WCF. Vea la [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo para obtener una versión de este escenario que se explica la implementación del servicio en profundidad hospedada por sí mismo. Este tema se centra en la característica de integración de la memoria caché de resultados de ASP.NET.  
  
## <a name="demonstrates"></a>Demostraciones  
 Integración con la memoria caché de resultados de ASP.NET  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>Explicación  
 En el ejemplo se utiliza <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> para utilizar el almacenamiento en la memoria caché de resultados de ASP.NET con el servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> se aplica a las operaciones de servicio y proporciona el nombre de un perfil de la memoria caché en un archivo de configuración que se debería aplicar a las respuestas de la operación dada.  
  
 En el archivo Service.cs del proyecto de servicio de ejemplo, tanto la `GetCustomer` y `GetCustomers` operaciones se marcan con la <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, que proporciona el nombre del perfil de caché "CacheFor60Seconds". En el archivo Web.config del proyecto de servicio, el perfil de caché "CacheFor60Seconds" se proporciona en el <`caching`> elemento de <`system.web`>. Para este perfil de caché, el valor de la `duration` atributo es "60", por lo que las respuestas asociadas con este perfil se almacenan en caché en la caché de resultados ASP.NET durante 60 segundos. Además, para este perfil de caché, el `varmByParam` atributo está establecido en "format" de modo que las solicitudes con valores diferentes para el `format` consulta al parámetro de cadena tienen sus respuestas en caché por separado. Por último, el perfil de caché `varyByHeader` atributo está establecido en "Accept", por lo que las solicitudes con diferentes valores de encabezado Accept tienen sus respuestas en caché por separado.  
  
 Program.cs en el proyecto cliente muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>. Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF. También es posible tener acceso al servicio utilizando otras clases de .NET Framework como el generador de canales de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y <xref:System.Net.WebClient>. Otros ejemplos del SDK (como el [servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) ejemplo y la [la selección automática de formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) ejemplo) muestran cómo utilizar estas clases para comunicarse con un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio.  
  
## <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
 El ejemplo consta de tres proyectos:  
  
-   **Servicio**: proyecto de aplicación Web que incluye un servicio HTTP WCF hospedado en ASP.NET.  
  
-   **Cliente**: un proyecto de aplicación de consola que realiza llamadas al servicio.  
  
-   **Common**: una biblioteca compartida que contiene el tipo de cliente utilizado por el cliente y el servicio.  
  
 Cuando se ejecuta la aplicación de consola Cliente, el cliente realiza las solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución para obtener el ejemplo de integración del almacenamiento en caché de ASP.NET.  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Si el **el Explorador de soluciones** ventana ya no está abierta, presione CTRL + W + S.  
  
4.  Desde el **el Explorador de soluciones** (ventana), haga clic derecho el **servicio** de proyecto y seleccione **Iniciar nueva instancia**. De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5.  Desde el **el Explorador de soluciones** (ventana), haga clic derecho el **cliente** de proyecto y seleccione **Iniciar nueva instancia**.  
  
6.  La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.  
  
7.  A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
8.  Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
9. Presione MAYÚS+F5 para dejar de depurar el servicio.  
  
10. En el área de notificación de Windows, haga clic con el icono del servidor de desarrollo de ASP.NET y seleccione **detener**.
