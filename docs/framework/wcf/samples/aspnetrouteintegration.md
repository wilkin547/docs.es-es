---
title: AspNetRouteIntegration
ms.date: 03/30/2017
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
ms.openlocfilehash: 8d9a0710e5106cbc3d02a06e81f4f8ed9ae3e03b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43475886"
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
Este ejemplo muestra cómo hospedar un servicio REST de Windows Communication Foundation (WCF) mediante las rutas de ASP.NET. El [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo se muestra una versión auto-hospedada de este escenario y explica la implementación del servicio en profundidad. Este tema se centra en la característica de integración de ASP.NET. Para obtener más información sobre el enrutamiento de ASP.NET, vea <xref:System.Web.Routing>.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 El servicio WCF expone una colección de clientes de una manera de REST u orientado a recursos. Al igual que un servicio WCF basado en SOAP, el servicio puede hospedarse en ASP.NET utilizando un archivo .svc. Sin embargo, a menudo esto no es deseable para los escenarios del HTTP porque requiere tener .svc en la dirección URL del servicio. Además, requiere implementar un archivo .svc junto con la biblioteca de servicios. Estas limitaciones se pueden evitar hospedando el servicio mediante las rutas de ASP.NET, como se muestra en este ejemplo.  
  
 En el ejemplo se hospeda el servicio en ASP.NET agregando un objeto <xref:System.ServiceModel.Activation.ServiceRoute> en un archivo Global.asax. El objeto <xref:System.ServiceModel.Activation.ServiceRoute> especifica el tipo del servicio ('Service' en este caso), el tipo del generador de host de servicio para utilizar para el servicio (<xref:System.ServiceModel.Activation.WebServiceHostFactory> en este caso) y la dirección base HTTP para el servicio ('~/Customers en este caso).  
  
 Además de esto, en el ejemplo se incluye un archivo Web.config que agrega el objeto <xref:System.Web.Routing.UrlRoutingModule> (para activar las rutas ASP.NET) e incluye la configuración para el servicio. En concreto, la configuración configura el servicio WCF con el valor predeterminado es <xref:System.ServiceModel.Description.WebHttpEndpoint> que tiene el <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> si se establece en `true`. Como resultado, la infraestructura de WCF crea una página de Ayuda basada en HTML automática en `http://localhost/Customers/help` que proporciona información acerca de cómo construir HTTP las solicitudes al servicio y cómo tener acceso a la respuesta HTTP del servicio, por ejemplo, un ejemplo de cómo el cliente los detalles se representan en XML y JSON.  
  
 Exponer la colección del cliente (y más generalmente, de cualquier recurso) de esta manera permite a un cliente interactuar con un servicio de una manera uniforme utilizando direcciones URI y HTTP `GET`, `PUT`, `DELETE` y `POST`.  
  
 Program.cs en el proyecto cliente muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>. Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF. También es posible tener acceso al servicio utilizando otras clases de .NET Framework, como el generador de canales WCF y <xref:System.Net.WebClient>. Otros ejemplos del SDK (como el [servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) ejemplo y el [selección automática de formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) ejemplo) se muestra cómo utilizar estas clases para comunicarse con un servicio WCF.  
  
 ESte ejemplo consta de tres proyectos:  
  
 web de Office  
 Proyecto de aplicación web que incluye un servicio HTTP WCF hospedado en ASP.NET.  
  
 Cliente  
 Proyecto de aplicación de consola que realiza las llamadas al servicio.  
  
 Común  
 Biblioteca compartida que contiene el tipo `Customer` que usa el cliente y el servicio. Cuando se ejecuta la aplicación de consola del cliente, el cliente realiza las solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución para obtener el ejemplo de Integración de rutas de ASP.NET en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Si aún no está abierto, presione "CTRL+W, S" para abrir el **el Explorador de soluciones** ventana.  
  
4.  Desde el **el Explorador de soluciones** windows, haga clic en el **servicio** del proyecto y coloque el cursor sobre la **depurar** opción del menú contextual para que el **iniciar Nueva instancia** menú contextual aparece y seleccione **Iniciar nueva instancia**.  De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.  
  
5.  Desde el **el Explorador de soluciones** windows, haga clic en el **cliente** del proyecto y coloque el cursor sobre la **depurar** opción del menú contextual para que el **iniciar nuevo Instancia** menú contextual aparece y seleccione **Iniciar nueva instancia**.  
  
6.  La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
7.  Presione cualquier tecla para terminar la aplicación de consola del cliente.  
  
8.  Presione MAYÚS+F5 para detener la depuración del servicio y en el área de notificación de Windows, haga clic en el icono del servidor de desarrollo de ASP.NET y seleccione **detener** en el menú contextual.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>Vea también
