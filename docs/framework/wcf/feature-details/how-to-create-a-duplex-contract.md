---
title: Procedimiento para crear un contrato dúplex
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: e5b6c7eecce08a23490b6ab1991e4561d9462469
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598988"
---
# <a name="how-to-create-a-duplex-contract"></a>Procedimiento para crear un contrato dúplex
En este tema se muestran los pasos básicos para crear métodos que utilicen un contrato dúplex (bidireccional). Un contrato dúplex permite a los clientes y servidores comunicarse entre sí independientemente de manera que cada uno puede iniciar llamadas al otro. El contrato dúplex es uno de tres patrones de mensajes disponibles para los servicios Windows Communication Foundation (WCF). Los otros dos patrones de mensaje son unidireccionales y de solicitud-respuesta. Un contrato dúplex consta de dos contratos unidireccionales entre el cliente y el servidor y no requiere que se pongan en correlación las llamadas al método. Use este tipo de contrato cuando el servicio debe consultar al cliente para obtener más información o provocar explícitamente eventos en el cliente. Para obtener más información sobre cómo crear una aplicación cliente para un contrato dúplex, consulte [Cómo: obtener acceso a los servicios con un contrato dúplex](how-to-access-services-with-a-duplex-contract.md). Para obtener un ejemplo funcional, vea el ejemplo [dúplex](../samples/duplex.md) .  
  
### <a name="to-create-a-duplex-contract"></a>Creación de un contrato dúplex  
  
1. Cree la interfaz que crea el lado del servidor del contrato dúplex.  
  
2. Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. Declare las firmas de los métodos en la interfaz.  
  
4. Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada firma de método que debe formar parte del contrato público.  
  
5. Cree la interfaz de devolución de llamada que define el conjunto de operaciones que el servicio puede invocar en el cliente.  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. Declare las firmas de métodos en la interfaz de devolución de llamadas.  
  
7. Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada firma de método que debe formar parte del contrato público.  
  
8. Vincule las dos interfaces en un contrato dúplex estableciendo la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> de la interfaz principal en el tipo de la interfaz de devolución de llamadas.  
  
### <a name="to-call-methods-on-the-client"></a>Realización de llamadas a métodos en el cliente  
  
1. En la implementación del servicio del contrato principal, declare una variable para la interfaz de devolución de llamadas.  
  
2. Establezca la variable en la referencia al objeto devuelta por el método <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> de la clase <xref:System.ServiceModel.OperationContext>.  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. Llame a los métodos definidos por la interfaz de devolución de llamadas.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código de ejemplo muestra la comunicación dúplex. El contrato del servicio contiene las operaciones del servicio para avanzar o retroceder. El contrato del cliente contiene una operación del servicio para informar sobre su posición.  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- La aplicación de los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> permite la generación automática de definiciones de contrato de servicios en el Lenguaje de descripción de servicios Web (WSDL).  
  
- Use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para recuperar el documento WSDL y el código (opcional) y la configuración de un cliente.  
  
- Se deben proteger los extremos que exponen servicios dúplex. Cuando un servicio recibe un mensaje dúplex, examina el elemento ReplyTo en ese mensaje entrante para determinar a dónde enviar la respuesta. Si no se protege el canal, un cliente que no es de confianza podría enviar un mensaje malintencionado con un ReplyTo del equipo de destino, provocando una denegación de servicio del equipo de destino. Esto no es un problema con mensajes de solicitud-respuesta normales, porque el ReplyTo se pasa por alto y se envía la respuesta al canal en el que entró el mensaje original.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Procedimiento para obtener acceso a los servicios con un contrato dúplex](how-to-access-services-with-a-duplex-contract.md)
- [Dúplex](../samples/duplex.md)
- [Diseño e implementación de servicios](../designing-and-implementing-services.md)
- [Cómo definir un contrato de servicios](../how-to-define-a-wcf-service-contract.md)
- [Sesión](../samples/session.md)
