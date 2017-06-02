---
title: "Ejemplo de anuncios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Ejemplo de anuncios
En este ejemplo se muestra cómo utilizar la funcionalidad de anuncio de la característica de detección.Los anuncios permiten a los servicios enviar mensajes de anuncio que contienen metadatos del servicio.De forma predeterminada, se envía un anuncio de saludo cuando el servicio se inicia y otro de despedida al cerrarse.Estos anuncios pueden ser de multidifusión o se pueden enviar de punto a punto.Este ejemplo está compuesto de dos proyectos: servicio y cliente.  
  
## Servicio  
 Este proyecto contiene un servicio de calculadora autohospedado.En el método `Main`, se crea un host de servicio y se le agrega un extremo de servicio.Después, se crea un <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.Para habilitar los anuncios, se debe agregar un extremo de anuncio a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.En este caso, se agrega como extremo del anuncio un extremo estándar que usa multidifusión UDP.De esta forma se difunden los anuncios a través de una dirección UDP conocida.  
  
```  
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());  
  
// Create a ServiceHost for the CalculatorService type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
{  
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);  
  
     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();  
  
     // Announce the availability of the service over UDP multicast  
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());  
  
    // Make the service discoverable over UDP multicast.  
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);                  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    serviceHost.Open();  
    // ...  
}  
```  
  
## Cliente  
 En este proyecto, observe que el cliente hospeda un <xref:System.ServiceModel.Discovery.AnnouncementService>.Además, se registran dos delegados con eventos.Estos eventos dictan lo que el cliente hace cuando se reciben anuncios en línea y sin conexión.  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
```  
  
 Los métodos `OnOfflineEvent` y `OnOnlineEvent` administran los mensajes de anuncio de saludo y despedida, respectivamente.  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)  
{  
    Console.WriteLine();              
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);  
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);  
}  
  
static void OnOfflineEvent(object sender, AnnouncementEventArgs e)  
{  
    Console.WriteLine();  
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);  
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);  
}  
```  
  
#### Para utilizar este ejemplo  
  
1.  Este ejemplo utiliza los extremos HTTP y para ejecutarlo se deben agregar las ACL de dirección URL apropiadas; vea [Configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener detalles.Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.`netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  Compile la solución.  
  
3.  Ejecute la aplicación client.exe.  
  
4.  Ejecute la aplicación service.exe.Observe que el cliente recibe un anuncio en línea.  
  
5.  Cierre la aplicación service.exe.Observe que el cliente recibe un anuncio sin conexión.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`  
  
## Vea también