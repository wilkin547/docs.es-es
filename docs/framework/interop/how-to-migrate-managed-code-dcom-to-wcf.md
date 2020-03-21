---
title: 'Cómo: Migrar código administrado DCOM a WCF'
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: 2576e88c25ae381e90ec7d613efb648048145b3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181390"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a>Cómo: Migrar código administrado DCOM a WCF
Windows Communication Foundation (WCF) es la opción recomendada y segura para reemplazar al modelo de objetos de componentes distribuidos (DCOM) en las llamadas de código administrado entre servidores y clientes en un entorno distribuido. En este artículo se muestra cómo migrar el código de DCOM a WCF en los escenarios siguientes.  
  
- El servicio remoto devuelve un objeto por valor al cliente.  
  
- El cliente envía un objeto por valor al servicio remoto.  
  
- El servicio remoto devuelve un objeto por referencia al cliente.  
  
 Por motivos de seguridad, en WCF no se permite enviar objetos por referencia desde el cliente al servicio. En WCF puede conseguir un escenario que necesite una conversación entre el cliente y el servidor con un servicio dúplex.  Para más información sobre los servicios dúplex, vea [Duplex Services](../wcf/feature-details/duplex-services.md) (Servicios dúplex).  
  
 Para obtener más detalles sobre cómo crear servicios WCF y clientes para esos servicios, vea [Programación basica de WFC](../wcf/basic-wcf-programming.md), [Diseño e implementación de servicios](../wcf/designing-and-implementing-services.md) y [Creación de clientes](../wcf/building-clients.md).  
  
## <a name="dcom-example-code"></a>Código de ejemplo DCOM  
 Para estos escenarios, las interfaces DCOM que se muestran con WCF tienen la siguiente estructura:  
  
```csharp  
[ComVisible(true)]  
[Guid("AA9C4CDB-55EA-4413-90D2-843F1A49E6E6")]  
public interface IRemoteService  
{  
   Customer GetObjectByValue();  
   IRemoteObject GetObjectByReference();  
   void SendObjectByValue(Customer customer);  
}  
  
[ComVisible(true)]  
[Guid("A12C98DE-B6A1-463D-8C24-81E4BBC4351B")]  
public interface IRemoteObject  
{  
}  
  
public class Customer  
{  
}  
```  
  
## <a name="the-service-returns-an-object-by-value"></a>El servicio devuelve un objeto por valor  
 En este escenario, se realiza una llamada a un servicio y el método devuelve un objeto que se pasa por valor desde el servidor al cliente. Este escenario representa la siguiente llamada COM:  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 En este escenario, el cliente recibe una copia deserializada de un objeto desde el servicio remoto. El cliente puede interactuar con esta copia local sin tener que volver a llamar al servicio.  En otras palabras, se garantiza al cliente que el servicio no participará en modo alguno cuando se llame a métodos en la copia local. WCF siempre devuelve objetos desde el servicio por valor, por lo que los pasos siguientes describen la creación de un servicio WCF normal.  
  
### <a name="step-1-define-the-wcf-service-interface"></a>Paso 1: Definir la interfaz de servicio WCF  
 Defina una interfaz pública para el servicio WCF y márquela con el atributo [<xref:System.ServiceModel.ServiceContractAttribute>].  Marque los métodos que desea exponer a los clientes con el atributo [<xref:System.ServiceModel.OperationContractAttribute>]. En el ejemplo siguiente se muestra cómo usar estos atributos para identificar la interfaz del servidor y los métodos de interfaz a los que puede llamar un cliente. El método usado para este escenario se muestra en negrita.  
  
```csharp  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Web;
. . .  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]  
    void StoreCustomer(Customer customer);  
  
    [OperationContract]     Customer GetCustomer(string firstName, string lastName);
  
}  
```  
  
### <a name="step-2-define-the-data-contract"></a>Paso 2: Definir el contrato de datos  
 A continuación debe crear un contrato de datos para el servicio, en el que se describirá cómo se intercambian los datos entre el servicio y sus clientes.  Las clases descritas en el contrato de datos deben marcarse con el atributo [<xref:System.Runtime.Serialization.DataContractAttribute>]. Las propiedades o los campos individuales que quiera que sean visibles para el cliente y el servidor deben marcarse con el atributo [<xref:System.Runtime.Serialization.DataMemberAttribute>]. Si quiere que los tipos derivados de una clase estén permitidos en el contrato de datos, debe identificarlos con el atributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>]. WCF solo serializará o deserializará tipos en la interfaz de servicio y tipos identificados como tipos conocidos. Si intenta usar un tipo que no sea un tipo conocido, se producirá una excepción.  
  
 Para más información sobre los contratos de datos, vea [Data Contracts](../wcf/samples/data-contracts.md) (Contratos de datos).  
  
```csharp  
[DataContract]  
[KnownType(typeof(PremiumCustomer))]  
public class Customer  
{  
    [DataMember]  
    public string Firstname;  
    [DataMember]  
    public string Lastname;  
    [DataMember]  
    public Address DefaultDeliveryAddress;  
    [DataMember]  
    public Address DefaultBillingAddress;  
}  
 [DataContract]  
public class PremiumCustomer : Customer  
{  
    [DataMember]  
    public int AccountID;  
}  
  
 [DataContract]  
public class Address  
{  
    [DataMember]  
    public string Street;  
    [DataMember]  
    public string Zipcode;  
    [DataMember]  
    public string City;  
    [DataMember]  
    public string State;  
    [DataMember]  
    public string Country;  
}  
```  
  
### <a name="step-3-implement-the-wcf-service"></a>Paso 3: Implementar el servicio WCF  
 A continuación, debe implementar la clase de servicio WCF que implementa la interfaz que definió en el paso anterior.  
  
```csharp  
public class CustomerService: ICustomerManager
{  
    public void StoreCustomer(Customer customer)  
    {  
        // write to a database  
    }  
    public Customer GetCustomer(string firstName, string lastName)  
    {  
        // read from a database  
    }  
}  
```  
  
### <a name="step-4-configure-the-service-and-the-client"></a>Paso 4: Configurar el servicio y el cliente  
 Para ejecutar un servicio WCF, deberá declarar un punto de conexión que exponga esa interfaz de servicio en una dirección URL específica mediante un enlace WCF específico. Un enlace especifica los detalles de transporte, codificación y protocolo para que los clientes y el servidor puedan comunicarse. Normalmente, los enlaces se agregan al archivo de configuración del proyecto de servicio (web.config). A continuación se muestra una entrada de enlace para el servicio de ejemplo:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Server.CustomerService">  
        <endpoint address="http://localhost:8083/CustomerManager"
                  binding="basicHttpBinding"  
                  contract="Shared.ICustomerManager" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Después, deberá configurar el cliente para que coincida con la información de enlace especificada por el servicio. Para ello, agregue lo siguiente al archivo de configuración (app.config) de la aplicación del cliente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="customermanager"
                address="http://localhost:8083/CustomerManager"
                binding="basicHttpBinding"
                contract="Shared.ICustomerManager"/>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="step-5-run-the-service"></a>Paso 5: Ejecutar el servicio  
 Por último, puede probarlo internamente en una aplicación de consola; para ello, agregue las líneas siguientes a la aplicación de servicio e inicie la aplicación. Para más información sobre otras formas de hospedar una aplicación de servicio WCF, vea [Hosting Services](../wcf/hosting-services.md) (Servicios de hospedaje).  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a>Paso 6: Llamar al servicio desde el cliente  
 Para llamar al servicio desde el cliente, deberá crear un generador de canales para el servicio y solicitar un canal, lo que le permitirá llamar directamente al método `GetCustomer` desde el cliente. El canal implementa la interfaz del servicio y controla automáticamente la lógica de solicitud/respuesta subyacente.  El valor devuelto de esta llamada de método es la copia deserializada de la respuesta del servicio.  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a>El cliente envía un objeto por valor al servidor  
 En este escenario, el cliente envía un objeto en el servidor por valor. Esto significa que el servidor recibirá una copia del objeto deserializada.  El servidor puede llamar a métodos en esa copia con la garantía de que no habrá ninguna devolución de llamada en el código de cliente. Como se mencionó anteriormente, los intercambios normales de datos de WCF son por valor.  Esto garantiza que una llamada a métodos en uno de estos objetos se ejecuta únicamente de forma local y no invoca código en el cliente.  
  
 Este escenario representa la siguiente llamada de método COM:  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 En el escenario se usa la misma interfaz de servicio y el mismo contrato de datos que en el primer ejemplo. Además, el cliente y el servicio se configurarán de la misma manera. En este ejemplo, se crea un canal para enviar el objeto y que se ejecute de la misma manera. Sin embargo, en este ejemplo, se creará un cliente que llame al servicio pasando un objeto por valor. El método de servicio que llamará el cliente en el contrato de servicio se muestra en negrita:  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a>Agregar código al cliente que envíe un objeto por valor  
 El siguiente código muestra cómo el cliente crea un nuevo objeto de cliente por valor, crea un canal para comunicarse con el servicio `ICustomerManager` y le envía el objeto de cliente.  
  
 El objeto de cliente se serializa y se envía al servicio, donde se deserializa en una nueva copia del objeto.  Cualquier método al que llame el servicio en este objeto solo se ejecutará localmente en el servidor. Es importante que tenga en cuenta que este código ejemplifique el envío de un tipo derivado (`PremiumCustomer`).  El contrato de servicio espera un objeto `Customer`, pero los datos del servicio de contrato usan el atributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>] para indicar que `PremiumCustomer` también está permitido.  WCF no podrá serializar ni deserializar cualquier otro tipo a través de esta interfaz de servicio.  
  
```csharp  
PremiumCustomer customer = new PremiumCustomer();  
customer.Firstname = "John";  
customer.Lastname = "Doe";  
customer.DefaultBillingAddress = new Address();  
customer.DefaultBillingAddress.Street = "One Microsoft Way";  
customer.DefaultDeliveryAddress = customer.DefaultBillingAddress;  
customer.AccountID = 42;  
  
ChannelFactory<ICustomerManager> factory =  
   new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager customerManager = factory.CreateChannel();  
customerManager.StoreCustomer(customer);  
```  
  
## <a name="the-service-returns-an-object-by-reference"></a>El servicio devuelve un objeto por referencia  
 En este escenario, la aplicación cliente realiza una llamada al servicio remoto y el método devuelve un objeto que se pasa por referencia desde el servicio al cliente.  
  
 Como se mencionó anteriormente, los servicios WCF siempre devuelven objetos por valor.  Sin embargo, se puede conseguir un resultado similar usando la clase <xref:System.ServiceModel.EndpointAddress10>.  <xref:System.ServiceModel.EndpointAddress10> es un objeto serializable por valor que el cliente puede usar para obtener un objeto por referencia con sesión en el servidor.  
  
 El comportamiento del objeto por referencia de WCF que se muestra en este escenario es diferente al de DCOM.  En DCOM, el servidor puede devolver directamente un objeto por referencia al cliente y el cliente puede llamar a métodos del objeto, que se ejecutan en el servidor.  En WCF, sin embargo, el objeto devuelto es siempre por valor.  El cliente debe tomar ese objeto por valor, representado por <xref:System.ServiceModel.EndpointAddress10>, y usarlo para crear su propio objeto por referencia con sesión.  Las llamadas de método de cliente en el objeto con sesión se ejecutan en el servidor. En otras palabras, este objeto por referencia en WCF es un servicio WCF normal que se configura para ser con sesión.  
  
 En WCF, una sesión es una manera de asociar varios mensajes enviados entre dos puntos de conexión.  Esto significa que cuando un cliente obtiene una conexión a este servicio, se establecerá una sesión entre el cliente y el servidor.  El cliente usará una única instancia del objeto del lado servidor para todas las interacciones dentro de esta sesión única. Los contratos de WCF con sesión son similares a los patrones de solicitud/respuesta de red orientados a conexiones.  
  
 Este escenario se representa mediante el siguiente método DCOM.  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a>Paso 1: Definir la interfaz de servicio de WCF con sesión y la implementación  
 En primer lugar, defina una interfaz de servicio WCF que contenga el objeto con sesión.  
  
 En este código, el objeto con sesión se marca con el atributo `ServiceContract`, que lo identifica como una interfaz de servicio WCF normal.  Además, se establece la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> para indicar que será un servicio con sesión.  
  
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
  
 En el siguiente código se muestra la implementación del servicio.  
  
 El servicio se marca con el atributo [ServiceBehavior] y su propiedad InstanceContextMode se establece en InstanceContextMode.PerSessions para indicar que debe crearse una instancia única de este tipo para cada sesión.  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a>Paso 2: Definir el servicio del generador WCF para el objeto con sesión  
 El servicio que crea el objeto con sesión debe definirse e implementarse. El código siguiente muestra cómo hacerlo. Este código crea otro servicio WCF que devuelve un objeto <xref:System.ServiceModel.EndpointAddress10>.  Se trata de una forma serializable de un punto de conexión que puede usarse para crear el objeto con sesión.  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 A continuación se muestra la implementación de este servicio. Esta implementación mantiene un generador de canales de singleton para crear objetos con sesión.  Cuando se llama a `GetInstanceAddress`, este crea un canal y crea un objeto <xref:System.ServiceModel.EndpointAddress10> que apunta a la dirección remota asociada a este canal.   <xref:System.ServiceModel.EndpointAddress10> es un tipo de datos que se puede devolver al cliente por valor.
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a>Paso 3: Configurar e iniciar los servicios WCF  
 Para hospedar estos servicios, deberá agregar lo siguiente al archivo de configuración del servidor (web.config).  
  
1. Agregue una sección `<client>` que describa el extremo para el objeto con sesión.  En este escenario, el servidor también actúa como un cliente y debe configurarse para habilitar esta opción.  
  
2. En la sección `<services>`, declare los extremos de servicio para el generador y el objeto con sesión.  Esto permite al cliente comunicarse con los puntos de conexión de servicio, adquirir el <xref:System.ServiceModel.EndpointAddress10> y crear el canal con sesión.  
  
 A continuación se muestra un archivo de configuración de ejemplo con estas opciones:  
  
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
  
 Agregue las siguientes líneas a una aplicación de consola para hospedar el servicio e inicie la aplicación.  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a>Paso 4: Configurar el cliente y llamar al servicio  
 Configure el cliente para comunicarse con los servicios WCF; para ello, realice las siguientes entradas en el archivo de configuración de aplicación del proyecto (app.config).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
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
  
 Para llamar al servicio, agregue el código al cliente para hacer lo siguiente:  
  
1. Cree un canal para el servicio `ISessionBoundFactory`.  
  
2. Use el canal para invocar el servicio `ISessionBoundFactory` y obtener un objeto <xref:System.ServiceModel.EndpointAddress10>.  
  
3. Use <xref:System.ServiceModel.EndpointAddress10> para crear un canal para obtener un objeto con sesión.  
  
4. Llame a los métodos `SetCurrentValue` y `GetCurrentValue` para mostrar que sigue siendo la misma instancia de objeto que se usa en varias llamadas.  
  
```csharp  
ChannelFactory<ISessionBoundFactory> factory =  
        new ChannelFactory<ISessionBoundFactory>("factory");  
  
ISessionBoundFactory sessionBoundFactory = factory.CreateChannel();  
  
EndpointAddress10 address = sessionBoundFactory.GetInstanceAddress();  
  
ChannelFactory<ISessionBoundObject> sessionBoundObjectFactory =  
    new ChannelFactory<ISessionBoundObject>(  
        new NetTcpBinding(),  
        address.ToEndpointAddress());  
  
ISessionBoundObject sessionBoundObject =  
        sessionBoundObjectFactory.CreateChannel();  
  
sessionBoundObject.SetCurrentValue("Hello");  
if (sessionBoundObject.GetCurrentValue() == "Hello")  
{  
    Console.WriteLine("Session-full instance management works as expected");  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Programación básica de WCF](../wcf/basic-wcf-programming.md)
- [Diseño e implementación de servicios](../wcf/designing-and-implementing-services.md)
- [Creación de clientes](../wcf/building-clients.md)
- [Servicios dúplex](../wcf/feature-details/duplex-services.md)
