---
title: "Ejemplo de detecci&#243;n de un servicio con un modo de URI de escucha &#250;nico | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Ejemplo de detecci&#243;n de un servicio con un modo de URI de escucha &#250;nico
En este ejemplo se muestra cómo detectar un servicio que tiene la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> establecida en <xref:System.ServiceModel.Description.ListenUriMode>.Cuando la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> está establecida en <xref:System.ServiceModel.Description.ListenUriMode>, se asegura de que ListenUri es único estableciendo el puerto para que sea único o para que la ruta de acceso sea único anexando un GUID.  
  
### Características en el servicio  
 La propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> se establece en <xref:System.ServiceModel.Description.ListenUriMode> para el extremo TCP.A continuación, el servicio se puede detectar a través de un extremo de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
### Características en el cliente  
 Este cliente se conecta al servicio utilizando el `Via.Uri` correcto con el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>.A continuación, el objeto <xref:System.ServiceModel.Discovery.FindResponse> que devuelve el método se consulta para comprobar si contiene una propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> válida y si es diferente de `Address.Uri`.A continuación, la información adecuada se pasa al método `InvokeCalculatorService`.En el método `InvokeCalculatorService`, el llamador pasa la propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> y un `ClientViaBehavior` con el `Via.Uri` correcto se agrega al extremo del cliente.  
  
##### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra UniqueListenUriMode.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Ejecute la aplicación de servicio, que se genera en la carpeta \[directorio base de la solución\]\\service\\bin\\debug.  
  
4.  Ejecute la aplicación cliente, que se genera en la carpeta \[directorio base de la solución\]\\Client\\bin\\debug.  
  
     El cliente busca el servicio en ejecución y escribe en la consola los metadatos publicados por el extremo del servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## Vea también