---
title: Control de errores de WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d951c0d85294dfcef56e231f7702cb2d37efa967
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="wcf-error-handling"></a>Control de errores de WCF
Los errores detectados por una aplicación WCF pertenecen a uno de los tres grupos:  
  
1.  Errores de comunicación  
  
2.  Errores de proxy o canal  
  
3.  Errores de aplicación  
  
 Los errores de comunicación se producen cuando una red no está disponible, un cliente usa una dirección incorrecta o el host de servicio no escucha los mensajes entrantes. Los errores de este tipo se devuelven al cliente como clase <xref:System.ServiceModel.CommunicationException> o clase derivada de la clase <xref:System.ServiceModel.CommunicationException>.  
  
 Los errores de proxy o canal son errores que se producen en el propio canal o proxy. Los errores de este tipo incluyen: el intento por usar un proxy o canal cerrados, la existencia de una discrepancia entre el cliente y el servicio, o el rechazo de las credenciales del cliente por parte del servicio. Existen muchos tipos de errores distintos en esta categoría, demasiados para enumerarlos aquí. Los errores de este tipo se devuelven al cliente tal cual (no se realiza ninguna transformación en los objetos de excepción).  
  
 Los errores de aplicación se producen durante la ejecución de una operación de servicio. Los errores de este tipo se envían al cliente como clase <xref:System.ServiceModel.FaultException> o clase <xref:System.ServiceModel.FaultException%601>.  
  
 El control de errores en WCF se realiza mediante una o varias de las siguientes acciones:  
  
-   Controlar directamente la excepción producida, que solo se lleva a cabo para errores de comunicación y de proxy o canal.  
  
-   Usar contratos de errores  
  
-   Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler>  
  
-   Controlar eventos <xref:System.ServiceModel.ServiceHost>  
  
## <a name="fault-contracts"></a>Contrato de error  
 Los contratos de error le permiten definir los errores que se pueden producir durante la operación de servicio en una plataforma de manera independiente. De forma predeterminada, todas las excepciones producidas desde una operación de servicio se devolverán al cliente como objeto <xref:System.ServiceModel.FaultException>. El objeto <xref:System.ServiceModel.FaultException> contendrá muy poca información. Puede controlar la información enviada al cliente mediante la definición de un contrato de error y la devolución del error como clase <xref:System.ServiceModel.FaultException%601>. Para obtener más información, consulte [especificar y control de errores en contactos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="ierrorhandler"></a>IErrorHandler  
 La interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> le permite controlar más la respuesta de la aplicación WCF a los errores.  Proporciona control total sobre el mensaje de error devuelto al cliente y permite realizar el procesamiento de errores personalizado como el registro.  Para obtener más información acerca de <xref:System.ServiceModel.Dispatcher.IErrorHandler> y [extender Control sobre un control de errores e informes](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)  
  
## <a name="servicehost-events"></a>Eventos ServiceHost  
 La clase <xref:System.ServiceModel.ServiceHost> hospeda servicios y define varios eventos que quizá sean necesarios para el control de errores. Por ejemplo:  
  
1.  <!--zz <xref:System.ServiceModel.ServiceHost.Faulted>-->  `System.ServiceModel.ServiceHost.Faulted`
  
2. <!--zz  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  --> `System.ServiceModel.ServiceHost.UnknownMessageReceived`
  
 Para obtener más información, vea <xref:System.ServiceModel.ServiceHost>
