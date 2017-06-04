---
title: "AspNetRouteIntegration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# AspNetRouteIntegration
En este ejemplo se muestra cómo hospedar un servicio REST de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mediante rutas de ASP.NET.El ejemplo de [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) muestra una versión auto\-hospedada de este escenario y discute la implementación del servicio en profundidad.Este tema se centra en la característica de integración de ASP.NET.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] Servicio de enrutamiento ASP.NET, vea <xref:System.Web.Routing>.  
  
## Detalles del ejemplo  
 El servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expone una colección de clientes al modo de REST u orientado a los recursos.Al igual que un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basado en SOAP, el servicio se puede hospedar en ASP.NET utilizando un archivo .svc.Sin embargo, a menudo esto no es deseable para los escenarios del HTTP porque requiere tener .svc en la dirección URL del servicio.Además, requiere implementar un archivo .svc junto con la biblioteca de servicios.Estas limitaciones se pueden evitar hospedando el servicio mediante las rutas de ASP.NET, como se muestra en este ejemplo.  
  
 En el ejemplo se hospeda el servicio en ASP.NET agregando un objeto <xref:System.ServiceModel.Activation.ServiceRoute> en un archivo Global.asax.El objeto <xref:System.ServiceModel.Activation.ServiceRoute> especifica el tipo del servicio \('Service' en este caso\), el tipo del generador de host de servicio para utilizar para el servicio \(<xref:System.ServiceModel.Activation.WebServiceHostFactory> en este caso\) y la dirección base HTTP para el servicio \('~\/Customers en este caso\).  
  
 Además de esto, en el ejemplo se incluye un archivo Web.config que agrega el objeto <xref:System.Web.Routing.UrlRoutingModule> \(para activar las rutas ASP.NET\) e incluye la configuración para el servicio.En particular, la configuración configura el servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con un objeto <xref:System.ServiceModel.Description.WebHttpEndpoint> predeterminado que tiene la propiedad <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> establecida en `true`.Como resultado, la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una página de Ayuda basada en HTML automática en `http://localhost/Customers/help` que proporciona información acerca de cómo construir las solicitudes HTTP para servicio y cómo tener acceso a la respuesta HTTP del servicio, por ejemplo, lo que es una muestra de cómo se representan los detalles del cliente en XML y JSON.  
  
 Exponer la colección del cliente \(y más generalmente, de cualquier recurso\) de esta manera permite a un cliente interactuar con un servicio de una manera uniforme utilizando direcciones URI y HTTP `GET`, `PUT`, `DELETE` y `POST`.  
  
 Program.cs en el proyecto cliente muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>.Observe que se trata de simplemente una manera de tener acceso a un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].También es posible tener acceso al servicio utilizando otras clases de .NET Framework como el generador de canales de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y <xref:System.Net.WebClient>.Otros ejemplos del SDK \(como [Servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) y [Selección de formato automática](../../../../docs/framework/wcf/samples/automatic-format-selection.md)\) muestran cómo utilizar estas clases para comunicarse con un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 ESte ejemplo consta de tres proyectos:  
  
 Servicio  
 Proyecto de aplicación web que incluye un servicio HTTP WCF hospedado en ASP.NET.  
  
 Cliente  
 Proyecto de aplicación de consola que realiza las llamadas al servicio.  
  
 Común  
 Biblioteca compartida que contiene el tipo `Customer` que usa el cliente y el servicio.Cuando se ejecuta la aplicación de consola del cliente, el cliente realiza las solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### Para utilizar este ejemplo  
  
1.  Abra la solución para obtener el ejemplo de Integración de rutas de ASP.NET en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
3.  Si no está abierta aún, presione "CTRL\+W, S" para abrir la ventana del **Explorador de soluciones**.  
  
4.  Desde las ventanas del **Explorador de soluciones**, haga clic con el botón secundario en el proyecto de **Servicio**, coloque el cursor sobre la opción de menú contextual **Depurar** para que el menú contextual **Iniciar nueva instancia** aparezca y seleccione **Iniciar nueva instancia**.De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5.  Desde las ventanas del **Explorador de soluciones**, haga clic con el botón secundario en el proyecto de **Cliente**, coloque el cursor sobre la opción de menú contextual **Depurar** para que el menú contextual **Iniciar nueva instancia** aparezca y seleccione **Iniciar nueva instancia**.  
  
6.  La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
7.  Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
8.  Presione Mayús\+F5 para detener la depuración del servicio y, en el Área de notificación de Windows, haga clic con el botón secundario en el icono del servidor de desarrollo de ASP.NET y seleccione **Detener** en el menú contextual.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## Vea también