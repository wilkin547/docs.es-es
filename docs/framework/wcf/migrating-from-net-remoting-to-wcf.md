---
title: Migración de .NET Remoting a WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 4b6996b01da6312486649482ffbb812fcb021306
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452557"
---
# <a name="migrating-from-net-remoting-to-wcf"></a>Migración de .NET Remoting a WCF
En este artículo se describe el procedimiento para migrar una aplicación que usa .NET Remoting para que use Windows Communication Foundation (WCF). Se comparan conceptos similares entre estos productos y se describe cómo llevar a cabo varios escenarios comunes de comunicación remota en WCF.  
  
 .NET Remoting es un producto heredado que solo se admite para la compatibilidad con versiones anteriores. No es seguro en entornos de confianza mixta porque no puede mantener los niveles de confianza independientes entre el cliente y el servidor. Por ejemplo, nunca debe exponer un punto de conexión de .NET Remoting a Internet o a los clientes que no son de confianza. Recomendamos que las aplicaciones de Remoting existentes se migren a tecnologías más recientes y seguras. Si el diseño de la aplicación solo usa HTTP y es RESTful, recomendamos ASP.NET Web API. Para obtener más información, consulte ASP.NET Web API. Si la aplicación se basa en SOAP o necesita protocolos que no sean HTTP, como TCP, recomendamos WCF.  

## <a name="comparing-net-remoting-to-wcf"></a>Comparación de .NET Remoting con WCF  
 En esta sección se comparan los bloques de creación básicos de .NET Remoting con sus equivalentes de WCF. Usaremos estos bloques de creación más adelante para crear algunos escenarios comunes de cliente-servidor en WCF. En el gráfico siguiente se resumen las similitudes y diferencias principales entre .NET Remoting y WCF.  
  
||.NET Remoting|WCF|  
|-|-------------------|---------|  
|Tipo de servidor|Subclase de MarshalByRefObject|Marcar con el atributo [ServiceContract]|  
|Operaciones de servicio|Métodos públicos en el tipo de servidor|Marcar con el atributo [OperationContract]|  
|Serialización|ISerializable o [Serializable]|DataContractSerializer o XmlSerializer|  
|Objetos pasados|Por valor o por referencia|Solo por valor|  
|Errores y excepciones|Cualquier excepción serializable|FaultContract\<TDetail >|  
|Objetos proxy de cliente|Los servidores proxy transparentes fuertemente tipados se crean automáticamente desde MarshalByRefObjects|Los proxies fuertemente tipados se generan a petición mediante ChannelFactory\<TChannel >|  
|Plataforma necesaria|Tanto el cliente como el servidor deben usar Microsoft OS y .NET|Multiplataforma|  
|Formato de los mensajes|Privada|Estándares del sector (SOAP, WS-*, etc.)|  
  
### <a name="server-implementation-comparison"></a>Comparación de la implementación del servidor  
  
#### <a name="creating-a-server-in-net-remoting"></a>Crear un servidor en .NET Remoting  
 Los tipos de servidor de .NET Remoting se deben derivar de MarshalByRefObject y definen los métodos a los que el cliente puede llamar, como el siguiente:  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 Los métodos públicos de este tipo de servidor se convierten en el contrato público disponible para los clientes.  No hay una separación entre la interfaz pública del servidor y su implementación: un solo tipo controla ambas.  
  
 Una vez definido el tipo de servidor, se puede poner a disposición de los clientes, como en el siguiente ejemplo:  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),   
    "RemotingServer",   
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 Hay muchas maneras de hacer que el tipo de Remoting esté disponible como servidor, incluido el uso de archivos de configuración. Esto es solo un ejemplo.  
  
#### <a name="creating-a-server-in-wcf"></a>Crear un servidor en WCF  
 El paso equivalente en WCF implica la creación de dos tipos: el "contrato de servicio" público y la implementación concreta. El primero se declara como una interfaz marcada con [ServiceContract]. Los métodos disponibles para los clientes se marcan con [OperationContract]:  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 la implementación del servidor se define en una clase independiente concreta, como en el siguiente ejemplo:  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 Una vez definidos estos tipos, el servidor WCF se puede poner a disposición de los clientes, como en el siguiente ejemplo:  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine($"The WCF server is ready at {baseAddress}.");
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
> TCP se usa en los dos ejemplos para que sean lo más parecidos posible. Consulte los tutoriales más adelante en este tema para obtener ejemplos usando HTTP.  
  
 Existen muchas formas de configurar y hospedar los servicios WCF. Este es solo un ejemplo, conocido como "autohospedado". Para obtener más información, vea los temas siguientes:  
  
- [Cómo definir un contrato de servicios](how-to-define-a-wcf-service-contract.md)  
  
- [Configuración de servicios mediante archivos de configuración](configuring-services-using-configuration-files.md)  
  
- [Servicios de hospedaje](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a>Comparación de la implementación del cliente  
  
#### <a name="creating-a-client-in-net-remoting"></a>Crear un cliente en .NET Remoting  
 Una vez que un objeto de servidor de .NET Remoting está disponible, los clientes lo pueden consumir, como en el siguiente ejemplo:  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),   
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 La instancia RemotingServer devuelta desde Activator.GetObject () se denomina "proxy transparente". Implementa la API pública para el tipo RemotingServer en el cliente, pero todos los métodos llaman al objeto de servidor que se ejecuta en un proceso o una máquina distinta.  
  
#### <a name="creating-a-client-in-wcf"></a>Crear un cliente en WCF  
 El paso equivalente en WCF implica el uso de un generador de canales para crear el proxy de forma explícita. Como en Remoting, el objeto proxy se puede usar para invocar operaciones en el servidor, como en el siguiente ejemplo:  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =   
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 Este ejemplo muestra la programación en el nivel de canal porque es más similar al ejemplo de Remoting. También está disponible el enfoque de **Agregar referencia de servicio** en Visual Studio que genera código para simplificar la programación de cliente. Para obtener más información, vea los temas siguientes:  
  
- [Programación de nivel de canal de cliente](./extending/client-channel-level-programming.md)  
  
- [Cómo: agregar, actualizar o quitar una referencia de servicio](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a>Uso de la serialización  
 Tanto .NET Remoting como WCF usan la serialización para enviar objetos entre el cliente y el servidor, pero se diferencian en estos aspectos importantes:  
  
1. Usan convenciones y serializadores diferentes para indicar qué se debe serializar.  
  
2. .NET Remoting admite la serialización "por referencia" que permite el acceso del método o la propiedad a un nivel para ejecutar el código en el otro nivel que se encuentra fuera de los límites de seguridad. Esta capacidad expone las vulnerabilidades de seguridad y es uno de los principales motivos por los que no se deben exponer nunca los extremos de Remoting a clientes que no sean de confianza.  
  
3. La serialización que usa .NET Remoting no es participativa (excluye explícitamente lo que no hay que serializar) y la serialización de WCF es participativa (marca explícitamente los miembros para serializar).  
  
#### <a name="serialization-in-net-remoting"></a>Serialización en .NET Remoting  
 .NET Remoting admite dos modos para serializar y deserializar objetos entre el cliente y el servidor:  
  
- *Por valor* : los valores del objeto se serializan a través de los límites del nivel y se crea una nueva instancia de ese objeto en el otro nivel. Las llamadas a los métodos o las propiedades de la nueva instancia solo se ejecutan localmente y no afectan al objeto o al nivel original.  
  
- *Por referencia* : una "referencia de objeto" especial se serializa a través de los límites del nivel. Cuando un nivel interactúa con los métodos o las propiedades de ese objeto, se comunica de nuevo al objeto original del nivel original. Los objetos por referencia pueden fluir en cualquier dirección: de servidor a cliente o de cliente a servidor.  
  
 Los tipos por valor de Remoting se marcan con el atributo [Serializable] o implementan ISerializable, como en el siguiente ejemplo:  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 Los tipos por referencia se derivan de la clase MarshalByRefObject, como en el siguiente ejemplo:  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 Es muy importante comprender las implicaciones de los objetos por referencia de Remoting. Si cualquier nivel (cliente o servidor) envía un objeto por referencia al otro nivel, todas las llamadas de método se ejecutan en el nivel que posee el objeto. Por ejemplo, un cliente que llame a los métodos en un objeto por referencia devuelto por el servidor ejecutará el código en el servidor. De forma similar, un servidor que llame a los métodos en un objeto por referencia que proporciona el cliente ejecutará el código en el cliente. Por este motivo, solo se recomienda el uso de .NET Remoting en entornos de plena confianza. Exponer un extremo de .NET Remoting público a clientes sin confianza hará que un servidor de Remoting sea vulnerable a los ataques.  
  
#### <a name="serialization-in-wcf"></a>Serialización en WCF  
 WCF solo admite la serialización por valor. El modo más común de definir un tipo para el intercambio entre el cliente y el servidor es como en el siguiente ejemplo:  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 El atributo [DataContract] identifica este tipo como uno que se puede serializar y deserializar entre el cliente y el servidor. El atributo [DataMember] identifica las propiedades o los campos individuales para serializar.  
  
 Cuando WCF envía un objeto entre niveles, solo serializa los valores y crea una nueva instancia del objeto en el otro nivel. Cualquier interacción con los valores del objeto se produce solo localmente; no se comunican con el nivel del mismo modo que lo hacen los objetos por referencia de .NET Remoting. Para obtener más información, vea [serialización y deserialización](./feature-details/serialization-and-deserialization.md).  
  
### <a name="exception-handling-capabilities"></a>Capacidades de control de excepciones  
  
#### <a name="exceptions-in-net-remoting"></a>Excepciones en .NET Remoting  
 Las excepciones producidas por un servidor de Remoting se serializan, se envían al cliente y se producen localmente en el cliente, como cualquier otra excepción. Las excepciones personalizadas se pueden crear subclasificando el tipo de excepción y marcándolo con [Serializable].   La mayoría de las excepciones de marco ya están marcadas de este modo, lo que permite que el servidor produzca la mayoría, se serialicen y se vuelvan a producir en el cliente. Aunque este diseño es adecuado durante el desarrollo, la información del lado servidor se puede divulgar accidentalmente al cliente. Este es uno de los muchos motivos por los que Remoting solo se debe usar en entornos de plena confianza.  
  
#### <a name="exceptions-and-faults-in-wcf"></a>Excepciones y errores en WCF  
 WCF no admite la devolución de tipos de excepción arbitrarios del servidor al cliente porque podrían provocar la divulgación accidental de información. Si una operación de servicio produce una excepción inesperada, hace que se produzca una excepción FaultException de propósito general en el cliente. Esta excepción no contiene información del motivo o el lugar en el que ocurrió el problema y, para algunas aplicaciones, es suficiente. Las aplicaciones que necesitan comunicar más información del error al cliente lo hacen definiendo un contrato de error.  
  
 Para ello, primero crean un tipo [DataContract] para transportar la información del error.  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 Especifican el contrato de error que se usará para cada operación de servicio.  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 El servidor informa de las condiciones del error produciendo una excepción  FaultException.  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {   
        CustomerId = customerId,   
        ErrorMessage = "Illegal customer Id"   
    });  
```  
  
 Y, siempre que el cliente realice una solicitud al servidor, puede detectar errores como excepciones normales.  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine($"Fault received: {fault.Detail.ErrorMessage}");
}  
```  
  
 Para obtener más información sobre los contratos de errores, consulte <xref:System.ServiceModel.FaultException>.  
  
### <a name="security-considerations"></a>Consideraciones sobre la seguridad  
  
#### <a name="security-in-net-remoting"></a>Seguridad en .NET Remoting  
 Algunos canales de .NET Remoting admiten características de seguridad como la autenticación y el cifrado en el nivel de canal (IPC y TCP). El canal HTTP se basa en Internet Information Services (IIS) para la autenticación y el cifrado. A pesar de esta compatibilidad, debe considerar .NET Remoting como un protocolo de comunicación no seguro y usarlo solo en entornos de plena confianza. No exponga nunca un extremo de Remoting público a Internet o a clientes que no sean de confianza.  
  
#### <a name="security-in-wcf"></a>Seguridad en WCF  
 WCF se diseñó teniendo en cuenta la seguridad, en parte para tratar los tipos de vulnerabilidades que se encuentran en .NET Remoting. WCF ofrece seguridad a nivel de mensajes y transporte, y ofrece muchas opciones para la autenticación, la autorización, el cifrado, etc. Para obtener más información, vea los temas siguientes:  
  
- [Seguridad](./feature-details/security.md)  
  
- [Instrucciones de seguridad de WCF](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a>Migrar a WCF  
  
### <a name="why-migrate-from-remoting-to-wcf"></a>¿Por qué migrar de Remoting a WCF?  
  
- **.NET Remoting es un producto heredado.** Tal y como se describe en [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), se considera un producto heredado y no se recomienda para el nuevo desarrollo. Se recomienda WCF o ASP.NET Web API para aplicaciones nuevas y existentes.  
  
- **WCF usa estándares multiplataforma.** WCF se diseñó teniendo en cuenta la interoperabilidad multiplataforma y admite muchos estándares del sector (SOAP, WS-Security, WS-Trust, etc.). Un servicio WCF puede interoperar con clientes que se ejecuten en sistemas operativos distintos de Windows. La comunicación remota se diseñó principalmente para entornos en los que las aplicaciones cliente y servidor se ejecutan con .NET Framework en un sistema operativo Windows.
  
- **WCF tiene seguridad integrada.** WCF se diseñó teniendo en cuenta la seguridad y ofrece muchas opciones de autenticación, seguridad de nivel de transporte, seguridad de nivel de mensaje, etc. La comunicación remota se diseñó para facilitar la interoperabilidad de las aplicaciones, pero no se diseñó para ser segura en entornos que no son de confianza. WCF se diseñó para funcionar en entornos de confianza y de no confianza.  
  
### <a name="migration-recommendations"></a>Recomendaciones de migración  
 Estos son los pasos recomendados para migrar de .NET Remoting a WCF:  
  
- **Cree el contrato de servicio.** Defina los tipos de interfaz de servicio y márquelos con el atributo [ServiceContract]. Marque todos los métodos a los que podrán llamar los clientes con [OperationContract].  
  
- **Cree el contrato de datos.** Defina los tipos de datos que se intercambiarán entre el cliente y el servidor, y márquelos con el atributo [DataContract]. Marque todos los campos y propiedades que podrá usar el cliente con [DataMember].  
  
- **Cree el contrato de error (opcional).** Cree los tipos que se intercambiarán entre el cliente y el servidor cuando se produzcan errores. Marque estos tipos con [DataContract] y [DataMember] para que se puedan serializar. Marque también con [FaultContract] todas las operaciones de servicio que marcó con [OperationContract] para indicar qué errores pueden devolver.  
  
- **Configurar y hospedar el servicio.** Una vez creado el contrato de servicio, el siguiente paso es configurar un enlace para exponer el servicio a un punto de conexión. Para obtener más información, vea [puntos de conexión: direcciones, enlaces y contratos](./feature-details/endpoints-addresses-bindings-and-contracts.md).  
  
 Una vez migrada la aplicación de Remoting a WCF, es importante quitar las dependencias de .NET Remoting. Esto garantiza que se quitan las vulnerabilidades de Remoting de la aplicación. Estos pasos son los siguientes:  
  
- **El uso de MarshalByRefObject es discontinuo.** El tipo MarshalByRefObject solo existe para Remoting y WCF no lo usa. Se debe quitar o cambiar cualquier tipo de aplicación que subclasifique MarshalByRefObject.  
  
- **Dejar de usar [Serializable] y ISerializable.** El atributo [Serializable] y la interfaz ISerializable se diseñaron originalmente para serializar los tipos dentro de entornos de confianza y Remoting los usa. La serialización de WCF se basa en los tipos marcados con [DataContract] y [DataMember]. Los tipos de datos que usa una aplicación se deben modificar para usar [DataContract] y no para usar ISerializable o [Serializable].  
  
### <a name="migration-scenarios"></a>Escenarios de migración  
 Ahora veamos cómo conseguir los siguientes escenarios comunes de Remoting en WCF:  
  
1. El servidor devuelve un objeto por valor al cliente  
  
2. El servidor devuelve un objeto por referencia al cliente  
  
3. El cliente envía un objeto por valor al servidor  
  
> [!NOTE]
> No se permite el envío de un objeto por referencia desde el cliente al servidor en WCF.  
  
 Al leer estos escenarios, suponga que nuestras interfaces de línea base para .NET Remoting son parecidas al siguiente ejemplo. Aquí, la implementación de .NET Remoting no es importante porque solo queremos mostrar cómo usar WCF para implementar una funcionalidad equivalente.  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a>Escenario 1: el servicio devuelve un objeto por valor  
 Este escenario muestra un servidor que devuelve un objeto al cliente por valor. WCF siempre devuelve los objetos desde el servidor por valor, por lo que los siguientes pasos solo describen cómo compilar un servicio WCF normal.  
  
1. Empiece definiendo una interfaz pública para el servicio WCF y márquela con el atributo [ServiceContract]. Usamos [OperationContract] para identificar los métodos del lado servidor a los que llamará nuestro cliente.  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2. El siguiente paso es crear el contrato de datos para este servicio. Lo hacemos creando clases (no interfaces) marcadas con el atributo [DataContract]. Las propiedades o los campos individuales que queremos que sean visibles para el cliente y el servidor se marcan con [DataMember]. Si queremos permitir los tipos derivados, debemos usar el atributo [KnownType] para identificarlos. Los únicos tipos que WCF permite serializar o deserializar para este servicio son los de la interfaz de servicio y estos "tipos conocidos". Se rechazarán los intentos de intercambiar cualquier otro tipo que no se encuentre en esta lista.  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer   
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3. A continuación, ofrecemos la implementación de la interfaz de servicio.  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4. Para ejecutar el servicio WCF, debemos declarar un extremo que exponga esa interfaz de servicio en una dirección URL específica con un enlace WCF específico. Normalmente, esto se lleva a cabo agregando las siguientes secciones al archivo web.config del proyecto de servidor.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5. A continuación, se puede iniciar el servicio WCF con el siguiente código:  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     Cuando se inicia este ServiceHost, usa el archivo web.config para establecer el contrato, el enlace y el extremo adecuados. Para obtener más información sobre los archivos de configuración, vea [configuración de servicios mediante archivos de configuración](./configuring-services-using-configuration-files.md). Este estilo de inicio del servidor se conoce como autohospedaje. Para obtener más información sobre otras opciones para hospedar servicios WCF, vea [servicios de hospedaje](./hosting-services.md).  
  
6. El archivo app.config del proyecto de cliente debe declarar la información de enlace coincidente para el punto de conexión del servicio. La forma más fácil de hacerlo en Visual Studio es usar **Agregar referencia de servicio**, que actualizará automáticamente el archivo app. config. Además, estos cambios se pueden agregar manualmente.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Para obtener más información acerca del uso de **Agregar referencia de servicio**, consulte [Cómo: agregar, actualizar o quitar una referencia de servicio](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).  
  
7. Ahora podemos llamar al servicio WCF desde el cliente. Para ello creamos un generador de canales para el servicio, solicitando un canal y llamando directamente al método que queremos en ese canal. Podemos hacerlo porque el canal implementa la interfaz del servicio y controla la lógica de la solicitud o la respuesta subyacente para nosotros. El valor devuelto de esta llamada al método es la copia deserializada de la respuesta del servidor.  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 Los objetos devueltos por WCF desde el servidor al cliente siempre son por valor. Los objetos son copias deserializadas de los datos enviados por el servidor. El cliente puede llamar a métodos en estas copias locales sin riesgo de invocar código de servidor a través de devoluciones de llamada.  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a>Escenario 2: el servidor devuelve un objeto por referencia  
 Este escenario muestra el servidor que proporciona un objeto al cliente por referencia. En .NET Remoting, esto se controla de forma automática para cualquier tipo derivado de MarshalByRefObject, que se serializa por referencia. Un ejemplo de este escenario es permitir que varios clientes tengan objetos del lado servidor con sesión independientes. Como se mencionó anteriormente, los objetos devueltos por un servicio WCF siempre son por valor, por lo que no hay ningún equivalente directo de un objeto por referencia, pero es posible conseguir algo similar a la semántica por referencia con un objeto <xref:System.ServiceModel.EndpointAddress10>. Se trata de un objeto por valor serializable que puede usar el cliente para obtener un objeto por referencia con sesión en el servidor. Esto habilita el escenario de tener varios clientes con objetos del lado servidor con sesión independientes.  
  
1. Primero necesitamos definir un contrato de servicio WCF que se corresponda con el propio objeto con sesión.  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    > Tenga en cuenta que el objeto con sesión está marcado con [ServiceContract], lo que hace que sea una interfaz de servicio WCF normal. El hecho de establecer la propiedad SessionMode indica que será un servicio con sesión. En WCF, una sesión es una manera de asociar varios mensajes enviados entre dos puntos de conexión. Esto significa que cuando un cliente obtiene una conexión a este servicio, se establecerá una sesión entre el cliente y el servidor. El cliente usará una única instancia del objeto del lado servidor para todas las interacciones dentro de esta sesión única.  
  
2. A continuación, debemos proporcionar la implementación de esta interfaz de servicio. Al representarlo con [ServiceBehavior] y al configurar InstanceContextMode, le indicamos a WCF que queremos usar una instancia única de este tipo para cada sesión.  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3. Ahora necesitamos un modo de obtener una instancia de este objeto con sesión. Para ello, creamos otra interfaz de servicio WCF que devuelva un objeto EndpointAddress10. Se trata de un formato serializable de un punto de conexión que el cliente puede usar para crear el objeto con sesión.  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     E implementamos este servicio WCF:  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =   
               new ChannelFactory<ISessionBoundObject>("sessionbound");  
 
           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     Esta implementación mantiene un generador de canales de singleton para crear objetos con sesión. Cuando se llama a GetInstanceAddress(), crea un canal y crea un objeto EndpointAddress10 que apunta de forma efectiva a la dirección remota asociada a este canal. EndpointAddress10 es simplemente un tipo de datos que se puede devolver al cliente por valor.  
  
4. Debemos modificar el archivo de configuración del servidor mediante las siguientes dos cosas que se muestran en el siguiente ejemplo:  
  
    1. Declare una sección > de cliente de \<que describa el punto de conexión para el objeto con sesión. Esto es necesario porque el servidor también actúa como un cliente en esta situación.  
  
    2. Declare los extremos para el objeto de generador y el objeto con sesión. Esto es necesario para permitir que el cliente se comunique con los puntos de conexión del servicio para adquirir EndpointAddress10 y para crear el canal con sesión.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     A continuación, podemos iniciar estos servicios:  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. Configuramos el cliente declarando estos mismos puntos de conexión en el archivo app.config de su proyecto.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6. Para crear y usar este objeto con sesión, el cliente debe seguir estos pasos:  
  
    1. Crear un canal para el servicio ISessionBoundFactory.  
  
    2. Usar ese canal para invocar el servicio para obtener EndpointAddress10.  
  
    3. Usar EndpointAddress10 para crear un canal para obtener un objeto con sesión.  
  
    4. Interactuar con el objeto con sesión para mostrar que sigue siendo la misma instancia en varias llamadas.  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =   
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 WCF siempre devuelve objetos por valor, pero es posible que admita el equivalente de la semántica por referencia con EndpointAddress10. Esto permite que el cliente solicite una instancia de servicio WCF con sesión, tras lo cual puede interactuar con ella como con cualquier otro servicio WCF.  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a>Escenario 3: el cliente envía al servidor una instancia por valor  
 Este escenario muestra el cliente enviando una instancia de objeto no primitivo al servidor por valor. Dado que WCF solo envía objetos por valor, este escenario muestra el uso de WCF normal.  
  
1. Use el mismo servicio WCF del escenario 1.  
  
2. Use el cliente para crear un nuevo objeto por valor (Customer), cree un canal para comunicarse con el servicio ICustomerService y envíele el objeto.  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {   
   FirstName = "Bob",   
   LastName = "Jones",   
   CustomerId = 43,   
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine($"  Server returned {success}.");
   ```  
  
     El objeto de cliente se serializa y se envía al servidor, donde se deserializa en una nueva copia de dicho objeto.  
  
    > [!NOTE]
    > Este código también muestra el envío de un tipo derivado (PremiumCustomer). La interfaz de servicio espera un objeto Customer, pero el atributo [KnownType] de la clase Customer indica que también se permite PremiumCustomer. WCF no podrá serializar o deserializar cualquier otro tipo a través de esta interfaz de servicio.  
  
 Los intercambios de datos de WCF normales son por valor. Esto garantiza que la invocación de métodos en uno de estos objetos de datos solo se ejecuta localmente; no invocará código en el otro nivel. Aunque es posible lograr algo similar a los objetos por referencia devueltos *desde* el servidor, no es posible que un cliente pase un objeto por referencia *al* servidor. En WCF puede conseguir un escenario que necesite una conversación entre el cliente y el servidor con un servicio dúplex. Para obtener más información, vea [servicios dúplex](./feature-details/duplex-services.md).  
  
## <a name="summary"></a>Resumen  
 .NET Remoting es un marco de comunicación diseñado para su uso únicamente en entornos de plena confianza. Se trata de un producto heredado que solo se admite para la compatibilidad con versiones anteriores. No se debe usar para compilar nuevas aplicaciones. En cambio, WCF se diseñó teniendo en cuenta la seguridad y se recomienda para las aplicaciones nuevas y existentes. Microsoft recomienda la migración de las aplicaciones Remoting existentes para usar WCF o ASP.NET Web API en su lugar.
