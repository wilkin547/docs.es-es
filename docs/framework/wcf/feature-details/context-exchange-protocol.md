---
title: Protocolo de intercambio de contexto
ms.date: 03/30/2017
ms.assetid: 3dfd38e0-ae52-491c-94f4-7a862b9843d4
ms.openlocfilehash: ba613a2d12843ad00034057f8bbf08d5357d7f04
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237825"
---
# <a name="context-exchange-protocol"></a>Protocolo de intercambio de contexto

En esta sección se describe el protocolo de intercambio de contexto incluido en Windows Communication Foundation (WCF) versión .NET Framework versión 3,5. Este protocolo permite al canal de cliente que acepte un contexto proporcionado por un servicio y que lo aplique a todas las solicitudes posteriores a ese servicio enviado sobre la misma instancia del canal de cliente. La implementación del protocolo de intercambio de contexto puede utilizar uno de los dos mecanismos siguientes para propagar el contexto entre el servidor y el cliente: cookies de HTTP o un encabezado SOAP.  
  
 El protocolo de intercambio de contexto se implementa en una capa de canal personalizada. El canal comunica el contexto a y desde el nivel de aplicación utilizando una propiedad <xref:System.ServiceModel.Channels.ContextMessageProperty>. Para la transmisión entre extremos, el valor del contexto se serializa como un encabezado SOAP en la capa de canal o convertido a o desde las propiedades de mensaje que representan una solicitud y respuesta HTTP. En el último caso, se espera que una de las capas del canal subyacentes convierta las propiedades de mensajes de solicitud y respuesta HTTP a y desde cookies HTTP, respectivamente. La opción del mecanismo utilizado para intercambiar el contexto se realiza mediante la propiedad <xref:System.ServiceModel.Channels.ContextExchangeMechanism> en el <xref:System.ServiceModel.Channels.ContextBindingElement>. Los valores válidos son `HttpCookie` y `SoapHeader`.  
  
 En el cliente, una instancia de un canal puede funcionar de dos modos en función de los valores de la propiedad de canal, <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A>.  
  
## <a name="mode-1-channel-context-management"></a>Modo 1: administración del contexto del canal  

 Éste es el modo predeterminado donde <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> está establecido en `true`. En este modo, el canal del contexto administra el contexto y lo almacena en memoria caché durante su duración. El contexto se puede recuperar desde el canal mediante la propiedad de canal `IContextManager` llamando al método `GetContext`. El canal también se puede preinicializar con contexto concreto antes de abrirse llamando al método `SetContext` en la propiedad de canal. Una vez inicializado el canal con contexto no se puede restablecer.  
  
 A continuación, se muestra una lista de invariables en este modo:  
  
- Cualquier intento de restablecer el contexto mediante `SetContext` una vez abierto el canal inicia una <xref:System.InvalidOperationException>.  
  
- Cualquier intento de enviar el contexto utilizando la <xref:System.ServiceModel.Channels.ContextMessageProperty> en un mensaje saliente inicia una <xref:System.InvalidOperationException>.  
  
- Si un mensaje se recibe del servidor con un contexto concreto, cuando el canal ya se ha inicializado con un contexto concreto, se produce una <xref:System.ServiceModel.ProtocolException>.  
  
    > [!NOTE]
    > Es adecuado recibir un contexto inicial desde el servidor solo si el canal se abre sin ningún contexto establecido explícitamente.  
  
- <xref:System.ServiceModel.Channels.ContextMessageProperty> en un mensaje entrante siempre es null.  
  
## <a name="mode-2-application-context-management"></a>Modo 2: administración de contexto de aplicación  

 Éste es el modo cuando <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> se establece en `false`. En este modo el canal de contexto no administra contexto. Es responsabilidad de la aplicación el recuperar, administrar y aplicar el contexto utilizando la <xref:System.ServiceModel.Channels.ContextMessageProperty>. Cualquier intento de llamar al método `GetContext` o `SetContext` produce una <xref:System.InvalidOperationException>.  
  
 Independientemente del modo elegido, el generador de canales de cliente admite patrones de intercambio de mensajes <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.  
  
 En el servicio, una instancia del canal es responsable de convertir el contexto proporcionado por el cliente en los mensajes entrantes a la <xref:System.ServiceModel.Channels.ContextMessageProperty>. A continuación, el nivel de aplicación u otros canales pueden tener acceso a la propiedad de mensaje más arriba en la pila de llamadas. Los canales de servicio también permiten al nivel de aplicación especificar un nuevo valor de contexto se propagará de vuelta al cliente adjuntando una <xref:System.ServiceModel.Channels.ContextMessageProperty> al mensaje de respuesta. Esta propiedad se convierte en el encabezado SOAP o en cookie HTTP que contiene el contexto, que depende de la configuración del enlace. El agente de escuchas del canal de servicio admite patrones de intercambio de mensajes <xref:System.ServiceModel.Channels.IReplyChannel>, <xref:System.ServiceModel.Channels.IReplySessionChannel> y <xref:System.ServiceModel.Channels.IReplySessionChannel>.  
  
 El protocolo de intercambio de contexto introduce un nuevo encabezado SOAP `wsc:Context` para representar las información de contexto cuando no se utilizan cookies HTTP para propagar el contexto. El esquema de encabezado de contexto permite un número ilimitado de elementos secundarios, cada uno con una clave de cadena y contenido de cadena. A continuación se muestra un ejemplo del encabezado de contexto:  
  
 `<Context xmlns="http://schemas.microsoft.com/ws/2006/05/context">`  
  
 `<property name="myContext">context-2</property>`  
  
 `</Context>`  
  
 Cuando se encuentra en modo `HttpCookie`, las cookies se establecen utilizando el encabezado `SetCookie`. El nombre de la cookie es `WscContext`. El valor de la cookie es la codificación Base64 del encabezado `wsc:Context`. Este valor se encierra entre comillas.  
  
 El valor del contexto debe protegerse contra modificaciones mientras esté en tránsito por la misma razón que se protegen los encabezados WS-Addressing; el encabezado se utiliza para determinar a dónde enviar la solicitud en el servicio. El encabezado `wsc:Context` se exige por consiguiente que esté firmado digitalmente o firmado y cifrado en el nivel de transporte o SOAP cuando el enlace ofrece la capacidad de protección de mensajes. Cuando se utilizan cookies HTTP para propagar contexto, deben protegerse utilizando la seguridad de transporte.  
  
 Los puntos de conexión de servicio que requieren compatibilidad con respecto al protocolo de intercambio de contexto pueden hacerlo explícito en la directiva publicada. Se han introducido dos nuevas aserciones de directivas para representar el requisito de que el cliente admita el protocolo de intercambio de contexto en el nivel de SOAP o de que habilite la compatibilidad con cookies HTTP. La generación de estas aserciones en la directiva en el servicio está controlada por el valor de la propiedad <xref:System.ServiceModel.Channels.ContextBindingElement.ContextExchangeMechanism%2A>, como se muestra a continuación:  
  
- Para <xref:System.ServiceModel.Channels.ContextExchangeMechanism.ContextSoapHeader>, se genera la siguiente aserción:  
  
    ```xml  
    <IncludeContext
    xmlns="http://schemas.microsoft.com/ws/2006/05/context"  
    protectionLevel="Sign" />  
    ```  
  
- Para <xref:System.ServiceModel.Channels.ContextExchangeMechanism.HttpCookie>, se genera la siguiente aserción:  
  
    ```xml  
    <HttpUseCookie xmlns="http://schemas.xmlsoap.org/soap/http"/>  
    ```  
  
## <a name="see-also"></a>Vea también

- [Guía de interoperabilidad de los protocolos de servicios web](web-services-protocols-interoperability-guide.md)
