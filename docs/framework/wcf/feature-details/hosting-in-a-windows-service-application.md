---
title: "Hospedaje en una aplicaci&#243;n de servicios de Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Hospedaje en una aplicaci&#243;n de servicios de Windows
Los servicios de Windows \(anteriormente conocidos como servicios de Windows NT\) proporcionan un modelo de procesamiento particularmente apropiado para las aplicaciones que deben vivir en una aplicación ejecutable de larga duración y que no deben mostrar ninguna forma de interfaz de usuario.  La duración de un proceso de una aplicación de servicios de Windows es administrada mediante el Administrador de control de servicios \(SCM\) que le permite iniciar, detener y pausar aplicaciones de servicios de Windows.  Puede configurar un proceso de servicio de Windows para que se inicie automáticamente cuando el equipo se inicia, convirtiéndolo en un entorno de hospedaje apropiado para aplicaciones que siempre deban estar en funcionamiento.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] sobre las aplicaciones de servicios de Windows, vea [Aplicaciones de servicios de Windows](http://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Las aplicaciones que hospedan servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] de ejecución prolongada comparten muchas características con los servicios de Windows.  En concreto, los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son aplicaciones ejecutables de servidor de ejecución prolongada que no interactúan directamente con el usuario y que, por consiguiente, no implementan ninguna forma de interfaz de usuario.  Como tal, el hospedaje de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una aplicación de servicios de Windows constituye una opción para crear aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] robustas y de ejecución prolongada.  
  
 A menudo, los programadores de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deben decidir si hospedar su aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una aplicación de servicios de Windows o dentro del entorno de hospedaje de Internet Information Services \(IIS\) o Windows Process Activation Service \(WAS\).  Debería considerar el uso de aplicaciones de servicios de Windows bajo las siguientes condiciones:  
  
-   Su aplicación requiere la activación explícita.  Por ejemplo, debería utilizar los servicios de Windows cuando su aplicación se deba iniciar automáticamente cuando el servidor se inicie en lugar de iniciarse dinámicamente en respuesta al primer mensaje entrante.  
  
-   El proceso que hospeda su aplicación debe seguir ejecutándose una vez iniciado.  Una vez iniciado, un proceso de servicio de Windows permanece ejecutándose a menos que sea cerrado explícitamente por parte de un administrador del servidor mediante el Administrador de control de servicios.  Las aplicaciones hospedadas en IIS o WAS se pueden iniciar y detener dinámicamente para realizar un uso óptimo de los recursos del sistema.  Las aplicaciones que requieren el control explícito sobre la duración de su proceso de hospedaje deberían utilizar los servicios de Windows en lugar de IIS o WAS.  
  
-   Su servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe ejecutarse en Windows Server 2003 y usar transportes que no sean HTTP.  En Windows Server 2003, el entorno de hospedaje de [!INCLUDE[iis601](../../../../includes/iis601-md.md)] está restringido solo a la comunicación HTTP.  Las aplicaciones de servicio de Windows no están sujetas a esta restricción y pueden utilizar cualquier transporte que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admita, incluyendo net.tcp, net.pipe y net.msmq.  
  
### Hospedaje de WCF dentro de una aplicación de servicio de Windows  
  
1.  Cree una aplicación de servicio de Windows.  Puede escribir aplicaciones de servicio de Windows mediante código administrado utilizando las clases del espacio de nombres <xref:System.ServiceProcess>.  Esta aplicación debe incluir una clase que herede a partir de <xref:System.ServiceProcess.ServiceBase>.  
  
2.  Vincule la duración de los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a la duración de la aplicación de servicio de Windows.  Normalmente, desea que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en una aplicación de servicio de Windows se activen cuando se inicia el servicio de hospedaje, dejen de realizar escuchas de mensajes cuando se detiene el servicio de hospedaje y cierren el proceso de hospedaje cuando el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] encuentre un error.  Esto se puede lograr de la siguiente manera:  
  
    -   Invalide [OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> para abrir una o más instancias de <xref:System.ServiceModel.ServiceHost>.  Una única aplicación de servicio de Windows puede hospedar varios servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se inician y se detienen como un grupo.  
  
    -   Invalide <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Closed> en el <xref:System.ServiceModel.ServiceHost> cualquier servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en ejecución que se inició durante [OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.  
  
    -   Suscríbase al evento <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> de <xref:System.ServiceModel.ServiceHost> y utilice la clase <xref:System.ServiceProcess.ServiceController> para cerrar la aplicación de servicio de Windows en caso de error.  
  
     Las aplicaciones de servicio de Windows que hospedan servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se implementan y administran de la misma manera que las aplicaciones de servicio de Windows que no utilizan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Vea también  
 <xref:System.ServiceProcess>   
 [Tutorial: Crear una aplicación de servicios de Windows en el Diseñador de componentes](http://go.microsoft.com/fwlink/?LinkId=94875)   
 [Hospedaje de un servicio WCF en un servicio administrado de Windows](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)   
 [Host de servicio de Windows](../../../../docs/framework/wcf/samples/windows-service-host.md)   
 [Arquitectura de programación de aplicaciones de servicio](http://go.microsoft.com/fwlink/?LinkId=94876)   
 [Características de hospedaje de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201276)