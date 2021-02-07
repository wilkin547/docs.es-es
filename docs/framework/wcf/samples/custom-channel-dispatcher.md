---
description: 'Más información acerca de: distribuidor de canal personalizado'
title: Distribuidor de canal personalizado
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: cb56c21b540f359d78e71d8769e9f2d9ccf65a63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732597"
---
# <a name="custom-channel-dispatcher"></a>Distribuidor de canal personalizado

Este ejemplo muestra cómo crear la pila del canal de manera personalizada implementando <xref:System.ServiceModel.ServiceHostBase> directamente y cómo crear un distribuidor de canal personalizado en un entorno de host web. El distribuidor del canal interactúa con <xref:System.ServiceModel.Channels.IChannelListener> para aceptar los canales y recupera los mensajes de la pila del canal. Este ejemplo también proporciona un ejemplo básico para mostrar cómo integrar una pila del canal en un entorno de host web con <xref:System.ServiceModel.Activation.VirtualPathExtension>.  
  
## <a name="custom-servicehostbase"></a>ServiceHostBase personalizado  

 En este ejemplo se implementa el tipo base <xref:System.ServiceModel.ServiceHostBase> en lugar de <xref:System.ServiceModel.ServiceHost> para mostrar cómo reemplazar la implementación de la pila Windows Communication Foundation (WCF) con una capa de control de mensajes personalizada en la parte superior de la pila del canal. Se invalida el método virtual <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> para compilar los agentes de escucha del canal y el distribuidor de canal.  
  
 Para implementar un servicio hospedado en web, obtenga la extensión de servicio <xref:System.ServiceModel.Activation.VirtualPathExtension> de la colección de la propiedad <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> y agréguela al objeto <xref:System.ServiceModel.Channels.BindingParameterCollection> para que el nivel de transporte sepa cómo configurar el agente de escucha del canal según los valores de entorno de hospedaje, es decir, la configuración de Internet Information Services (IIS)/Servicio de activación de procesos de Windows (WAS).  
  
## <a name="custom-channel-dispatcher"></a>Distribuidor de canal personalizado  

 El distribuidor de canal personalizado extiende el tipo <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>. Este tipo implementa la lógica de programación del nivel del canal. En este ejemplo, solo se admite <xref:System.ServiceModel.Channels.IReplyChannel> para el patrón de intercambio de mensajes de solicitud-respuesta, pero el distribuidor del canal personalizado se puede extender con facilidad a otros tipos de canal.  
  
 El distribuidor abre el agente de escucha del canal primero y, a continuación, acepta el canal de respuesta singleton. Con el canal, empieza a enviar los mensajes (solicitudes) en un bucle infinito. Para cada solicitud, crea un mensaje de respuesta y lo envía de nuevo al cliente.  
  
## <a name="creating-a-response-message"></a>Crear un mensaje de respuesta  

 El procesamiento de mensajes se implementa en el tipo `MyServiceManager`. En el método `HandleRequest`, el encabezado de mensaje `Action` se comprueba primero para ver si se admite la solicitud. Se define una acción SOAP predefinida " http://tempuri.org/HelloWorld/Hello " para proporcionar el filtrado de mensajes. Esto es similar al concepto de contrato de servicio en la implementación de WCF de <xref:System.ServiceModel.ServiceHost> .  
  
 En el caso de la acción SOAP correcta, el ejemplo recupera los datos de mensaje solicitados y genera una respuesta correspondiente a la solicitud similar a lo que se ve en el caso de <xref:System.ServiceModel.ServiceHost>.  
  
 Para administrar el verbo HTTP-GET en especial, devuelve un mensaje HTML personalizado, en este caso, para que pueda examinar el servicio desde un explorador para ver que está compilado correctamente. Si la acción SOAP no coincide, envíe a un mensaje de error para indicar que no se admite la solicitud.  
  
 El cliente de este ejemplo es un cliente de WCF normal que no asume nada del servicio. Por lo tanto, el servicio está diseñado especialmente para coincidir con lo que se obtiene de una implementación de WCF normal <xref:System.ServiceModel.ServiceHost> . Como resultado, solo se requiere un contrato de servicio en el cliente.  
  
## <a name="using-the-sample"></a>Utilizar el ejemplo  

 Al ejecutar la aplicación cliente directamente, se genera el siguiente resultado.  
  
```output  
Client is talking to a request/reply WCF service.
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 También puede examinar el servicio desde un explorador para que se procese un mensaje HTTP-GET en el servidor. De esta forma obtiene de vuelta texto HTLM con formato correcto.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
