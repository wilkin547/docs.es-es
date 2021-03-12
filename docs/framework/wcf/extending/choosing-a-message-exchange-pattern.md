---
description: Más información acerca de cómo elegir un patrón de intercambio de mensajes
title: Elección de un patrón de intercambio de mensajes
ms.date: 03/30/2017
ms.assetid: 0f502ca1-6a8e-4607-ba15-59198c0e6146
ms.openlocfilehash: c0849ddb16596ebd6e064bb39f0727ac51642eb7
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605365"
---
# <a name="choosing-a-message-exchange-pattern"></a>Elección de un patrón de intercambio de mensajes

El primer paso para escribir un transporte personalizado es decidir qué *patrones de intercambio de mensajes* (o MEP) son necesarios para el canal que está desarrollando. Este tema describe las opciones disponibles y trata sobre los distintos requisitos. Esta es la primera tarea en la lista de tareas de desarrollo de canales que se describe en [desarrollar canales](developing-channels.md).  
  
## <a name="six-message-exchange-patterns"></a>Seis patrones de intercambio de mensajes  

 Hay tres MEP entre los que elegir:  
  
- Datagrama (<xref:System.ServiceModel.Channels.IInputChannel> y <xref:System.ServiceModel.Channels.IOutputChannel>)  
  
     Cuando se usa un MEP de datagrama, un cliente envía un mensaje mediante un *desencadenador y olvidó* Exchange. Un intercambio de este tipo es uno que exige una confirmación fuera de banda de entrega correcta. El mensaje se podría perderse por el camino y no llegar nunca al servicio. Si la operación de envío se completa correctamente en la parte del cliente, no garantiza que el extremo remoto haya recibido el mensaje. El datagrama es un bloque de creación fundamental para la mensajería, ya que puede crear sus propios protocolos encima de él, incluidos protocolos confiables y seguros. Los canales de datagrama del cliente implementan la interfaz <xref:System.ServiceModel.Channels.IOutputChannel> y los del servicio, la interfaz <xref:System.ServiceModel.Channels.IInputChannel>.  
  
- Solicitud-respuesta (<xref:System.ServiceModel.Channels.IRequestChannel> y <xref:System.ServiceModel.Channels.IReplyChannel>)  
  
     En este MEP, un mensaje se envía y se recibe una respuesta. El patrón está compuesto de los pares solicitud-respuesta. Los ejemplos de llamadas de solicitud-respuesta son llamadas a procedimientos remotos (RPC) y solicitudes GET del explorador. Este patrón también se conoce como dúplex medio. En este MEP, los canales de cliente implementan <xref:System.ServiceModel.Channels.IRequestChannel> y los canales de servicio <xref:System.ServiceModel.Channels.IReplyChannel>.  
  
- Dúplex (<xref:System.ServiceModel.Channels.IDuplexChannel>)  
  
     El MEP dúplex permite que un cliente envíe un número arbitrario de mensajes y que se reciban en cualquier orden. El MEP de dúplex es como una conversación telefónica, donde cada palabra que se pronuncia es un mensaje. Dado que ambos lados pueden enviar y recibir en este MEP, la interfaz implementada por los canales de servicio y cliente es <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
 ![Diagrama de flujo que muestra los tres patrones de intercambio de mensajes básicos](./media/wcfc-basicthreemepsc.gif)  
Los tres patrones de intercambio de mensajes básicos. De arriba abajo: datagrama, solicitud-respuesta y dúplex.  
  
 Cada uno de estos MEP también puede admitir *sesiones*. Una sesión (e implementación de <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType> de tipo <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>) pone en correlación todos los mensajes enviados y recibidos en un canal. El patrón de solicitud-respuesta es una sesión autónoma de dos mensajes, ya que la solicitud y la respuesta se ponen en correlación. Por el contrario, el patrón de solicitud-respuesta que admite las sesiones implica que se ponen en correlación todos los pares de solicitud/respuesta en ese canal entre sí. Esto le da un total de seis MEP entre los que elegir:  
  
- Datagrama  
  
- Solicitud-respuesta  
  
- Dúplex  
  
- Datagrama con sesiones  
  
- Solicitud-respuesta con sesiones  
  
- Dúplex con sesiones  
  
> [!NOTE]
> En el caso del transporte de UDP, el único MEP que se admite es el datagrama, ya que UDP es en sí mismo un protocolo de tipo desencadenar y omitir.  
  
## <a name="sessions-and-sessionful-channels"></a>Sesiones y canales con sesiones  

 En el mundo de red, hay protocolos orientado a la conexión (por ejemplo, TCP) y protocolos sin conexión (por ejemplo, UDP). WCF usa el término sesión para indicar una abstracción lógica similar a la de una conexión. Los protocolos WCF con sesión son similares a los protocolos de red orientados a la conexión y los protocolos WCF sin sesión son similares a los protocolos de red sin sesión.  
  
 En el modelo de objetos de canal, cada sesión lógica se manifiesta como una instancia de un canal con sesión. Por consiguiente, cada nueva sesión creada por el cliente y aceptada en el servicio se corresponde con un nuevo canal con sesión en cada lado. El siguiente diagrama muestra, en la parte superior, la estructura de los canales sin sesión y, en la parte inferior, la estructura de los canales con sesión.  
  
 ![Diagrama de flujo que muestra la estructura de los canales sin sesión y con sesión](./media/wcfc-sessionandsessionlesschannelsc.gif)  
  
 Un cliente crea un nuevo canal con sesión y envía un mensaje. En el lado del servicio, el agente de escucha del canal recibe este mensaje y detecta que pertenece a una nueva sesión de manera que crea un nuevo canal con sesión y lo une a la aplicación (en respuesta a la aplicación que llama a AcceptChannel en el agente de escucha del canal). La aplicación recibe a continuación este mensaje y todos los mensajes subsiguientes enviados en la misma sesión a través del mismo canal con sesión.  
  
 Otro cliente (o el mismo cliente) crea un nuevo canal con sesión y envía un mensaje. El agente de escucha del canal detecta que este mensaje está en una nueva sesión y crea un nuevo canal con sesión. El proceso se repite.  
  
 Sin las sesiones, no hay ninguna correlación entre los canales y ellas. Por consiguiente, un agente de escucha del canal crea solo un canal a través del cual se entregarán los mensajes recibidos a la aplicación. Tampoco hay un orden de mensajes porque no hay sesión dentro de la cual mantener el orden de los mensajes. La parte superior del gráfico anterior muestra un intercambio de mensajes sin sesión.  
  
## <a name="starting-and-terminating-sessions"></a>Inicio y finalización de sesiones  

 Para iniciar las sesiones en el cliente basta con crear un canal con sesión nuevo. Se inician en el servicio cuando recibe un mensaje que se envió en una nueva sesión. Igualmente, las sesiones se finalizan cerrando o anulando un canal con sesión.  
  
 La excepción a esto es <xref:System.ServiceModel.Channels.IDuplexSessionChannel> que se utiliza para enviar y recibir los mensajes en un patrón de comunicación con sesión dúplex. Es posible que un lado desee dejar de enviar los mensajes pero continuar recibiéndolos. Por tanto, cuando se use <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, habrá un mecanismo que le permitirá cerrar la sesión de salida que indicará que no enviará más mensajes pero que mantendrá la sesión de entrada abierta lo que le permitirá continuar recibiendo mensajes.  
  
 En general, las sesiones se cierran en el lado de salida y no en el de entrada. Es decir, los canales de salida con sesión pueden cerrarse, cerrando con ello la sesión. Cerrar un canal de salida con sesión provoca que el canal de entrada con sesión correspondiente devuelva el valor null a la aplicación que esté llamando a <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.  
  
 Sin embargo, los canales de entrada con sesión no deberían estar cerrados a menos que <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.Channels.IDuplexSessionChannel> devuelva el valor null, indicando que la sesión ya está cerrada. Si <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.Channels.IDuplexSessionChannel> no ha devuelto el valor null, cerrar un canal de entrada con sesión puede producir una excepción porque puede recibir mensajes inesperados al cerrarse. Si un receptor desea finalizar una sesión antes de que el remitente lo haga, debería llamar a <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en el canal de entrada, lo que terminaría la sesión bruscamente.  
  
## <a name="writing-sessionful-channels"></a>Creación de canales con sesión  

 Como autor del canal con sesión, hay algunas cosas que el canal deberá hacer para proporcionar sesiones. En el lado del envío, el canal tendrá que:  
  
- Para cada canal nuevo, crear una sesión nueva y asociarla a un identificador de sesión nuevo que sea una cadena única. U obtener una nueva sesión a partir del canal con sesión debajo de usted en la pila.  
  
- Para cada mensaje enviado utilizando este canal, si el canal creó la sesión (lo contrario a obtenerla de la capa debajo de usted), tendrá que asociar el mensaje con la sesión. Para los canales de protocolo, esto se realiza normalmente añadiendo un encabezado SOAP. En el caso de los canales de transporte, esto se hace normalmente creando una nueva conexión de transporte o agregando la información de sesión al protocolo de tramas.  
  
- Para cada mensaje enviado mediante este canal, necesita proporcionar las garantías de entrega mencionadas anteriormente. Si está confiando en el canal situado debajo de usted para proporcionar la sesión, ese canal también proporcionará las garantías de la entrega. Si está proporcionando la sesión usted mismo, necesita implementar esas garantías como parte del protocolo. En general, si está escribiendo un canal de protocolo que supone WCF en ambos lados, es posible que necesite el transporte de TCP o el canal de mensajería confiable y confíe en cualquier de ellos para proporcionar una sesión.  
  
- Cuando se llama a <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> en su canal, realice el trabajo necesario para cerrar la sesión mediante el tiempo de espera especificado o el valor predeterminado. Esto puede ser tan simple como llamar a <xref:System.ServiceModel.ICommunicationObject.Close%2A> en el canal debajo de usted (si acabara de obtener una sesión de él) o enviar un mensaje SOAP especial o cerrar una conexión de transporte.  
  
- Cuando se llama a <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en su canal, finalice la sesión bruscamente sin realizar E/S. Esto puede significar no hacer nada o puede suponer interrumpir la conexión de red o algún otro recurso.  
  
 En el lado de recepción, el canal tendrá que:  
  
- Para cada mensaje entrante, el agente de escucha debe detectar la sesión a la que pertenece. Si éste es el primer mensaje en la sesión, el agente de escucha del canal debe crear un nuevo canal y devolverlo desde la llamada a <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType>. De lo contrario, el agente de escucha del canal debe buscar el canal existente que corresponde a la sesión y entregar el mensaje a través de ese canal.  
  
- Si su canal proporciona la sesión (junto con las garantías de la entrega necesarias), es posible que se pida al lado de recepción que realice algunas acciones como volver a ordenar los mensajes y enviar confirmaciones.  
  
- Cuando se llama a <xref:System.ServiceModel.ICommunicationObject.Close%2A> en su canal, realice el trabajo necesario para cerrar la sesión mediante el tiempo de espera especificado o el valor predeterminado. Esto podría producir excepciones si el canal recibe un mensaje mientras espera que el tiempo de espera esté a punto de agotarse. Esto se debe a que el canal estará en estado de cierre cuando reciba un mensaje por lo que se producirá una.  
  
- Cuando se llama a <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en su canal, finalice la sesión bruscamente sin realizar E/S. De nuevo, esto puede significar no hacer nada o puede suponer interrumpir la conexión de red o algún otro recurso.  
  
## <a name="see-also"></a>Vea también

- [Información general del modelo de canales](channel-model-overview.md)
