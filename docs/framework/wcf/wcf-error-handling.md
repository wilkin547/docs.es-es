---
title: "Control de errores de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Control de errores de WCF
Los errores detectados por una aplicación WCF pertenecen a uno de los tres grupos:  
  
1.  Errores de comunicación  
  
2.  Errores de proxy o canal  
  
3.  Errores de aplicación  
  
 Los errores de comunicación se producen cuando una red no está disponible, un cliente usa una dirección incorrecta o el host de servicio no escucha los mensajes entrantes.Los errores de este tipo se devuelven al cliente como clase <xref:System.ServiceModel.CommunicationException> o clase derivada de la clase <xref:System.ServiceModel.CommunicationException>.  
  
 Los errores de proxy o canal son errores que se producen en el propio canal o proxy.Los errores de este tipo incluyen: el intento por usar un proxy o canal cerrados, la existencia de una discrepancia entre el cliente y el servicio, o el rechazo de las credenciales del cliente por parte del servicio.Existen muchos tipos de errores distintos en esta categoría, demasiados para enumerarlos aquí.Los errores de este tipo se devuelven al cliente tal cual \(no se realiza ninguna transformación en los objetos de excepción\).  
  
 Los errores de aplicación se producen durante la ejecución de una operación de servicio.Los errores de este tipo se envían al cliente como clase <xref:System.ServiceModel.FaultException> o clase <xref:System.ServiceModel.FaultException%601>.  
  
 El control de errores en WCF se realiza mediante una o varias de las siguientes acciones:  
  
-   Controlar directamente la excepción producida,que solo se lleva a cabo para errores de comunicación y de proxy o canal.  
  
-   Usar contratos de errores  
  
-   Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler>  
  
-   Controlar eventos <xref:System.ServiceModel.ServiceHost>  
  
## Contrato de error  
 Los contratos de error le permiten definir los errores que se pueden producir durante la operación de servicio en una plataforma de manera independiente.De forma predeterminada, todas las excepciones producidas desde una operación de servicio se devolverán al cliente como objeto <xref:System.ServiceModel.FaultException>.El objeto <xref:System.ServiceModel.FaultException> contendrá muy poca información.Puede controlar la información enviada al cliente mediante la definición de un contrato de error y la devolución del error como clase <xref:System.ServiceModel.FaultException%601>.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Especificación y administración de errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## IErrorHandler  
 La interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> le permite controlar más la respuesta de la aplicación WCF a los errores.Proporciona control total sobre el mensaje de error devuelto al cliente y permite realizar el procesamiento de errores personalizado como el registro.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Dispatcher.IErrorHandler> y [Extensión de control a control de errores y creación de informes](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)  
  
## Eventos ServiceHost  
 La clase <xref:System.ServiceModel.ServiceHost> hospeda servicios y define varios eventos que quizá sean necesarios para el control de errores.Por ejemplo:  
  
1.  <xref:System.ServiceModel.ServiceHost.Faulted>  
  
2.  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] <xref:System.ServiceModel.ServiceHost>