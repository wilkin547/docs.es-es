---
description: 'Más información sobre: actividades de mensajería'
title: Actividades de mensajería
ms.date: 03/30/2017
ms.assetid: 8498f215-1823-4aba-a6e1-391407f8c273
ms.openlocfilehash: fc98081cabc552cd51bf35db3bed9443220fc065
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756076"
---
# <a name="messaging-activities"></a>Actividades de mensajería

Las actividades de mensajería permiten a los flujos de trabajo enviar y recibir mensajes de WCF. Al agregar actividades de mensajería a un flujo de trabajo, puede modelar cualquier patrón de intercambio de mensajes (MEP) arbitrariamente complejo.

## <a name="message-exchange-patterns"></a>Patrones de intercambio de mensajes

Hay tres patrones de intercambio de mensajes básicos:

- **Datagram** : cuando se usa el datagrama MEP, el cliente envía un mensaje al servicio, pero el servicio no responde. Esto se llama a veces "fire and forget" (dispare y olvídese). Un intercambio de este tipo es uno que exige una confirmación fuera de banda de entrega correcta. El mensaje se podría perderse por el camino y no llegar nunca al servicio. El hecho de que el cliente envíe un mensaje correctamente no garantiza que el servicio haya recibido el mensaje. El datagrama es una unidad de creación fundamental para la mensajería, ya que puede compilar sus propios MEP sobre él.

- **Solicitud-respuesta** : cuando se usa el MEP de solicitud-respuesta, el cliente envía un mensaje al servicio, el servicio realiza el procesamiento requerido y, a continuación, envía una respuesta de vuelta al cliente. El patrón está compuesto de los pares solicitud-respuesta. Los ejemplos de llamadas de solicitud-respuesta son llamadas a procedimientos remotos (RPC) y solicitudes GET del explorador. Este patrón también se conoce como dúplex medio.

- **Dúplex** : cuando se usa el MEP dúplex, el cliente y el servicio pueden enviar mensajes entre sí en cualquier orden. El MEP de dúplex es como una conversación telefónica, donde cada palabra que se pronuncia es un mensaje.

Las actividades de mensajería le permiten implementar cualquiera de estos MEP básicos, así como cualquier MEP arbitrariamente complejo.

## <a name="messaging-activities"></a>Actividades de mensajería

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] define las siguientes actividades de mensajería:

- <xref:System.ServiceModel.Activities.Send>: Use la actividad <xref:System.ServiceModel.Activities.Send> para enviar un mensaje.

- <xref:System.ServiceModel.Activities.SendReply>: Utilice la actividad <xref:System.ServiceModel.Activities.SendReply> para enviar una respuesta a un mensaje recibido. Esta actividad la emplean los servicios de flujo de trabajo al implementar un MEP de solicitud/respuesta.

- <xref:System.ServiceModel.Activities.Receive>: Use la actividad <xref:System.ServiceModel.Activities.Receive> para recibir un mensaje.

- <xref:System.ServiceModel.Activities.ReceiveReply>: Use la actividad <xref:System.ServiceModel.Activities.ReceiveReply> para recibir un mensaje de respuesta. Esta actividad la emplean los clientes de servicios de flujo de trabajo al implementar un MEP de solicitud/respuesta.

## <a name="messaging-activities-and-message-exchange-patterns"></a>Actividades de mensajería y patrones de intercambio de mensajes

Un MEP de datagrama implica que un cliente envía un mensaje y un servicio recibe el mensaje. Si el cliente es un uso del flujo de trabajo, use una actividad <xref:System.ServiceModel.Activities.Send> para enviar el mensaje. Para recibir ese mensaje en un flujo de trabajo, use una actividad <xref:System.ServiceModel.Activities.Receive>. Cada una de las actividades <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive> tiene una propiedad denominada `Content`. Esta propiedad contiene los datos que se envían o se reciben. Al implementar el MEP de solicitud-respuesta, tanto el cliente como el servicio usan pares de actividades. El cliente usa una actividad <xref:System.ServiceModel.Activities.Send> para enviar al mensaje y a una actividad <xref:System.ServiceModel.Activities.ReceiveReply> para recibir la respuesta del servicio. La propiedad <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> asocia entre sí estas dos actividades. Esta propiedad está establecida en la actividad <xref:System.ServiceModel.Activities.Send> que envió el mensaje original. El servicio también usa un par de actividades asociadas: <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>. La propiedad <xref:System.ServiceModel.Activities.SendReply.Request%2A> asocia estas dos actividades. Esta propiedad está establecida en la actividad <xref:System.ServiceModel.Activities.Receive> que recibió el mensaje original. Las actividades <xref:System.ServiceModel.Activities.ReceiveReply> y <xref:System.ServiceModel.Activities.SendReply>, como <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive>, le permiten enviar una instancia <xref:System.ServiceModel.Channels.Message> o un tipo de contrato de mensaje.

Debido a la naturaleza de ejecución prolongada de los flujos de trabajo, es importante que el patrón dúplex de comunicación también admita las conversaciones de ejecución prolongada. Para admitir conversaciones de ejecución prolongada, los clientes que inician la conversación deben proporcionar el servicio con una oportunidad de volver a llamarlo posteriormente cuando los datos estén disponibles. Por ejemplo, se envía una solicitud de pedido de compra para la aprobación del administrador, pero podría no procesarse durante un día, una semana, o incluso un año; el flujo de trabajo que administra la aprobación del pedido de compra debe saber reanudar una vez otorgada la aprobación. Este patrón de comunicación dúplex se admite en flujos de trabajo que usan correlación. Para implementar un patrón dúplex, use las actividades <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive>. En la <xref:System.ServiceModel.Activities.Receive> actividad, inicialice una correlación mediante <xref:System.ServiceModel.Activities.CorrelationHandle> . En la actividad <xref:System.ServiceModel.Activities.Send>, establezca ese controlador de correlación como valor de propiedad <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>. Para obtener más información, consulte [dúplex duradero](durable-duplex-correlation.md).

> [!NOTE]
> La implementación del flujo de trabajo de dúplex mediante una correlación de devolución de llamada ("dúplex duradero") está pensada para conversaciones de ejecución prolongada. Esto no es igual que el dúplex de WCF con contratos de devolución de llamada, donde la conversación es de ejecución reducida (la duración del canal).

## <a name="message-formatting-and-messaging-activities"></a>Formato de mensajes y actividades de mensajería

Las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.ReceiveReply> tienen una propiedad denominada `Content`. Esta propiedad es del tipo <xref:System.ServiceModel.Activities.ReceiveContent> y representa los datos que recibe la actividad <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.ReceiveReply>. El sistema .NET Framework define dos clases relacionadas denominadas <xref:System.ServiceModel.Activities.ReceiveMessageContent> y <xref:System.ServiceModel.Activities.ReceiveParametersContent>, que se derivan de <xref:System.ServiceModel.Activities.ReceiveContent>. Establezca la propiedad <xref:System.ServiceModel.Activities.Receive> de la actividad <xref:System.ServiceModel.Activities.ReceiveReply> o `Content` en una instancia de uno de estos tipos para recibir datos en un servicio de flujo de trabajo. El tipo que se va a usar depende del tipo de datos que recibe la actividad. Si la actividad recibe un objeto `Message` o un tipo de contrato de mensaje, use <xref:System.ServiceModel.Activities.ReceiveMessageContent>. Si la actividad recibe un conjunto de contrato de datos o tipos de XML que se puede serializar, use <xref:System.ServiceModel.Activities.ReceiveParametersContent>. <xref:System.ServiceModel.Activities.ReceiveParametersContent> le permite enviar varios parámetros, mientras que <xref:System.ServiceModel.Activities.ReceiveMessageContent> solo permite enviar un objeto, el mensaje (o tipo de contrato de mensaje).

> [!NOTE]
> <xref:System.ServiceModel.Activities.ReceiveMessageContent> también se puede utilizar con un contrato de datos único o un tipo de XML que se puede serializar. La diferencia entre utilizar la clase <xref:System.ServiceModel.Activities.ReceiveParametersContent> con un parámetro único y el objeto pasado directamente a <xref:System.ServiceModel.Activities.ReceiveMessageContent> es el formato de conexión. El contenido del parámetro se ajusta en un elemento XML que corresponde al nombre de la operación, y el objeto serializado se ajusta en un elemento XML mediante el nombre de parámetro (por ejemplo, `<Echo><msg>Hello, World</msg></Echo>`). El nombre de la operación no ajusta el contenido del mensaje. En su lugar, el objeto serializado se coloca dentro de un elemento XML mediante el nombre de tipo XML completo (por ejemplo, `<string>Hello, World</string>`).

Las actividades <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.SendReply> también tienen una propiedad denominada `Content`. Esta propiedad es del tipo <xref:System.ServiceModel.Activities.SendContent> y representa datos que envía la actividad <xref:System.ServiceModel.Activities.Send> o <xref:System.ServiceModel.Activities.SendReply>. El sistema .NET Framework define dos tipos relacionados denominados <xref:System.ServiceModel.Activities.SendMessageContent> y <xref:System.ServiceModel.Activities.SendParametersContent>, que se derivan de <xref:System.ServiceModel.Activities.SendContent>. Establezca la propiedad <xref:System.ServiceModel.Activities.Send> de la actividad <xref:System.ServiceModel.Activities.SendReply> o `Content` en una instancia de uno de estos tipos para enviar datos de un servicio de flujo de trabajo. El tipo que se va a usar depende del tipo de datos que envía la actividad. Si la actividad envía un objeto `Message` o un tipo de contrato de mensaje, use <xref:System.ServiceModel.Activities.SendMessageContent>. Si la actividad envía un tipo de contrato de datos, use <xref:System.ServiceModel.Activities.SendParametersContent>. <xref:System.ServiceModel.Activities.SendParametersContent> le permite enviar varios parámetros, mientras que <xref:System.ServiceModel.Activities.SendMessageContent> solo permite enviar un objeto, el mensaje (o tipo de contrato de mensaje).

Al programar imperiosamente con las actividades de mensajería, use <xref:System.Activities.InArgument%601> y <xref:System.Activities.OutArgument%601> de forma genérica para ajustar los objetos asignados al mensaje o las propiedades de parámetros de las actividades <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.ReceiveReply>. Se usa <xref:System.Activities.InArgument%601> para <xref:System.ServiceModel.Activities.Send> las <xref:System.ServiceModel.Activities.SendReply> actividades y, y <xref:System.Activities.OutArgument%601> para las <xref:System.ServiceModel.Activities.Receive> <xref:System.ServiceModel.Activities.ReceiveReply> actividades y. Los argumentos `In` se usan con las actividades de envío porque los datos se pasan a las actividades. Los argumentos `Out` se usan con las actividades de recepción porque se pasan datos de las actividades, como se muestra en el ejemplo siguiente.

```csharp
Receive reserveSeat = new Receive
{
    ...
    Content = new ReceiveParametersContent
    {
        Parameters =
        {
            { "ReservationInfo", new OutArgument<ReservationRequest>(reservationInfo) }
        }
    }
};
SendReply reserveSeat = new SendReply
{
    ...
    Request = reserveSeat,
    Content = new SendParametersContent
    {
        Parameters =
        {
            { "ReservationId", new InArgument<string>(reservationId) }
        }
    },
};
```

Al implementar un servicio de flujo de trabajo que define una operación de solicitud/respuesta que devuelve un valor nulo, debe crear instancias de una actividad <xref:System.ServiceModel.Activities.SendReply> y establecer la propiedad <xref:System.ServiceModel.Activities.SendReply.Content%2A> en una instancia vacía de uno de los tipos de contenido (<xref:System.ServiceModel.Activities.SendMessageContent> o <xref:System.ServiceModel.Activities.SendParametersContent>), tal y como se muestra en el siguiente ejemplo.

```csharp
Receive rcv = new Receive()
{
ServiceContractName = "IService",
OperationName = "NullReturningContract",
Content = new ReceiveParametersContent( new Dictionary<string, OutArgument>() { { "message", new OutArgument<string>() } } )
};
SendReply sr = new SendReply()
{
Request = rcv
   Content = new SendParametersContent();
};
```

## <a name="add-service-reference"></a>Agregar referencia de servicio

Cuando se llama a un servicio de flujo de trabajo desde una aplicación de flujo de trabajo, Visual Studio 2012 genera actividades de mensajería personalizadas que encapsulan las <xref:System.ServiceModel.Activities.Send> actividades habituales y <xref:System.ServiceModel.Activities.ReceiveReply> utilizadas en un MEP de solicitud/respuesta. Para usar esta característica, haga clic con el botón derecho en el proyecto de cliente en Visual Studio y seleccione **Agregar**  >  **referencia de servicio**. Escriba la dirección base del servicio en el cuadro de dirección y haga clic en Ir. Los servicios disponibles se muestran en el cuadro **servicios:** . Expanda el nodo de servicio para mostrar los contratos admitidos. Seleccione el contrato al que desea llamar y la lista de operaciones disponibles se muestra en el cuadro **operaciones** . Después, puede especificar el espacio de nombres para la actividad generada y hacer clic en **Aceptar**. A continuación, verá un cuadro de diálogo que dice que la operación se ha completado correctamente y que las actividades personalizadas generadas se encontrarán en el cuadro de herramientas tras haber recompilado el proyecto. Hay una actividad para cada operación definida en el contrato de servicios. Después de recompilar el proyecto, puede arrastrar y colocar las actividades personalizadas en el flujo de trabajo y establecer cualquier propiedad necesaria en la ventana Propiedades.

## <a name="messaging-activity-templates"></a>Plantillas de actividad de mensajería

Para facilitar la configuración de un MEP de solicitud/respuesta en el cliente y el servicio, Visual Studio 2012 proporciona dos plantillas de actividad de mensajería. `System.ServiceModel.Activities.Design.ReceiveAndSendReply` se usa en el servicio y `System.ServiceModel.Activities.Design.SendAndReceiveReply` se usa en el cliente. En ambos casos, las plantillas agregan las actividades de mensajería adecuadas al flujo de trabajo. En el servicio, `System.ServiceModel.Activities.Design.ReceiveAndSendReply` agrega una actividad <xref:System.ServiceModel.Activities.Receive> seguida por una actividad <xref:System.ServiceModel.Activities.SendReply>. La propiedad <xref:System.ServiceModel.Activities.SendReply.Request> se establece en la actividad <xref:System.ServiceModel.Activities.Receive> de forma automática. En el cliente, `System.ServiceModel.Activities.Design.SendAndReceiveReply` agrega una actividad <xref:System.ServiceModel.Activities.Send> seguida por <xref:System.ServiceModel.Activities.ReceiveReply>. La propiedad <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> se establece en la actividad <xref:System.ServiceModel.Activities.Send> de forma automática. Para utilizar estas plantillas, simplemente arrastre y coloque la plantilla adecuada en el flujo de trabajo.

## <a name="messaging-activities-and-transactions"></a>Actividades de mensajería y transacciones

Cuando se realiza una llamada a un servicio de flujo de trabajo, puede desear hacer fluir una transacción a una operación del servicio. Para ello, coloque la actividad <xref:System.ServiceModel.Activities.Receive> dentro de una actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope>. La actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope> contiene una actividad `Receive` y un cuerpo. La transacción que ha fluido al servicio permanece ambiente a lo largo de la ejecución del cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Se completa la transacción cuando el cuerpo termina de ejecutarse. Para obtener más información acerca de los flujos de trabajo y las transacciones, consulte [transacciones de flujo de trabajo](../../windows-workflow-foundation/workflow-transactions.md).

## <a name="see-also"></a>Vea también

- [Enviar y recibir errores en los servicios de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=189151)
- [Crear un servicio de flujo de trabajo de larga ejecución](creating-a-long-running-workflow-service.md)
