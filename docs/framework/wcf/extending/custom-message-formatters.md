---
description: 'Más información acerca de: formateadores de mensajes personalizados'
title: Formateadores de mensajes personalizados
ms.date: 03/30/2017
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
ms.openlocfilehash: 34d4eb1820ce57162c7ac4d97a85a409e27fc062
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735275"
---
# <a name="custom-message-formatters"></a>Formateadores de mensajes personalizados

El contenido de un mensaje tiene, a menudo, forma de XML, que normalmente no es un formato conveniente para una aplicación. Las aplicaciones manipulan objetos, obteniendo y estableciendo sus propiedades. Windows Communication Foundation (WCF) utiliza el *contrato de datos* para convertir un <xref:System.ServiceModel.Channels.Message> objeto en un objeto fácilmente controlado por una aplicación. Estos procesos se denominan serialización y deserialización. Tenga en cuenta que estas mismas condiciones se utilizan para describir la serialización y deserialización realizada por el nivel de transporte al formato de conexión del mensaje y desde este, que es un proceso no relacionado.  
  
 Puede utilizar un formateador de mensaje personalizado si necesita implementar una conversión especializada entre los mensajes y objetos que no puede lograr por medio de un Contrato de datos. Haga esto modificando o extendiendo el comportamiento de ejecución de una operación del contrato específica en un cliente o un servicio.  
  
## <a name="custom-message-formatters-on-the-client"></a>Formateadores de mensaje personalizados en el cliente  

 La interfaz  <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> Define métodos que se utilizan para controlar la conversión de mensajes en objetos y de objetos en mensajes para aplicaciones cliente.  
  
 Usted tan solo debe implementar la interfaz. Primero, invalide el método <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> para deserializar un mensaje. Se llama a este método una vez recibido un mensaje entrante, pero antes de enviarse a la operación del cliente.  
  
 A continuación, invalide el método <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> para serializar un objeto. Se llama a este método antes de enviar un mensaje saliente.  
  
 Para insertar el formateador personalizado en la aplicación de servicio, asigne el objeto <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> a la propiedad <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> utilizando un comportamiento de operación. Para obtener más información sobre los comportamientos, vea [configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="custom-message-formatters-on-the-service"></a>Formateadores de mensajes personalizados en el Servicio  

 La interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> define métodos que convierten un objeto <xref:System.ServiceModel.Channels.Message> en los parámetros para una operación y desde los parámetros en un objeto <xref:System.ServiceModel.Channels.Message> en una aplicación de servicio.  
  
 Usted tan solo debe implementar la interfaz. Primero, invalide el método <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> para deserializar un mensaje. Se llama a este método una vez recibido un mensaje entrante, pero antes de enviarse a la operación del cliente.  
  
 A continuación, invalide el método <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> para serializar un objeto. Se llama a este método antes de enviar un mensaje saliente.  
  
 Para insertar el formateador personalizado en la aplicación de servicio, asigne el objeto <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> a la propiedad <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> utilizando un comportamiento de operación. Para obtener más información sobre los comportamientos, vea [configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>
- [Configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md)
