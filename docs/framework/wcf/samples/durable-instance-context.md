---
title: Contexto de instancia duradera
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4f1f3f9e840ba422e327792ec2b0554fad45902
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="durable-instance-context"></a>Contexto de instancia duradera
Este ejemplo muestra cómo personalizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en tiempo de ejecución para habilitar los contextos de instancia duraderos. Utiliza SQL Server 2005 como su memoria auxiliar (SQL Server 2005 Express en este caso). Sin embargo, también proporciona una manera de tener acceso a los mecanismos de almacenamiento personalizados.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo implica extender tanto la capa del canal como la capa de modelo de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Por consiguiente, es necesario entender los conceptos subyacentes antes de entrar en los detalles de la implementación.  
  
 Los contextos de la instancia duraderos se pueden encontrar bastante a menudo en situaciones reales. Una aplicación de carro de la compra, por ejemplo, tiene la capacidad de pausar la compra cuando ésta se encuentra a la mitad y continuarla otro día. Para que cuando visitemos el carro de la compra el día siguiente, se restaure nuestro contexto original. Es importante tener en cuenta que la aplicación de carro de la compra (en el servidor) no mantiene la instancia del carro de la compra mientras estamos desconectados. En su lugar, conserva su estado en medios de almacenamiento duraderos y lo utiliza cuando construye una nueva instancia para el contexto restaurado. Por consiguiente, la instancia del servicio que puede ser de utilidad para el mismo contexto no es igual que la instancia anterior (es decir, no tiene la misma dirección de memoria).  
  
 Un protocolo pequeño que intercambia un id. de contexto entre el cliente y el servicio posibilita el contexto de la instancia duradera. Este id. de contexto se crea en el cliente y se transmite al servicio. Cuando se crea la instancia del servicio, el tiempo de ejecución del servicio intenta cargar el estado conservado que corresponde a este id. de contexto desde un almacenamiento persistente (de forma predeterminada es una base de datos SQL Server 2005). Si no está disponible ningún estado, la nueva instancia tiene su estado predeterminado. La implementación del servicio utiliza un atributo personalizado para marcar operaciones que cambian el estado de la implementación del servicio para que el tiempo de ejecución pueda guardar la instancia del servicio después de invocarlos.  
  
 Por la descripción anterior, se pueden distinguir con facilidad dos pasos para lograr el objetivo:  
  
1.  Cambiar el mensaje en la conexión para llevar el id. de contexto.  
  
2.  Cambiar el comportamiento local del servicio para implementar la lógica de creación de instancias personalizada.  
  
 Dado que la primera en la lista afecta a los mensajes en la conexión, se debería implementar como un canal personalizado y enlazarse hasta la capa del canal. El último solo afecta al comportamiento local del servicio y por consiguiente se puede implementar extendiendo varios puntos de extensibilidad de servicio. Cada una de estas extensiones se trata en las siguientes secciones.  
  
## <a name="durable-instancecontext-channel"></a>Canal de InstanceContext duradero  
 Lo primero que se ha de mirar es una extensión de capa de canal. El primer paso en escribir un canal personalizado es decidir la estructura de comunicación del canal. Cuando se introduce un nuevo protocolo de conexión, el canal debería trabajar con casi cualquier otro canal en la pila de canales. Por consiguiente, debería admitir todos los patrones de intercambio de mensajes. Sin embargo, la funcionalidad básica del canal es la misma, independientemente de su estructura de comunicación. Más específicamente, del cliente debería escribir el id. de contexto a los mensajes y del servicio debería leer este id. de contexto de los mensajes y pasarlo a los niveles superiores. Debido a eso, se crea una clase `DurableInstanceContextChannelBase` que actúa como la clase base abstracta para todas las implementaciones de canal de contexto de instancia duraderas. Esta clase contiene las funciones de administración de máquina de estado común y dos miembros protegidos para aplicar y leer la información de contexto a y desde los mensajes.  
  
```  
class DurableInstanceContextChannelBase  
{  
  //…  
  protected void ApplyContext(Message message)  
  {  
    //…              
  }  
  protected string ReadContextId(Message message)  
  {  
    //…              
  }  
}  
```  
  
 Estos dos métodos utilizan implementaciones `IContextManager` para escribir y leer el id. de contexto a o del mensaje. (`IContextManager` es una interfaz personalizada utilizada para definir el contrato para todos los administradores del contexto). El canal puede incluir o el id. de contexto en un encabezado SOAP personalizado o en un encabezado cookie HTTP. Cada implementación de administrador de contexto hereda de la clase `ContextManagerBase` que contiene la funcionalidad común para todos los administradores del contexto. El método `GetContextId` en esta clase se utiliza para originar el id. de contexto del cliente. Cuando se origina un id. de contexto por primera vez, este método lo guarda en un archivo de texto cuyo nombre se construye a partir de la dirección remota del punto de conexión (los caracteres del nombre de archivo no válidos en los URI típicos se reemplazan con caracteres @).  
  
 Después, cuando el id. de contexto se requiere para el mismo punto de conexión remoto, comprueba si existe un archivo adecuado. Si es así, lee el id. de contexto y lo devuelve. De lo contrario devuelve un id. de contexto recientemente generado y lo guarda en un archivo. Con la configuración predeterminada, estos archivos se colocan en un directorio llamado ContextStore, que reside en el directorio temp del usuario actual. No obstante, esta ubicación es configurable utilizando el elemento de enlace.  
  
 El mecanismo utilizado para transportar el id. de contexto es configurable. Se pudría escribir en el encabezado cookie HTTP o en un encabezado SOAP personalizado. El enfoque del encabezado SOAP personalizado permite utilizar este protocolo con protocolos que no son HTTP (por ejemplo, TCP o canalizaciones con nombre). Hay dos clases, a saber `MessageHeaderContextManager` y `HttpCookieContextManager`, que implementan estas dos opciones.  
  
 Ambos escriben apropiadamente el id. de contexto en el mensaje. Por ejemplo, la clase `MessageHeaderContextManager` lo escribe en un encabezado SOAP en el método `WriteContext`.  
  
```  
public override void WriteContext(Message message)  
{  
  string contextId = this.GetContextId();  
  
  MessageHeader contextHeader =  
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,  
      DurableInstanceContextUtility.HeaderNamespace,  
      contextId,   
      true);  
  
  message.Headers.Add(contextHeader);  
}   
```  
  
 Ambos métodos, `ApplyContext` y `ReadContextId` en la clase `DurableInstanceContextChannelBase` invocan el `IContextManager.ReadContext` y `IContextManager.WriteContext`, respectivamente. Sin embargo, la clase `DurableInstanceContextChannelBase` no crea directamente estos administradores del contexto. En su lugar utiliza la clase `ContextManagerFactory` para hacer ese trabajo.  
  
```  
IContextManager contextManager =  
                ContextManagerFactory.CreateContextManager(contextType,   
                this.contextStoreLocation,   
                this.endpointAddress);  
```  
  
 Los canales de envío invocan el método `ApplyContext`. Éste inserta el id. de contexto a los mensajes salientes. Los canales de recepción invocan el método `ReadContextId`. Este método garantiza que el id. de contexto esté disponible en los mensajes entrantes y lo agrega a la colección `Properties` de la clase `Message`. También produce un `CommunicationException` en caso de un error al leer el id. de contexto y así hace que se anule el canal.  
  
```  
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);  
```  
  
 Antes de continuar, es importante entender el uso de la colección `Properties` en la clase `Message`. Normalmente, esta colección se utiliza `Properties` al pasar los datos de niveles bajos a superiores desde la capa del canal. De este modo los datos deseados se pueden proporcionar a los niveles superiores de una manera coherente sin tener en cuenta los detalles protocolares. En otras palabras, la capa del canal puede enviar y recibir el id. de contexto como un encabezado SOAP o un encabezado cookie HTTP. Pero no es necesario que los niveles superiores conozcan estos detalles, porque la capa del canal hace que esta información esté disponible en la colección `Properties`.  
  
 Ahora, con la clase `DurableInstanceContextChannelBase` en su lugar, se deben implementar los diez interfaces necesarios (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel). Se parecen a cualquier patrón de intercambio de mensajes disponible (datagrama, simplex, duplex y sus variantes con sesión). Cada una de estas implementaciones hereda previamente la clase base descrita y llama apropiadamente a `ApplyContext` y a `ReadContexId`. Por ejemplo, `DurableInstanceContextOutputChannel`- que implementa la interfaz IOutputChannel - llama al método `ApplyContext` desde cada método que envía los mensajes.  
  
```  
public void Send(Message message, TimeSpan timeout)  
{  
    // Apply the context information before sending the message.  
    this.ApplyContext(message);  
    //…  
}   
```  
  
 Por otro lado, `DurableInstanceContextInputChannel`- qué implementa la interfaz `IInputChannel`- llama al método `ReadContextId` en cada método que recibe los mensajes.  
  
```  
public Message Receive(TimeSpan timeout)  
{  
    //…  
      ReadContextId(message);  
      return message;  
}  
```  
  
 Aparte de esto, estas implementaciones de canal delegan las invocaciones de método al canal debajo de ellos en la pila del canal. Sin embargo, las variantes con sesión tienen una lógica básica para asegurarse de que el id. de contexto se envía y se lee solo para el primer mensaje que provoca que la sesión se cree.  
  
```  
if (isFirstMessage)  
{  
//…  
    this.ApplyContext(message);  
    isFirstMessage = false;  
}  
```  
  
 Estas implementaciones del canal se agregan apropiadamente a continuación al tiempo de ejecución del canal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] por la clase `DurableInstanceContextBindingElement` y la clase `DurableInstanceContextBindingElementSection`. Consulte la [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) documentación de ejemplo para obtener más información acerca de los elementos de enlace y secciones de los elementos de enlace de canal.  
  
## <a name="service-model-layer-extensions"></a>Extensiones de la capa de modelo de servicio  
 Ahora que el id. de contexto ha viajado a través de la capa del canal, el comportamiento del servicio se puede implementar para personalizar la creación de instancias. En este ejemplo, se utiliza un administrador de almacenamiento para cargar y guardar el estado desde o al almacén persistente. Tal y como se explicó con anterioridad, este ejemplo proporciona un administrador de almacenamiento que utiliza SQL Server 2005 como su memoria auxiliar. Sin embargo, también es posible agregar mecanismos de almacenamiento personalizados a esta extensión. Para hacer eso se declara una interfaz pública, la cual debe ser implementada por todos los administradores de almacenamiento.  
  
```  
public interface IStorageManager  
{  
    object GetInstance(string contextId, Type type);  
    void SaveInstance(string contextId, object state);  
}  
```  
  
 La clase `SqlServerStorageManager`contiene la implementación `IStorageManager` predeterminada. En su método `SaveInstance`, el objeto determinado se serializa utilizando XmlSerializer y se guarda en la base de datos de SQL Server.  
  
```  
XmlSerializer serializer = new XmlSerializer(state.GetType());  
string data;  
  
using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))  
{  
    serializer.Serialize(writer, state);  
    data = writer.ToString();  
}  
  
using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
{  
    connection.Open();  
  
    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";  
  
    using (SqlCommand command = new SqlCommand(update, connection))  
    {  
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;  
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;  
  
        int rows = command.ExecuteNonQuery();  
  
        if (rows == 0)  
        {  
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";  
            command.CommandText = insert;  
            command.ExecuteNonQuery();  
        }  
    }  
}  
```  
  
 En el método `GetInstance` los datos serializados se leen para un id. de contexto determinado y el objeto construido a partir de él se devuelve al llamador.  
  
```  
object data;  
using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
{  
    connection.Open();  
  
    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";  
    using (SqlCommand command = new SqlCommand(select, connection))  
    {  
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;  
        data = command.ExecuteScalar();  
    }  
}  
  
if (data != null)  
{  
    XmlSerializer serializer = new XmlSerializer(type);  
    using (StringReader reader = new StringReader((string)data))  
    {  
        object instance = serializer.Deserialize(reader);  
        return instance;  
    }  
}  
```  
  
 No se supone que los usuarios de estos administradores de almacenamiento creen directamente instancias de ellos. Utilizan la clase `StorageManagerFactory`, que resume detalles de creación en el administrador de almacenamiento . Esta clase tiene un miembro estático, `GetStorageManager`, que crea una instancia de un tipo de administrador de almacenamiento determinado. Si el parámetro de tipo es `null`, este método crea una instancia de la clase `SqlServerStorageManager` predeterminada y lo devuelve. También valida el tipo determinado para asegurarse de que implementa la interfaz `IStorageManager`.  
  
```  
public static IStorageManager GetStorageManager(Type storageManagerType)  
{  
IStorageManager storageManager = null;  
  
if (storageManagerType == null)  
{  
    return new SqlServerStorageManager();  
}  
else  
{  
    object obj = Activator.CreateInstance(storageManagerType);  
  
    // Throw if the specified storage manager type does not  
    // implement IStorageManager.  
    if (obj is IStorageManager)  
    {  
        storageManager = (IStorageManager)obj;  
    }  
    else  
    {  
        throw new InvalidOperationException(  
                  ResourceHelper.GetString("ExInvalidStorageManager"));  
    }  
  
    return storageManager;  
}                  
}   
```  
  
 Se implementa la infraestructura necesaria para leer y escribir instancias del almacenamiento persistente. Ahora tienen que tomarse los pasos necesarios para cambiar el comportamiento del servicio.  
  
 Como primer paso de este proceso tenemos que guardar el id. de contexto, que pasó por la capa del canal al InstanceContext actual. InstanceContext es un componente en tiempo de ejecución que actúa como vínculo entre el distribuidor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y la instancia del servicio. Se puede utilizar para proporcionar estado y comportamiento adicionales a la instancia del servicio. Esto es esencial porque en comunicación con sesión el id. de contexto solo se envía con el primer mensaje.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite que se extienda su componente en tiempo de ejecución InstanceContext agregando un nuevo estado y comportamiento utilizando su patrón de objeto extensible. El patrón de objeto extensible se utiliza en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para extender clases de tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características del estado a un objeto. Hay tres interfaces en el patrón de objeto extensible - IExtensibleObject\<T >, IExtension\<T > e IExtensionCollection\<T >:  
  
-   El IExtensibleObject\<T > se implementa mediante objetos que permiten extensiones que personalicen su funcionalidad.  
  
-   IExtension\<T > interfaz se implementa mediante objetos que son extensiones de clases de tipo T.  
  
-   El IExtensionCollection\<T > interfaz es una colección de IExtensions que permite la recuperación de IExtensions por su tipo.  
  
 Por consiguiente una clase InstanceContextExtension se debería crear de tal manera que implementase la interfaz IExtension y definiese el estado necesario para guardar el id. de contexto. Esta clase también proporciona el estado para mantener al administrador de almacenamiento en uso. Una vez guardado el nuevo estado, no debería ser posible modificarlo. Por consiguiente, el estado se proporciona y guarda a la instancia en el momento en que se construye; en ese momento solo se puede tener acceso a él utilizando las propiedades de solo lectura.  
  
```  
// Constructor  
public DurableInstanceContextExtension(string contextId,   
            IStorageManager storageManager)  
{  
    this.contextId = contextId;  
    this.storageManager = storageManager;              
}  
  
// Read only properties  
public string ContextId  
{  
    get { return this.contextId; }  
}  
  
public IStorageManager StorageManager  
{  
    get { return this.storageManager; }              
}   
```  
  
 La clase InstanceContextInitializer implementa la interfaz IInstanceContextInitializer y agrega la extensión de contexto de instancia a la colección Extensions del InstanceContext construyéndose.  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
    string contextId =   
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];  
  
    DurableInstanceContextExtension extension =  
                new DurableInstanceContextExtension(contextId,   
                     storageManager);  
    instanceContext.Extensions.Add(extension);  
}  
```  
  
 Tal y como se describió con anterioridad, el id. de contexto se lee de la colección `Properties` de la clase `Message` y pasa al constructor de la clase de extensión. Esto muestra cómo la información se puede intercambiar entre las capas de una manera coherente.  
  
 El paso importante siguiente es invalidar el proceso de creación de la instancia de servicio. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite la implementación de comportamientos personalizados de creación de instancia y su enlace al tiempo de ejecución mediante la interfaz IInstanceProvider. La nueva clase `InstanceProvider` se implementa para hacer ese trabajo. En el constructor se acepta el tipo de servicio esperado del proveedor de instancias. Después se utiliza para crear nuevas instancias. En la implementación `GetInstance` una instancia de un administrador de almacenamiento se crea buscando una instancia conservada. Si devuelve a continuación `null` entonces una nueva instancia del tipo de servicio se crea y se devuelve al llamador.  
  
```  
public object GetInstance(InstanceContext instanceContext, Message message)  
{  
    object instance = null;  
  
    DurableInstanceContextExtension extension =  
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();  
  
    string contextId = extension.ContextId;  
    IStorageManager storageManager = extension.StorageManager;              
  
    instance = storageManager.GetInstance(contextId, serviceType);          
  
    if (instance == null)  
    {  
        instance = Activator.CreateInstance(serviceType);  
    }  
  
    return instance;  
}  
```  
  
 El siguiente paso importante es instalar el `InstanceContextExtension`, `InstanceContextInitializer` y las clases `InstanceProvider` en el tiempo de ejecución del modelo de servicio. Podría utilizarse un atributo personalizado para marcar las clases de implementación de servicio para instalar el comportamiento. `DurableInstanceContextAttribute` contiene la implementación para este atributo e implementa la interfaz `IServiceBehavior` para extender el tiempo de ejecución del servicio por completo.  
  
 Esta clase tiene una propiedad que acepta el tipo del administrador de almacenamiento que se va a utilizar. De esta manera la implementación les permite a los usuarios especificar su propia implementación `IStorageManager` como parámetro de este atributo.  
  
 En la implementación `ApplyDispatchBehavior`el `InstanceContextMode` del atributo `ServiceBehavior` actual se comprueba. Si esta propiedad está establecida en Singleton, no es posible habilitar la creación de instancias duraderas y se inicia un `InvalidOperationException` para notificar al host.  
  
```  
ServiceBehaviorAttribute serviceBehavior =  
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();  
  
if (serviceBehavior != null &&  
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)  
{  
    throw new InvalidOperationException(  
       ResourceHelper.GetString("ExSingeltonInstancingNotSupported"));  
}  
```  
  
 Después de esto se crean las instancias del administrador de almacenamiento, el inicializador de contexto de instancias y el proveedor de instancias, y se instalan en `DispatchRuntime` creado para cada extremo.  
  
```  
IStorageManager storageManager =   
    StorageManagerFactory.GetStorageManager(storageManagerType);  
  
InstanceContextInitializer contextInitializer =  
    new InstanceContextInitializer(storageManager);  
  
InstanceProvider instanceProvider =  
    new InstanceProvider(description.ServiceType);  
  
foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
{  
    ChannelDispatcher cd = cdb as ChannelDispatcher;  
  
    if (cd != null)  
    {  
        foreach (EndpointDispatcher ed in cd.Endpoints)  
        {  
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);  
            ed.DispatchRuntime.InstanceProvider = instanceProvider;  
        }  
    }  
}  
```  
  
 Resumiendo hasta ahora, este ejemplo ha generado un canal que habilita el protocolo de conexión personalizado para el intercambio de id. de contexto personalizado y también sobrescribe el comportamiento de la creación de instancias predeterminado para cargar las instancias desde el almacenamiento persistente.  
  
 Lo que queda es un modo de guardar la instancia del servicio en el almacenamiento persistente. Como se dijo con anterioridad, ya existe la funcionalidad necesaria para guardar el estado en una implementación `IStorageManager`. Debemos integrar ahora esto con el tiempo de ejecución [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Se requiere otro atributo, que es aplicable a los métodos en la clase de implementación de servicio. Se supone que este atributo se aplica a los métodos que cambian el estado de la instancia del servicio.  
  
 La clase `SaveStateAttribute` implementa esta funcionalidad. También implementa la clase `IOperationBehavior` para modificar el tiempo de ejecución [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para cada operación. Cuando un método se marca con este atributo, el tiempo de ejecución [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoca el método `ApplyBehavior` mientras se construye el `DispatchOperation` adecuado. En esta implementación de método hay línea única de código:  
  
```  
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);  
```  
  
 Esta instrucción crea una instancia del tipo `OperationInvoker` y lo asigna a la propiedad `Invoker` de `DispatchOperation` construyéndose. La clase `OperationInvoker` es un contenedor para el invocador de la operación predeterminado creado para `DispatchOperation`. Esta clase implementa la interfaz `IOperationInvoker`. En la implementación del método `Invoke` la invocación de método real se delega al invocador de operación interno. Sin embargo, antes de devolver los resultados el administrador de almacenamiento en `InstanceContext` se utiliza para guardar la instancia del servicio.  
  
```  
object result = innerOperationInvoker.Invoke(instance,  
    inputs, out outputs);  
  
// Save the instance using the storage manager saved in the   
// current InstanceContext.  
InstanceContextExtension extension =  
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();  
  
extension.StorageManager.SaveInstance(extension.ContextId, instance);  
return result;  
```  
  
## <a name="using-the-extension"></a>Utilizar la extensión  
 Se realizan las extensiones de la capa del canal y de la capa del modelo de servicio; desde este momento se pueden utilizar en aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Los servicios tienen que agregar el canal en la pila del canal utilizando un enlace personalizado y a continuación marcar las clases de implementación de servicio con los atributos adecuados.  
  
```  
[DurableInstanceContext]  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class ShoppingCart : IShoppingCart  
{  
//…  
     [SaveState]  
     public int AddItem(string item)  
     {  
         //…  
     }  
//…  
 }  
```  
  
 Las aplicaciones Cliente deben agregar DurableInstanceContextChannel en la pila de canal utilizando un enlace personalizado. Para configurar mediante declaración el canal en el archivo de configuración, la sección de elemento de enlace tiene que ser agregada a la colección de extensiones de elemento de enlace.  
  
```xml  
<system.serviceModel>  
 <extensions>  
   <bindingElementExtensions>  
     <add name="durableInstanceContext"  
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
   </bindingElementExtensions>  
 </extensions>  
```  
  
 Ahora el elemento de enlace se puede utilizar con un enlace personalizado, del mismo modo que otros elementos de enlace estándar:  
  
```xml  
<bindings>  
 <customBinding>  
   <binding name="TextOverHttp">  
     <durableInstanceContext contextType="HttpCookie"/>             
     <reliableSession />  
     <textMessageEncoding />  
     <httpTransport />  
   </binding>  
 </customBinding>  
</bindings>  
```  
  
## <a name="conclusion"></a>Conclusión  
 Este ejemplo mostró cómo crear un canal protocolar personalizado y cómo personalizar el comportamiento del servicio para habilitarlo.  
  
 La extensión se puede mejorar más, permitiendo a los usuarios especificar la implementación `IStorageManager` mediante una sección de configuración. Esto permite modificar la memoria auxiliar sin recompilar el código de servicio.  
  
 Además, puede intentar implementar una clase (por ejemplo, `StateBag`), que encapsula el estado de la instancia. Esa clase es responsable por haber conservado el estado cada vez que cambia. De esta manera puede evitar utilizar el atributo `SaveState` y realizar el trabajo persistente con más precisión (por ejemplo, podría conservar el estado cuando se cambia realmente el estado, en lugar de guardarlo cada vez que se llama a un método con el atributo `SaveState` ).  
  
 Al ejecutar el ejemplo, se muestra el resultado siguiente. El cliente agrega dos elementos a su carro de la compra y, a continuación, recibe la lista de elementos en su carro de la compra desde el servicio. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
```  
Enter the name of the product: apples  
Enter the name of the product: bananas  
  
Shopping cart currently contains the following items.  
apples  
bananas  
Press ENTER to shut down client  
```  
  
> [!NOTE]
>  Al recompilar el servicio, se sobrescribe el archivo de base de datos. Para observar el estado conservado durante varias ejecuciones del ejemplo, asegúrese de no recompilar el ejemplo entre las distintas ejecuciones.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
>  Debe estar ejecutando SQL Server 2005 o SQL Express 2005 para ejecutar este ejemplo. Si está ejecutando SQL Server 2005, debe modificar la configuración de la cadena de conexión del servicio. Al ejecutar un equipo cruzado, SQL Server sólo se requiere en el equipo del servidor.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`  
  
## <a name="see-also"></a>Vea también
