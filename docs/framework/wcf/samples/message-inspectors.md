---
title: Inspectores de mensaje
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 1a5519e815a6714e087a77c69e943a3a8c65db68
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585083"
---
# <a name="message-inspectors"></a>Inspectores de mensaje
Este ejemplo muestra cómo implementar y configurar los inspectores de mensaje de cliente y servicio.  
  
 Un inspector del mensaje es un objeto de extensibilidad que se puede utilizar en el cliente del modelo del servicio en tiempo de ejecución y enviarse mediante programación en tiempo de ejecución o a través de configuración, y que puede inspeccionar y modificar los mensajes una vez recibidos o antes de enviarse.  
  
 Este ejemplo implementa un cliente básico y un mecanismo de validación de mensaje de servicio que valida los mensajes entrantes contra un conjunto de documentos de esquema XML configurables. Tenga en cuenta que este ejemplo no valida los mensajes para cada operación. Esta es una simplificación intencional.  
  
## <a name="message-inspector"></a>Inspector de mensajes  
 Los inspectores de mensaje de cliente implementan la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> y los inspectores de mensaje de servicio implementan la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>. Las implementaciones se pueden combinar en una clase única para formar un inspector de mensaje que trabaja para ambas partes. Este ejemplo implementa este tipo de inspector de mensaje combinado. El inspector se construye transmitiendo un conjunto de esquemas sobre la base de qué mensajes entrantes y salientes se validan, y permite al programador especificar si se validan los mensajes entrantes o salientes y si el inspector está en modo cliente o envío, el cual afecta al control de errores tal y como se analiza después en este tema.  
  
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
  
 Todos los inspectores de mensaje de servicio (distribuidor) deben implementar los dos métodos <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> y <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.  
  
 El distribuidor invoca <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> cuando se ha recibido un mensaje, la pila del canal lo ha procesado y se ha asignado a un servicio, pero antes de que sea deserializado y enviado a una operación. Si el mensaje entrante está cifrado, se descifra cuando llega al inspector de mensaje. El método obtiene el mensaje `request` pasado como un parámetro de referencia, que permite inspeccionar el mensaje, manipularlo o reemplazarlo como sea necesario. El valor devuelto puede ser cualquier objeto y se utiliza como un objeto de estado de correlación que se pasa a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> cuando el servicio devuelve una respuesta al mensaje actual. En este ejemplo, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delega la inspección (validación) del mensaje al método `ValidateMessageBody` , privado y local, y no devuelve ningún objeto de estado de correlación. Este método asegura que ningún mensaje no válido pase al servicio.  
  
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
  
 Se invoca <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> siempre que una respuesta está lista para ser devuelta a un cliente o en el caso de mensajes unidireccionales, cuando se ha procesado el mensaje entrante. Esto permite a las extensiones contar con que se les llame simétricamente, sin tener en cuenta el MEP. Al igual que con <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, el mensaje se pasa como un parámetro de referencia y se puede inspeccionar, modificar o reemplazar. La validación del mensaje que se realiza en este ejemplo se delega de nuevo al método `ValidMessageBody`, pero el control de errores de validación es ligeramente diferente en este caso.  
  
 Si se produce un error de validación en el servicio, el método `ValidateMessageBody` inicia <xref:System.ServiceModel.FaultException>- excepciones derivadas. En <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, estas excepciones se pueden colocar en la infraestructura modelo del servicio, donde se transforman automáticamente en errores SOAP y se transmiten al cliente. En <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, las excepciones <xref:System.ServiceModel.FaultException> no se deben colocar en la infraestructura, porque la transformación de excepciones de error iniciada por el servicio se produce antes de llamar al inspector de mensaje. Por consiguiente, la implementación siguiente detecta la excepción `ReplyValidationFault` conocida y reemplaza el mensaje de respuesta con un mensaje de error explícito. Este método asegura que la implementación del servicio no devuelve ningún mensaje no válido.  
  
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
  
 El inspector de mensaje de cliente es muy similar. Los dos métodos que se deben implementar de <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> son <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> y <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.  
  
 Se invoca <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> cuando el mensaje se ha creado o por la aplicación cliente o por el formateador de la operación. Como con los inspectores de mensaje de distribuidor, el mensaje se puede simplemente inspeccionar o reemplazarlo por completo. En este ejemplo, el inspector delega al mismo método del asistente `ValidateMessageBody` local que también se utiliza para los inspectores de mensaje de envío.  
  
 La diferencia en el comportamiento entre la validación del cliente y la del servicio (tal y como se especifica en el constructor) es que la validación del cliente produce excepciones locales que se colocan en el código de usuario porque suceden localmente y no debido a un error del servicio. Generalmente, la regla es que los inspectores de distribuidor de servicio inician errores y los inspectores del cliente inician excepciones.  
  
 Esta implementación <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> asegura que ningún mensaje no válido se envía al servicio.  
  
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
  
 La implementación `AfterReceiveReply` asegura que ningún mensaje no válido recibido del servicio se transmita al código de usuario del cliente.  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 El centro de este inspector de mensaje determinado es el método `ValidateMessageBody`. Para realizar su trabajo, ajusta un <xref:System.Xml.XmlReader> ,que realiza labores de validación, alrededor del subárbol de contenido del cuerpo del mensaje pasado. El lector se rellena con el conjunto de esquemas que el inspector del mensaje contiene y la devolución de llamada de la validación se establece en un delegado que hace referencia a `InspectionValidationHandler` , el cual se define junto a este método. Para realizar la validación, el mensaje se lee y se guarda temporalmente en una memoria <xref:System.Xml.XmlDictionaryWriter>con copia de seguridad por cadena. Si se produce un error de validación o una advertencia en el proceso, se invoca el método de devolución de llamada.  
  
 Si no se produce ningún error, se construye un nuevo mensaje, que copia las propiedades y encabezados del mensaje original y utiliza el infoset entonces validado en la secuencia de la memoria, que es ajustada por <xref:System.Xml.XmlDictionaryReader> y se agrega al mensaje del reemplazo.  
  
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
  
 El método `InspectionValidationHandler` es llamado por <xref:System.Xml.XmlReader> , que realiza labores de validación, cada vez que se produce un error de validación del esquema o una advertencia. La implementación siguiente solo trabaja con errores y omite todas las advertencias.  
  
 En un primer momento, podría parecer posible insertar un <xref:System.Xml.XmlReader> que realice labores de validación en el mensaje con el inspector del mensaje y permitir la validación cuando se procesa el mensaje y sin almacenar en búfer el mensaje. Eso, sin embargo, significa que esta devolución de llamada inicia las excepciones de validación en alguna parte de la infraestructura del modelo del servicio o el código de usuario cuando se detectan nodos XML no válidos, lo que produce un comportamiento imprevisible. El enfoque del almacenado en búfer protege por completo el código de usuario de mensajes no válidos.  
  
 Tal y como se expuso con anterioridad, las excepciones iniciadas por el controlador difieren entre el cliente y el servicio. En el servicio, las excepciones se derivan de <xref:System.ServiceModel.FaultException>, en el cliente las excepciones son las excepciones normales.  
  
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
  
## <a name="behavior"></a>Comportamiento  
 Los inspectores de mensaje son extensiones del tiempo de ejecución del cliente o de la distribución. Dichas extensiones se configuran mediante *comportamientos*. Un comportamiento es una clase que cambia el comportamiento de tiempo de ejecución del modelo del servicio cambiando la configuración predeterminada o agregando extensiones (como inspectores de mensaje) a él.  
  
 La clase `SchemaValidationBehavior` siguiente es el comportamiento utilizado para agregar el inspector de mensaje de este ejemplo al tiempo de ejecución del cliente o la distribución. La implementación es bastante básica en ambos casos. En <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> y <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, se crea el inspector de mensaje y se agrega a la colección <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> del tiempo de ejecución respectivo.  
  
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
> Este comportamiento determinado no se duplica como un atributo y por consiguiente no se puede agregar mediante declaración a un tipo de contrato de un tipo de servicio. Ésta es una decisión realizada por diseño porque la colección de esquemas no se puede cargar en una declaración de atributos y hacer referencia a una ubicación de configuración adicional (por ejemplo a los valores de la aplicación) en este atributo significa crear un elemento de configuración que no es coherente con el resto de la configuración del modelo de servicio. Por consiguiente, este comportamiento solo se puede agregar imperiosamente a través de código y a través de una extensión de la configuración del modelo de servicio.  
  
## <a name="adding-the-message-inspector-through-configuration"></a>Agregar el Inspector de Mensaje a través de Configuración  
 Para configurar un comportamiento personalizado en un punto de conexión en el archivo de configuración de la aplicación, el modelo de servicio exige a los implementadores que creen un *elemento de extensión* de configuración representado por una clase derivada de <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> . Esta extensión se debe agregar a continuación a la sección de configuración del modelo del servicio para extensiones, tal y como se muestra para la siguiente extensión discutida en esta sección.  
  
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
  
 Las extensiones se pueden agregar en el archivo de configuración de la aplicación o de ASP.NET, que es la opción más común, o en el archivo de configuración del equipo.  
  
 Cuando la extensión se agrega a un ámbito de configuración, el comportamiento se puede agregar a una configuración de comportamiento, como se muestra en el siguiente código. Las configuraciones de comportamiento son elementos reutilizables que se pueden aplicar a varios extremos requeridos según se necesite. Dado que el comportamiento determinado que se configura aquí implementa <xref:System.ServiceModel.Description.IEndpointBehavior>, solo es válido en la sección de configuración respectiva en el archivo de configuración.  
  
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
  
 La clase `<schemaValidator>` respalda el elemento `SchemaValidationBehaviorExtensionElement` que configura el inspector de mensaje. La clase expone dos propiedades públicas booleanas denominadas `ValidateRequest` y `ValidateReply`. Ambos están marcados con un <xref:System.Configuration.ConfigurationPropertyAttribute>. Este atributo constituye el vínculo entre las propiedades de código y los atributos XML que se pueden ver en el elemento de configuración XML anterior. La clase también tiene una propiedad `Schemas` que se marca además con <xref:System.Configuration.ConfigurationCollectionAttribute> y es del tipo `SchemaCollection`, que también forma parte de este ejemplo pero se omitió en este documento por cuestiones de brevedad. Esta propiedad, junto con la colección y la clase de colección de elemento `SchemaConfigElement` respalda el elemento `<schemas>` en el fragmento de código de configuración anterior y permite agregar una colección de esquemas a la validación establecida.  
  
 El método `CreateBehavior` invalidado convierte los datos de configuración en un objeto de comportamiento cuando el tiempo de ejecución evalúa los datos de configuración cuando genera un cliente o un punto de conexión.  
  
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
  
## <a name="adding-message-inspectors-imperatively"></a>Agregar imperiosamente inspectores de mensaje  
 Excepto a través de atributos (lo cual no se contempla en este ejemplo por la razón citada previamente) y configuración, los comportamientos se pueden agregar con cierta facilidad a un tiempo de ejecución de cliente y de servicio utilizando el código imperativo. En este ejemplo, esto se hace en la aplicación cliente para probar el inspector de mensaje de cliente. La clase `GenericClient` se deriva de <xref:System.ServiceModel.ClientBase%601>, que expone la configuración del punto de conexión al código de usuario. Antes de que se abra el cliente implícitamente se puede cambiar la configuración del punto de conexión, por ejemplo agregando comportamientos, como se muestra en el código siguiente. Agregar el comportamiento al servicio es principalmente el equivalente a la técnica de cliente mostrada aquí y se debe realizar antes de que el host del servicio se abra.  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
