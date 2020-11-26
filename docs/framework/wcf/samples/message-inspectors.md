---
title: Inspectores de mensaje
description: Obtenga información sobre cómo implementar y configurar los inspectores de mensajes de servicio y de cliente de WCF, que proporcionan un mecanismo de validación de mensajes.
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 4b2f7b97d0895e3cb7550217f64a2b0b14545abf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240711"
---
# <a name="message-inspectors"></a><span data-ttu-id="775db-103">Inspectores de mensaje</span><span class="sxs-lookup"><span data-stu-id="775db-103">Message Inspectors</span></span>

<span data-ttu-id="775db-104">Este ejemplo muestra cómo implementar y configurar los inspectores de mensaje de cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-104">This sample demonstrates how to implement and configure client and service message inspectors.</span></span>  
  
 <span data-ttu-id="775db-105">Un inspector del mensaje es un objeto de extensibilidad que se puede utilizar en el cliente del modelo del servicio en tiempo de ejecución y enviarse mediante programación en tiempo de ejecución o a través de configuración, y que puede inspeccionar y modificar los mensajes una vez recibidos o antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="775db-105">A message inspector is an extensibility object that can be used in the service model's client runtime and dispatch runtime programmatically or through configuration and that can inspect and alter messages after they are received or before they are sent.</span></span>  
  
 <span data-ttu-id="775db-106">Este ejemplo implementa un cliente básico y un mecanismo de validación de mensaje de servicio que valida los mensajes entrantes contra un conjunto de documentos de esquema XML configurables.</span><span class="sxs-lookup"><span data-stu-id="775db-106">This sample implements a basic client and service message validation mechanism that validates incoming messages against a set of configurable XML Schema documents.</span></span> <span data-ttu-id="775db-107">Tenga en cuenta que este ejemplo no valida los mensajes para cada operación.</span><span class="sxs-lookup"><span data-stu-id="775db-107">Note that this sample does not validate messages for each operation.</span></span> <span data-ttu-id="775db-108">Esta es una simplificación intencional.</span><span class="sxs-lookup"><span data-stu-id="775db-108">This is an intentional simplification.</span></span>  
  
## <a name="message-inspector"></a><span data-ttu-id="775db-109">Inspector de mensajes</span><span class="sxs-lookup"><span data-stu-id="775db-109">Message Inspector</span></span>  

 <span data-ttu-id="775db-110">Los inspectores de mensaje de cliente implementan la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> y los inspectores de mensaje de servicio implementan la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>.</span><span class="sxs-lookup"><span data-stu-id="775db-110">Client message inspectors implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> interface and service message inspectors implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> interface.</span></span> <span data-ttu-id="775db-111">Las implementaciones se pueden combinar en una clase única para formar un inspector de mensaje que trabaja para ambas partes.</span><span class="sxs-lookup"><span data-stu-id="775db-111">The implementations can be combined into a single class to form a message inspector that works for both sides.</span></span> <span data-ttu-id="775db-112">Este ejemplo implementa este tipo de inspector de mensaje combinado.</span><span class="sxs-lookup"><span data-stu-id="775db-112">This sample implements such a combined message inspector.</span></span> <span data-ttu-id="775db-113">El inspector se construye transmitiendo un conjunto de esquemas sobre la base de qué mensajes entrantes y salientes se validan, y permite al programador especificar si se validan los mensajes entrantes o salientes y si el inspector está en modo cliente o envío, el cual afecta al control de errores tal y como se analiza después en este tema.</span><span class="sxs-lookup"><span data-stu-id="775db-113">The inspector is constructed passing in a set of schemas against which incoming and outgoing messages are validated and allows the developer to specify whether incoming or outgoing messages are validated and whether the inspector is in dispatch or client mode, which affects the error handling as discussed later in this topic.</span></span>  
  
```csharp
public class SchemaValidationMessageInspector : IClientMessageInspector, IDispatchMessageInspector  
{  
    XmlSchemaSet schemaSet;  
    bool validateRequest;  
    bool validateReply;  
    bool isClientSide;  
    [ThreadStatic]  
    bool isRequest;  
  
    public SchemaValidationMessageInspector(XmlSchemaSet schemaSet,  
         bool validateRequest, bool validateReply, bool isClientSide)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = validateReply;  
        this.validateRequest = validateRequest;  
        this.isClientSide = isClientSide;  
    }  
```  
  
 <span data-ttu-id="775db-114">Todos los inspectores de mensaje de servicio (distribuidor) deben implementar los dos métodos <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> y <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="775db-114">Any service (dispatcher) message inspector must implement the two <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> methods <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span></span>  
  
 <span data-ttu-id="775db-115">El distribuidor invoca <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> cuando se ha recibido un mensaje, la pila del canal lo ha procesado y se ha asignado a un servicio, pero antes de que sea deserializado y enviado a una operación.</span><span class="sxs-lookup"><span data-stu-id="775db-115"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> is invoked by the dispatcher when a message has been received, processed by the channel stack and assigned to a service, but before it is deserialized and dispatched to an operation.</span></span> <span data-ttu-id="775db-116">Si el mensaje entrante está cifrado, se descifra cuando llega al inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="775db-116">If the incoming message was encrypted, the message is already decrypted when it reaches the message inspector.</span></span> <span data-ttu-id="775db-117">El método obtiene el mensaje `request` pasado como un parámetro de referencia, que permite inspeccionar el mensaje, manipularlo o reemplazarlo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="775db-117">The method gets the `request` message passed as a reference parameter, which allows the message to be inspected, manipulated or replaced as required.</span></span> <span data-ttu-id="775db-118">El valor devuelto puede ser cualquier objeto y se utiliza como un objeto de estado de correlación que se pasa a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> cuando el servicio devuelve una respuesta al mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="775db-118">The return value can be any object and is used as a correlation state object that is passed to <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> when the service returns a reply to the current message.</span></span> <span data-ttu-id="775db-119">En este ejemplo, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delega la inspección (validación) del mensaje al método `ValidateMessageBody` , privado y local, y no devuelve ningún objeto de estado de correlación.</span><span class="sxs-lookup"><span data-stu-id="775db-119">In this sample, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delegates the inspection (validation) of the message to the private, local method `ValidateMessageBody` and returns no correlation state object.</span></span> <span data-ttu-id="775db-120">Este método asegura que ningún mensaje no válido pase al servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-120">This method ensures that no invalid messages pass into the service.</span></span>  
  
```csharp  
object IDispatchMessageInspector.AfterReceiveRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel, System.ServiceModel.InstanceContext instanceContext)  
{  
    if (validateRequest)  
    {  
        // inspect the message. If a validation error occurs,  
        // the thrown fault exception bubbles up.  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="775db-121">Se invoca <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> siempre que una respuesta está lista para ser devuelta a un cliente o en el caso de mensajes unidireccionales, cuando se ha procesado el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="775db-121"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> is invoked whenever a reply is ready to be sent back to a client, or in the case of one-way messages, when the incoming message has been processed.</span></span> <span data-ttu-id="775db-122">Esto permite a las extensiones contar con que se les llame simétricamente, sin tener en cuenta el MEP.</span><span class="sxs-lookup"><span data-stu-id="775db-122">This allows extensions to count on being called symmetrically, regardless of MEP.</span></span> <span data-ttu-id="775db-123">Al igual que con <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, el mensaje se pasa como un parámetro de referencia y se puede inspeccionar, modificar o reemplazar.</span><span class="sxs-lookup"><span data-stu-id="775db-123">As with <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, the message is passed as a reference parameter and can be inspected, modified or replaced.</span></span> <span data-ttu-id="775db-124">La validación del mensaje que se realiza en este ejemplo se delega de nuevo al método `ValidMessageBody`, pero el control de errores de validación es ligeramente diferente en este caso.</span><span class="sxs-lookup"><span data-stu-id="775db-124">The validation of the message that is performed in this sample is again delegated to the `ValidMessageBody` method, but the handling of validation errors is slightly different in this case.</span></span>  
  
 <span data-ttu-id="775db-125">Si se produce un error de validación en el servicio, el método `ValidateMessageBody` inicia <xref:System.ServiceModel.FaultException>- excepciones derivadas.</span><span class="sxs-lookup"><span data-stu-id="775db-125">If a validation error occurs on the service, the `ValidateMessageBody` method throws <xref:System.ServiceModel.FaultException>-derived exceptions.</span></span> <span data-ttu-id="775db-126">En <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, estas excepciones se pueden colocar en la infraestructura modelo del servicio, donde se transforman automáticamente en errores SOAP y se transmiten al cliente.</span><span class="sxs-lookup"><span data-stu-id="775db-126">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, these exceptions can be put into the service model infrastructure where they are automatically transformed into SOAP faults and relayed to the client.</span></span> <span data-ttu-id="775db-127">En <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, las excepciones <xref:System.ServiceModel.FaultException> no se deben colocar en la infraestructura, porque la transformación de excepciones de error iniciada por el servicio se produce antes de llamar al inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="775db-127">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, <xref:System.ServiceModel.FaultException> exceptions must not be put into the infrastructure, because the transformation of fault exceptions thrown by the service occurs before the message inspector is called.</span></span> <span data-ttu-id="775db-128">Por consiguiente, la implementación siguiente detecta la excepción `ReplyValidationFault` conocida y reemplaza el mensaje de respuesta con un mensaje de error explícito.</span><span class="sxs-lookup"><span data-stu-id="775db-128">Therefore the following implementation catches the known `ReplyValidationFault` exception and replaces the reply message with an explicit fault message.</span></span> <span data-ttu-id="775db-129">Este método asegura que la implementación del servicio no devuelve ningún mensaje no válido.</span><span class="sxs-lookup"><span data-stu-id="775db-129">This method ensures that no invalid messages are returned by the service implementation.</span></span>  
  
```csharp  
void IDispatchMessageInspector.BeforeSendReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        // Inspect the reply, catch a possible validation error
        try  
        {  
            ValidateMessageBody(ref reply, false);  
        }  
        catch (ReplyValidationFault fault)  
        {  
            // if a validation error occurred, the message is replaced  
            // with the validation fault.  
            reply = Message.CreateMessage(reply.Version,
                    fault.CreateMessageFault(), reply.Headers.Action);  
        }  
    }  
```  
  
 <span data-ttu-id="775db-130">El inspector de mensaje de cliente es muy similar.</span><span class="sxs-lookup"><span data-stu-id="775db-130">The client message inspector is very similar.</span></span> <span data-ttu-id="775db-131">Los dos métodos que se deben implementar de <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> son <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> y <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span><span class="sxs-lookup"><span data-stu-id="775db-131">The two methods that must be implemented from <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> are <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> and <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span></span>  
  
 <span data-ttu-id="775db-132">Se invoca <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> cuando el mensaje se ha creado o por la aplicación cliente o por el formateador de la operación.</span><span class="sxs-lookup"><span data-stu-id="775db-132"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> is invoked when the message has been composed either by the client application or by the operation formatter.</span></span> <span data-ttu-id="775db-133">Como con los inspectores de mensaje de distribuidor, el mensaje se puede simplemente inspeccionar o reemplazarlo por completo.</span><span class="sxs-lookup"><span data-stu-id="775db-133">As with the dispatcher message inspectors, the message can just be inspected or entirely replaced.</span></span> <span data-ttu-id="775db-134">En este ejemplo, el inspector delega al mismo método del asistente `ValidateMessageBody` local que también se utiliza para los inspectores de mensaje de envío.</span><span class="sxs-lookup"><span data-stu-id="775db-134">In this sample, the inspector delegates to the same local `ValidateMessageBody` helper method that is also used for the dispatch message inspectors.</span></span>  
  
 <span data-ttu-id="775db-135">La diferencia en el comportamiento entre la validación del cliente y la del servicio (tal y como se especifica en el constructor) es que la validación del cliente produce excepciones locales que se colocan en el código de usuario porque suceden localmente y no debido a un error del servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-135">The behavioral difference between the client and service validation (as specified in the constructor) is that the client validation throws local exceptions that are put into the user code because they occur locally and not because of a service failure.</span></span> <span data-ttu-id="775db-136">Generalmente, la regla es que los inspectores de distribuidor de servicio inician errores y los inspectores del cliente inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="775db-136">Generally, the rule is that service dispatcher inspectors throw faults and that client inspectors throw exceptions.</span></span>  
  
 <span data-ttu-id="775db-137">Esta implementación <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> asegura que ningún mensaje no válido se envía al servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-137">This <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> implementation ensures that no invalid messages are sent to the service.</span></span>  
  
```csharp  
object IClientMessageInspector.BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
{  
    if (validateRequest)  
    {  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="775db-138">La implementación `AfterReceiveReply` asegura que ningún mensaje no válido recibido del servicio se transmita al código de usuario del cliente.</span><span class="sxs-lookup"><span data-stu-id="775db-138">The `AfterReceiveReply` implementation ensures that no invalid messages received from the service are relayed to the client user code.</span></span>  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 <span data-ttu-id="775db-139">El centro de este inspector de mensaje determinado es el método `ValidateMessageBody`.</span><span class="sxs-lookup"><span data-stu-id="775db-139">The heart of this particular message inspector is the `ValidateMessageBody` method.</span></span> <span data-ttu-id="775db-140">Para realizar su trabajo, ajusta un <xref:System.Xml.XmlReader> ,que realiza labores de validación, alrededor del subárbol de contenido del cuerpo del mensaje pasado.</span><span class="sxs-lookup"><span data-stu-id="775db-140">To perform its work, it wraps a validating <xref:System.Xml.XmlReader> around the body content sub-tree of the passed message.</span></span> <span data-ttu-id="775db-141">El lector se rellena con el conjunto de esquemas que el inspector del mensaje contiene y la devolución de llamada de la validación se establece en un delegado que hace referencia a `InspectionValidationHandler` , el cual se define junto a este método.</span><span class="sxs-lookup"><span data-stu-id="775db-141">The reader is populated with the set of schemas that the message inspector holds and the validation callback is set to a delegate referring to the `InspectionValidationHandler` that is defined alongside this method.</span></span> <span data-ttu-id="775db-142">Para realizar la validación, el mensaje se lee y se guarda temporalmente en una memoria <xref:System.Xml.XmlDictionaryWriter>con copia de seguridad por cadena.</span><span class="sxs-lookup"><span data-stu-id="775db-142">To perform the validation, the message is then read and spooled into a memory stream-backed <xref:System.Xml.XmlDictionaryWriter>.</span></span> <span data-ttu-id="775db-143">Si se produce un error de validación o una advertencia en el proceso, se invoca el método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="775db-143">If a validation error or warning occurs in the process, the callback method is invoked.</span></span>  
  
 <span data-ttu-id="775db-144">Si no se produce ningún error, se construye un nuevo mensaje, que copia las propiedades y encabezados del mensaje original y utiliza el infoset entonces validado en la secuencia de la memoria, que es ajustada por <xref:System.Xml.XmlDictionaryReader> y se agrega al mensaje del reemplazo.</span><span class="sxs-lookup"><span data-stu-id="775db-144">If no error occurs, a new message is constructed that copies the properties and headers from the original message and uses the now-validated infoset in the memory stream, which is wrapped by an <xref:System.Xml.XmlDictionaryReader> and added to the replacement message.</span></span>  
  
```csharp  
void ValidateMessageBody(ref System.ServiceModel.Channels.Message message, bool isRequest)  
{  
    if (!message.IsFault)  
    {  
        XmlDictionaryReaderQuotas quotas =
                new XmlDictionaryReaderQuotas();  
        XmlReader bodyReader =
            message.GetReaderAtBodyContents().ReadSubtree();  
        XmlReaderSettings wrapperSettings =
                              new XmlReaderSettings();  
        wrapperSettings.CloseInput = true;  
        wrapperSettings.Schemas = schemaSet;  
        wrapperSettings.ValidationFlags =
                                XmlSchemaValidationFlags.None;  
        wrapperSettings.ValidationType = ValidationType.Schema;  
        wrapperSettings.ValidationEventHandler += new
           ValidationEventHandler(InspectionValidationHandler);  
        XmlReader wrappedReader = XmlReader.Create(bodyReader,
                                            wrapperSettings);  
  
        // pull body into a memory backed writer to validate  
        this.isRequest = isRequest;  
        MemoryStream memStream = new MemoryStream();  
        XmlDictionaryWriter xdw =  
              XmlDictionaryWriter.CreateBinaryWriter(memStream);  
        xdw.WriteNode(wrappedReader, false);  
        xdw.Flush(); memStream.Position = 0;  
        XmlDictionaryReader xdr =
        XmlDictionaryReader.CreateBinaryReader(memStream, quotas);  
  
        // reconstruct the message with the validated body  
        Message replacedMessage =
            Message.CreateMessage(message.Version, null, xdr);  
        replacedMessage.Headers.CopyHeadersFrom(message.Headers);  
        replacedMessage.Properties.CopyProperties(message.Properties);  
        message = replacedMessage;  
    }  
}  
```  
  
 <span data-ttu-id="775db-145">El método `InspectionValidationHandler` es llamado por <xref:System.Xml.XmlReader> , que realiza labores de validación, cada vez que se produce un error de validación del esquema o una advertencia.</span><span class="sxs-lookup"><span data-stu-id="775db-145">The `InspectionValidationHandler` method is called by the validating <xref:System.Xml.XmlReader> whenever a schema validation error or warning occurs.</span></span> <span data-ttu-id="775db-146">La implementación siguiente solo trabaja con errores y omite todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="775db-146">The following implementation only works with errors and ignores all warnings.</span></span>  
  
 <span data-ttu-id="775db-147">En un primer momento, podría parecer posible insertar un <xref:System.Xml.XmlReader> que realice labores de validación en el mensaje con el inspector del mensaje y permitir la validación cuando se procesa el mensaje y sin almacenar en búfer el mensaje.</span><span class="sxs-lookup"><span data-stu-id="775db-147">On first consideration, it might seem possible to inject a validating <xref:System.Xml.XmlReader> into the message with the message inspector and let the validation happen as the message is processed and without buffering the message.</span></span> <span data-ttu-id="775db-148">Eso, sin embargo, significa que esta devolución de llamada inicia las excepciones de validación en alguna parte de la infraestructura del modelo del servicio o el código de usuario cuando se detectan nodos XML no válidos, lo que produce un comportamiento imprevisible.</span><span class="sxs-lookup"><span data-stu-id="775db-148">That, however, means that this callback throws the validation exceptions somewhere into the service model infrastructure or the user code as invalid XML nodes are detected, resulting in unpredictable behavior.</span></span> <span data-ttu-id="775db-149">El enfoque del almacenado en búfer protege por completo el código de usuario de mensajes no válidos.</span><span class="sxs-lookup"><span data-stu-id="775db-149">The buffering approach shields the user code from invalid messages, entirely.</span></span>  
  
 <span data-ttu-id="775db-150">Tal y como se expuso con anterioridad, las excepciones iniciadas por el controlador difieren entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-150">As previously discussed, the exceptions thrown by the handler differ between the client and the service.</span></span> <span data-ttu-id="775db-151">En el servicio, las excepciones se derivan de <xref:System.ServiceModel.FaultException>, en el cliente las excepciones son las excepciones normales.</span><span class="sxs-lookup"><span data-stu-id="775db-151">On the service, the exceptions are derived from <xref:System.ServiceModel.FaultException>, on the client the exceptions are regular custom exceptions.</span></span>  
  
```csharp  
        void InspectionValidationHandler(object sender, ValidationEventArgs e)  
{  
    if (e.Severity == XmlSeverityType.Error)  
    {  
        // We are treating client and service side validation errors  
        // differently here. Client side errors cause exceptions  
        // and are thrown straight up to the user code. Service side  
        // validations cause faults.  
        if (isClientSide)  
        {  
            if (isRequest)  
            {  
                throw new RequestClientValidationException(e.Message);  
            }  
            else  
            {  
                throw new ReplyClientValidationException(e.Message);  
            }  
        }  
        else  
        {  
            if (isRequest)  
            {  
                // this fault is caught by the ServiceModel
                // infrastructure and turned into a fault reply.  
                throw new RequestValidationFault(e.Message);  
             }  
             else  
             {  
                // this fault is caught and turned into a fault message  
                // in BeforeSendReply in this class  
                throw new ReplyValidationFault(e.Message);  
              }  
          }  
      }  
    }  
```  
  
## <a name="behavior"></a><span data-ttu-id="775db-152">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="775db-152">Behavior</span></span>  

 <span data-ttu-id="775db-153">Los inspectores de mensaje son extensiones del tiempo de ejecución del cliente o de la distribución.</span><span class="sxs-lookup"><span data-stu-id="775db-153">Message inspectors are extensions to the client runtime or the dispatch runtime.</span></span> <span data-ttu-id="775db-154">Dichas extensiones se configuran mediante *comportamientos*.</span><span class="sxs-lookup"><span data-stu-id="775db-154">Such extensions are configured using *behaviors*.</span></span> <span data-ttu-id="775db-155">Un comportamiento es una clase que cambia el comportamiento de tiempo de ejecución del modelo del servicio cambiando la configuración predeterminada o agregando extensiones (como inspectores de mensaje) a él.</span><span class="sxs-lookup"><span data-stu-id="775db-155">A behavior is a class that changes the behavior of the service model runtime by changing the default configuration or adding extensions (such as message inspectors) to it.</span></span>  
  
 <span data-ttu-id="775db-156">La clase `SchemaValidationBehavior` siguiente es el comportamiento utilizado para agregar el inspector de mensaje de este ejemplo al tiempo de ejecución del cliente o la distribución.</span><span class="sxs-lookup"><span data-stu-id="775db-156">The following `SchemaValidationBehavior` class is the behavior used to add this sample's message inspector to the client or dispatch runtime.</span></span> <span data-ttu-id="775db-157">La implementación es bastante básica en ambos casos.</span><span class="sxs-lookup"><span data-stu-id="775db-157">The implementation is rather basic in both cases.</span></span> <span data-ttu-id="775db-158">En <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> y <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, se crea el inspector de mensaje y se agrega a la colección <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> del tiempo de ejecución respectivo.</span><span class="sxs-lookup"><span data-stu-id="775db-158">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> and <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, the message inspector is created and added to the <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> collection of the respective runtime.</span></span>  
  
```csharp
public class SchemaValidationBehavior : IEndpointBehavior  
{  
    XmlSchemaSet schemaSet;
    bool validateRequest;
    bool validateReply;  
  
    public SchemaValidationBehavior(XmlSchemaSet schemaSet, bool
                           inspectRequest, bool inspectReply)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = inspectReply;  
        this.validateRequest = inspectRequest;  
    }  
    #region IEndpointBehavior Members  
  
    public void AddBindingParameters(ServiceEndpoint endpoint,
       System.ServiceModel.Channels.BindingParameterCollection
                                            bindingParameters)  
    {  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint,
            System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
    {  
        SchemaValidationMessageInspector inspector =
           new SchemaValidationMessageInspector(schemaSet,
                      validateRequest, validateReply, true);  
            clientRuntime.MessageInspectors.Add(inspector);  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint,
         System.ServiceModel.Dispatcher.EndpointDispatcher
                                          endpointDispatcher)  
    {  
        SchemaValidationMessageInspector inspector =
           new SchemaValidationMessageInspector(schemaSet,
                        validateRequest, validateReply, false);  
   endpointDispatcher.DispatchRuntime.MessageInspectors.Add(inspector);  
    }  
  
   public void Validate(ServiceEndpoint endpoint)  
   {  
   }  
  
    #endregion  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="775db-159">Este comportamiento determinado no se duplica como un atributo y por consiguiente no se puede agregar mediante declaración a un tipo de contrato de un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-159">This particular behavior does not double as an attribute and therefore cannot be added declaratively onto a contract type of a service type.</span></span> <span data-ttu-id="775db-160">Ésta es una decisión realizada por diseño porque la colección de esquemas no se puede cargar en una declaración de atributos y hacer referencia a una ubicación de configuración adicional (por ejemplo a los valores de la aplicación) en este atributo significa crear un elemento de configuración que no es coherente con el resto de la configuración del modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-160">This is a by-design decision made because the schema collection cannot be loaded in an attribute declaration and referring to an extra configuration location (for instance to the application settings) in this attribute means creating a configuration element that is not consistent with the rest of the service model configuration.</span></span> <span data-ttu-id="775db-161">Por consiguiente, este comportamiento solo se puede agregar imperiosamente a través de código y a través de una extensión de la configuración del modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="775db-161">Therefore, this behavior can only be added imperatively through code and through a service model configuration extension.</span></span>  
  
## <a name="adding-the-message-inspector-through-configuration"></a><span data-ttu-id="775db-162">Agregar el Inspector de Mensaje a través de Configuración</span><span class="sxs-lookup"><span data-stu-id="775db-162">Adding the Message Inspector through Configuration</span></span>  

 <span data-ttu-id="775db-163">Para configurar un comportamiento personalizado en un punto de conexión en el archivo de configuración de la aplicación, el modelo de servicio exige a los implementadores que creen un *elemento de extensión* de configuración representado por una clase derivada de <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> .</span><span class="sxs-lookup"><span data-stu-id="775db-163">For configuring a custom behavior on an endpoint in the application configuration file, the service model requires implementers to create a configuration *extension element* represented by a class derived from <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.</span></span> <span data-ttu-id="775db-164">Esta extensión se debe agregar a continuación a la sección de configuración del modelo del servicio para extensiones, tal y como se muestra para la siguiente extensión discutida en esta sección.</span><span class="sxs-lookup"><span data-stu-id="775db-164">This extension must then be added to the service model's configuration section for extensions as shown for the following extension discussed in this section.</span></span>  
  
```xml  
<system.serviceModel>  
…  
   <extensions>  
      <behaviorExtensions>  
        <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
      </behaviorExtensions>  
    </extensions>  
…  
</system.serviceModel>  
```  
  
 <span data-ttu-id="775db-165">Las extensiones se pueden agregar en el archivo de configuración de la aplicación o de ASP.NET, que es la opción más común, o en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="775db-165">Extensions can be added in the application or ASP.NET configuration file, which is the most common choice, or in the machine configuration file.</span></span>  
  
 <span data-ttu-id="775db-166">Cuando la extensión se agrega a un ámbito de configuración, el comportamiento se puede agregar a una configuración de comportamiento, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="775db-166">When the extension is added to a configuration scope, the behavior can be added to a behavior configuration as it is shown in the following code.</span></span> <span data-ttu-id="775db-167">Las configuraciones de comportamiento son elementos reutilizables que se pueden aplicar a varios extremos requeridos según se necesite.</span><span class="sxs-lookup"><span data-stu-id="775db-167">Behavior configurations are reusable elements that can be applied to multiple endpoints as required.</span></span> <span data-ttu-id="775db-168">Dado que el comportamiento determinado que se configura aquí implementa <xref:System.ServiceModel.Description.IEndpointBehavior>, solo es válido en la sección de configuración respectiva en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="775db-168">Because the particular behavior to be configured here implements <xref:System.ServiceModel.Description.IEndpointBehavior>, it is only valid in the respective configuration section in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
   <behaviors>  
      …  
     <endpointBehaviors>  
        <behavior name="HelloServiceEndpointBehavior">  
          <schemaValidator validateRequest="True" validateReply="True">  
            <schemas>  
              <add location="messages.xsd" />
            </schemas>  
          </schemaValidator>  
        </behavior>  
      </endpointBehaviors>  
      …  
    </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="775db-169">La clase `<schemaValidator>` respalda el elemento `SchemaValidationBehaviorExtensionElement` que configura el inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="775db-169">The `<schemaValidator>` element that configures the message inspector is backed by the `SchemaValidationBehaviorExtensionElement` class.</span></span> <span data-ttu-id="775db-170">La clase expone dos propiedades públicas booleanas denominadas `ValidateRequest` y `ValidateReply`.</span><span class="sxs-lookup"><span data-stu-id="775db-170">The class exposes two Boolean public properties named `ValidateRequest` and `ValidateReply`.</span></span> <span data-ttu-id="775db-171">Ambos están marcados con un <xref:System.Configuration.ConfigurationPropertyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="775db-171">Both of these are marked with a <xref:System.Configuration.ConfigurationPropertyAttribute>.</span></span> <span data-ttu-id="775db-172">Este atributo constituye el vínculo entre las propiedades de código y los atributos XML que se pueden ver en el elemento de configuración XML anterior.</span><span class="sxs-lookup"><span data-stu-id="775db-172">This attribute constitutes the link between the code properties and the XML attributes that can be seen on the preceding XML configuration element.</span></span> <span data-ttu-id="775db-173">La clase también tiene una propiedad `Schemas` que se marca además con <xref:System.Configuration.ConfigurationCollectionAttribute> y es del tipo `SchemaCollection`, que también forma parte de este ejemplo pero se omitió en este documento por cuestiones de brevedad.</span><span class="sxs-lookup"><span data-stu-id="775db-173">The class also has a property `Schemas` that is additionally marked with the <xref:System.Configuration.ConfigurationCollectionAttribute> and is of the type `SchemaCollection`, which is also part of this sample but omitted from this document for brevity.</span></span> <span data-ttu-id="775db-174">Esta propiedad, junto con la colección y la clase de colección de elemento `SchemaConfigElement` respalda el elemento `<schemas>` en el fragmento de código de configuración anterior y permite agregar una colección de esquemas a la validación establecida.</span><span class="sxs-lookup"><span data-stu-id="775db-174">This property along with the collection and the collection element class `SchemaConfigElement` backs the `<schemas>` element in the preceding configuration snippet and allows adding a collection of schemas to the validation set.</span></span>  
  
 <span data-ttu-id="775db-175">El método `CreateBehavior` invalidado convierte los datos de configuración en un objeto de comportamiento cuando el tiempo de ejecución evalúa los datos de configuración cuando genera un cliente o un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="775db-175">The overridden `CreateBehavior` method turns the configuration data into a behavior object when the runtime evaluates the configuration data as it builds a client or an endpoint.</span></span>  
  
```csharp
public class SchemaValidationBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public SchemaValidationBehaviorExtensionElement()  
    {  
    }  
  
    public override Type BehaviorType
    {
        get  
        {  
            return typeof(SchemaValidationBehavior);  
        }
    }  
  
    protected override object CreateBehavior()  
    {  
        XmlSchemaSet schemaSet = new XmlSchemaSet();  
        foreach (SchemaConfigElement schemaCfg in this.Schemas)  
        {  
            Uri baseSchema = new
                Uri(AppDomain.CurrentDomain.BaseDirectory);  
            string location = new
                Uri(baseSchema,schemaCfg.Location).ToString();  
            XmlSchema schema =
                XmlSchema.Read(new XmlTextReader(location), null);  
            schemaSet.Add(schema);  
        }  
     return new
     SchemaValidationBehavior(schemaSet,ValidateRequest,ValidateReply);  
    }  
  
[ConfigurationProperty("validateRequest",DefaultValue=false,IsRequired=false)]  
public bool ValidateRequest  
{  
    get { return (bool)base["validateRequest"]; }  
    set { base["validateRequest"] = value; }  
}  
  
[ConfigurationProperty("validateReply", DefaultValue = false, IsRequired = false)]  
        public bool ValidateReply  
        {  
            get { return (bool)base["validateReply"]; }  
            set { base["validateReply"] = value; }  
        }  
  
     //Declare the Schema collection property.  
     //Note: the "IsDefaultCollection = false" instructs
     //.NET Framework to build a nested section of
     //the kind <Schema> ...</Schema>.  
    [ConfigurationProperty("schemas", IsDefaultCollection = true)]  
    [ConfigurationCollection(typeof(SchemasCollection),  
        AddItemName = "add",  
        ClearItemsName = "clear",  
        RemoveItemName = "remove")]  
    public SchemasCollection Schemas  
    {  
        get  
        {  
            SchemasCollection SchemasCollection =  
            (SchemasCollection)base["schemas"];  
            return SchemasCollection;  
        }  
    }  
}  
```  
  
## <a name="adding-message-inspectors-imperatively"></a><span data-ttu-id="775db-176">Agregar imperiosamente inspectores de mensaje</span><span class="sxs-lookup"><span data-stu-id="775db-176">Adding Message Inspectors Imperatively</span></span>  

 <span data-ttu-id="775db-177">Excepto a través de atributos (lo cual no se contempla en este ejemplo por la razón citada previamente) y configuración, los comportamientos se pueden agregar con cierta facilidad a un tiempo de ejecución de cliente y de servicio utilizando el código imperativo.</span><span class="sxs-lookup"><span data-stu-id="775db-177">Except through attributes (which is not supported in this sample for the reason cited previously) and configuration, behaviors can quite easily be added to a client and service runtime using imperative code.</span></span> <span data-ttu-id="775db-178">En este ejemplo, esto se hace en la aplicación cliente para probar el inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="775db-178">In this sample, this is done in the client application to test the client message inspector.</span></span> <span data-ttu-id="775db-179">La clase `GenericClient` se deriva de <xref:System.ServiceModel.ClientBase%601>, que expone la configuración del punto de conexión al código de usuario.</span><span class="sxs-lookup"><span data-stu-id="775db-179">The `GenericClient` class is derived from <xref:System.ServiceModel.ClientBase%601>, which exposes the endpoint configuration to the user code.</span></span> <span data-ttu-id="775db-180">Antes de que se abra el cliente implícitamente se puede cambiar la configuración del punto de conexión, por ejemplo agregando comportamientos, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="775db-180">Before the client is implicitly opened the endpoint configuration can be changed, for instance by adding behaviors as shown in the following code.</span></span> <span data-ttu-id="775db-181">Agregar el comportamiento al servicio es principalmente el equivalente a la técnica de cliente mostrada aquí y se debe realizar antes de que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="775db-181">Adding the behavior on the service is largely equivalent to the client technique shown here and must be performed before the service host is opened.</span></span>  
  
```csharp  
try  
{  
    Console.WriteLine("*** Call 'Hello' with generic client, with client behavior");  
    GenericClient client = new GenericClient();  
  
    // Configure client programmatically, adding behavior  
    XmlSchema schema = XmlSchema.Read(new StreamReader("messages.xsd"),
                                                          null);  
    XmlSchemaSet schemaSet = new XmlSchemaSet();  
    schemaSet.Add(schema);  
    client.Endpoint.Behaviors.Add(new
                SchemaValidationBehavior(schemaSet, true, true));  
  
    Console.WriteLine("--- Sending valid client request:");  
    GenericCallValid(client, helloAction);  
    Console.WriteLine("--- Sending invalid client request:");  
    GenericCallInvalid(client, helloAction);  
  
    client.Close();  
}  
catch (Exception e)  
{  
    DumpException(e);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="775db-182">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="775db-182">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="775db-183">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="775db-183">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="775db-184">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="775db-184">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="775db-185">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="775db-185">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="775db-186">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="775db-186">The samples may already be installed on your machine.</span></span> <span data-ttu-id="775db-187">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="775db-187">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="775db-188">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="775db-188">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="775db-189">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="775db-189">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
