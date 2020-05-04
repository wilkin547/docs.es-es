---
title: Procedimiento Migrar código administrado DCOM a WCF
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: 2576e88c25ae381e90ec7d613efb648048145b3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181390"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a><span data-ttu-id="712a9-102">Procedimiento Migrar código administrado DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="712a9-102">How to: Migrate Managed-Code DCOM to WCF</span></span>
<span data-ttu-id="712a9-103">Windows Communication Foundation (WCF) es la opción recomendada y segura para reemplazar al modelo de objetos de componentes distribuidos (DCOM) en las llamadas de código administrado entre servidores y clientes en un entorno distribuido.</span><span class="sxs-lookup"><span data-stu-id="712a9-103">Windows Communication Foundation (WCF) is the recommended and secure choice over Distributed Component Object Model (DCOM) for managed code calls between servers and clients in a distributed environment.</span></span> <span data-ttu-id="712a9-104">En este artículo se muestra cómo migrar el código de DCOM a WCF en los escenarios siguientes.</span><span class="sxs-lookup"><span data-stu-id="712a9-104">This article shows how you to migrate code from DCOM to WCF for the following scenarios.</span></span>  
  
- <span data-ttu-id="712a9-105">El servicio remoto devuelve un objeto por valor al cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-105">The remote service returns an object by-value to the client</span></span>  
  
- <span data-ttu-id="712a9-106">El cliente envía un objeto por valor al servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="712a9-106">The client sends an object by-value to the remote service</span></span>  
  
- <span data-ttu-id="712a9-107">El servicio remoto devuelve un objeto por referencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-107">The remote service returns an object by-reference to the client</span></span>  
  
 <span data-ttu-id="712a9-108">Por motivos de seguridad, en WCF no se permite enviar objetos por referencia desde el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="712a9-108">For security reasons, sending an object by-reference from the client to the service is not allowed in WCF.</span></span> <span data-ttu-id="712a9-109">En WCF puede conseguir un escenario que necesite una conversación entre el cliente y el servidor con un servicio dúplex.</span><span class="sxs-lookup"><span data-stu-id="712a9-109">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span>  <span data-ttu-id="712a9-110">Para más información sobre los servicios dúplex, vea [Duplex Services](../wcf/feature-details/duplex-services.md) (Servicios dúplex).</span><span class="sxs-lookup"><span data-stu-id="712a9-110">For more information about duplex services, see [Duplex Services](../wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="712a9-111">Para obtener más detalles sobre cómo crear servicios WCF y clientes para esos servicios, vea [Programación basica de WFC](../wcf/basic-wcf-programming.md), [Diseño e implementación de servicios](../wcf/designing-and-implementing-services.md) y [Creación de clientes](../wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="712a9-111">For more details about creating WCF services and clients for those services, see [Basic WCF Programming](../wcf/basic-wcf-programming.md), [Designing and Implementing Services](../wcf/designing-and-implementing-services.md), and [Building Clients](../wcf/building-clients.md).</span></span>  
  
## <a name="dcom-example-code"></a><span data-ttu-id="712a9-112">Código de ejemplo DCOM</span><span class="sxs-lookup"><span data-stu-id="712a9-112">DCOM example code</span></span>  
 <span data-ttu-id="712a9-113">Para estos escenarios, las interfaces DCOM que se muestran con WCF tienen la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="712a9-113">For these scenarios, the DCOM interfaces that are illustrated using WCF have the following structure:</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-value"></a><span data-ttu-id="712a9-114">El servicio devuelve un objeto por valor</span><span class="sxs-lookup"><span data-stu-id="712a9-114">The service returns an object by-value</span></span>  
 <span data-ttu-id="712a9-115">En este escenario, se realiza una llamada a un servicio y el método devuelve un objeto que se pasa por valor desde el servidor al cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-115">For this scenario, you make a call to a service and it method returns an object, which is passed by-value from the server to the client.</span></span> <span data-ttu-id="712a9-116">Este escenario representa la siguiente llamada COM:</span><span class="sxs-lookup"><span data-stu-id="712a9-116">This scenario represents the following COM call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 <span data-ttu-id="712a9-117">En este escenario, el cliente recibe una copia deserializada de un objeto desde el servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="712a9-117">In this scenario, the client receives a deserialized copy of an object from the remote service.</span></span> <span data-ttu-id="712a9-118">El cliente puede interactuar con esta copia local sin tener que volver a llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="712a9-118">The client can interact with this local copy without calling back to the service.</span></span>  <span data-ttu-id="712a9-119">En otras palabras, se garantiza al cliente que el servicio no participará en modo alguno cuando se llame a métodos en la copia local.</span><span class="sxs-lookup"><span data-stu-id="712a9-119">In other words, the client is guaranteed the service will not be involved in any way when methods on the local copy are called.</span></span> <span data-ttu-id="712a9-120">WCF siempre devuelve objetos desde el servicio por valor, por lo que los pasos siguientes describen la creación de un servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="712a9-120">WCF always returns objects from the service by value, so the following steps describe creating a regular WCF service.</span></span>  
  
### <a name="step-1-define-the-wcf-service-interface"></a><span data-ttu-id="712a9-121">Paso 1: Definir la interfaz de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="712a9-121">Step 1: Define the WCF service interface</span></span>  
 <span data-ttu-id="712a9-122">Defina una interfaz pública para el servicio WCF y márquela con el atributo [<xref:System.ServiceModel.ServiceContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="712a9-122">Define a public interface for the WCF service and mark it with the [<xref:System.ServiceModel.ServiceContractAttribute>] attribute.</span></span>  <span data-ttu-id="712a9-123">Marque los métodos que desea exponer a los clientes con el atributo [<xref:System.ServiceModel.OperationContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="712a9-123">Mark the methods you want to expose to clients with the [<xref:System.ServiceModel.OperationContractAttribute>] attribute.</span></span> <span data-ttu-id="712a9-124">En el ejemplo siguiente se muestra cómo usar estos atributos para identificar la interfaz del servidor y los métodos de interfaz a los que puede llamar un cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-124">The following example shows using these attributes to identify the server-side interface and interface methods a client can call.</span></span> <span data-ttu-id="712a9-125">El método usado para este escenario se muestra en negrita.</span><span class="sxs-lookup"><span data-stu-id="712a9-125">The method used for this scenario is shown in bold.</span></span>  
  
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
  
### <a name="step-2-define-the-data-contract"></a><span data-ttu-id="712a9-126">Paso 2: Definir el contrato de datos</span><span class="sxs-lookup"><span data-stu-id="712a9-126">Step 2: Define the data contract</span></span>  
 <span data-ttu-id="712a9-127">A continuación debe crear un contrato de datos para el servicio, en el que se describirá cómo se intercambian los datos entre el servicio y sus clientes.</span><span class="sxs-lookup"><span data-stu-id="712a9-127">Next you should create a data contract for the service, which will describe how the data will be exchanged between the service and its clients.</span></span>  <span data-ttu-id="712a9-128">Las clases descritas en el contrato de datos deben marcarse con el atributo [<xref:System.Runtime.Serialization.DataContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="712a9-128">Classes described in the data contract should be marked with the [<xref:System.Runtime.Serialization.DataContractAttribute>] attribute.</span></span> <span data-ttu-id="712a9-129">Las propiedades o los campos individuales que quiera que sean visibles para el cliente y el servidor deben marcarse con el atributo [<xref:System.Runtime.Serialization.DataMemberAttribute>].</span><span class="sxs-lookup"><span data-stu-id="712a9-129">The individual properties or fields you want visible to both client and server should be marked with the [<xref:System.Runtime.Serialization.DataMemberAttribute>] attribute.</span></span> <span data-ttu-id="712a9-130">Si quiere que los tipos derivados de una clase estén permitidos en el contrato de datos, debe identificarlos con el atributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>].</span><span class="sxs-lookup"><span data-stu-id="712a9-130">If you want types derived from a class in the data contract to be allowed, you must identify them with the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute.</span></span> <span data-ttu-id="712a9-131">WCF solo serializará o deserializará tipos en la interfaz de servicio y tipos identificados como tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="712a9-131">WCF will only serialize or deserialize types in the service interface and types identified as known types.</span></span> <span data-ttu-id="712a9-132">Si intenta usar un tipo que no sea un tipo conocido, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="712a9-132">If you attempt to use a type that is not a known type, an exception will occur.</span></span>  
  
 <span data-ttu-id="712a9-133">Para más información sobre los contratos de datos, vea [Data Contracts](../wcf/samples/data-contracts.md) (Contratos de datos).</span><span class="sxs-lookup"><span data-stu-id="712a9-133">For more information about data contracts, see [Data Contracts](../wcf/samples/data-contracts.md).</span></span>  
  
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
  
### <a name="step-3-implement-the-wcf-service"></a><span data-ttu-id="712a9-134">Paso 3: Implementar el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="712a9-134">Step 3: Implement the WCF service</span></span>  
 <span data-ttu-id="712a9-135">A continuación, debe implementar la clase de servicio WCF que implementa la interfaz que definió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="712a9-135">Next, you should implement the WCF service class that implements the interface you defined in the previous step.</span></span>  
  
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
  
### <a name="step-4-configure-the-service-and-the-client"></a><span data-ttu-id="712a9-136">Paso 4: Configurar el servicio y el cliente</span><span class="sxs-lookup"><span data-stu-id="712a9-136">Step 4: Configure the service and the client</span></span>  
 <span data-ttu-id="712a9-137">Para ejecutar un servicio WCF, deberá declarar un punto de conexión que exponga esa interfaz de servicio en una dirección URL específica mediante un enlace WCF específico.</span><span class="sxs-lookup"><span data-stu-id="712a9-137">To run a WCF service, you need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="712a9-138">Un enlace especifica los detalles de transporte, codificación y protocolo para que los clientes y el servidor puedan comunicarse.</span><span class="sxs-lookup"><span data-stu-id="712a9-138">A binding specifies the transport, encoding and protocol details for the clients and server to communicate.</span></span> <span data-ttu-id="712a9-139">Normalmente, los enlaces se agregan al archivo de configuración del proyecto de servicio (web.config).</span><span class="sxs-lookup"><span data-stu-id="712a9-139">You typically add bindings to the service project’s configuration file (web.config).</span></span> <span data-ttu-id="712a9-140">A continuación se muestra una entrada de enlace para el servicio de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="712a9-140">The following shows a binding entry for the example service:</span></span>  
  
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
  
 <span data-ttu-id="712a9-141">Después, deberá configurar el cliente para que coincida con la información de enlace especificada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="712a9-141">Next, you need to configure the client to match the binding information specified by the service.</span></span> <span data-ttu-id="712a9-142">Para ello, agregue lo siguiente al archivo de configuración (app.config) de la aplicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-142">To do so, add the following to the client’s application configuration (app.config) file.</span></span>  
  
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
  
### <a name="step-5-run-the-service"></a><span data-ttu-id="712a9-143">Paso 5: Ejecutar el servicio</span><span class="sxs-lookup"><span data-stu-id="712a9-143">Step 5: Run the service</span></span>  
 <span data-ttu-id="712a9-144">Por último, puede probarlo internamente en una aplicación de consola; para ello, agregue las líneas siguientes a la aplicación de servicio e inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="712a9-144">Finally, you can self-host it in a console application by adding the following lines to the service app, and starting the app.</span></span> <span data-ttu-id="712a9-145">Para más información sobre otras formas de hospedar una aplicación de servicio WCF, vea [Hosting Services](../wcf/hosting-services.md) (Servicios de hospedaje).</span><span class="sxs-lookup"><span data-stu-id="712a9-145">For more information about other ways to host a WCF service application, [Hosting Services](../wcf/hosting-services.md).</span></span>  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a><span data-ttu-id="712a9-146">Paso 6: Llamar al servicio desde el cliente</span><span class="sxs-lookup"><span data-stu-id="712a9-146">Step 6: Call the service from the client</span></span>  
 <span data-ttu-id="712a9-147">Para llamar al servicio desde el cliente, deberá crear un generador de canales para el servicio y solicitar un canal, lo que le permitirá llamar directamente al método `GetCustomer` desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-147">To call the service from the client, you need to create a channel factory for the service, and request a channel, which will enable you to directly call the `GetCustomer` method directly from the client.</span></span> <span data-ttu-id="712a9-148">El canal implementa la interfaz del servicio y controla automáticamente la lógica de solicitud/respuesta subyacente.</span><span class="sxs-lookup"><span data-stu-id="712a9-148">The channel implements the service’s interface and handles the underlying request/reply logic for you.</span></span>  <span data-ttu-id="712a9-149">El valor devuelto de esta llamada de método es la copia deserializada de la respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="712a9-149">The return value from that method call is the deserialized copy of the service response.</span></span>  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a><span data-ttu-id="712a9-150">El cliente envía un objeto por valor al servidor</span><span class="sxs-lookup"><span data-stu-id="712a9-150">The client sends a by-value object to the server</span></span>  
 <span data-ttu-id="712a9-151">En este escenario, el cliente envía un objeto en el servidor por valor.</span><span class="sxs-lookup"><span data-stu-id="712a9-151">In this scenario, the client sends an object to the server, by-value.</span></span> <span data-ttu-id="712a9-152">Esto significa que el servidor recibirá una copia del objeto deserializada.</span><span class="sxs-lookup"><span data-stu-id="712a9-152">This means that the server will receive a deserialized copy of the object.</span></span>  <span data-ttu-id="712a9-153">El servidor puede llamar a métodos en esa copia con la garantía de que no habrá ninguna devolución de llamada en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-153">The server can call methods on that copy and be guaranteed there is no callback into client code.</span></span> <span data-ttu-id="712a9-154">Como se mencionó anteriormente, los intercambios normales de datos de WCF son por valor.</span><span class="sxs-lookup"><span data-stu-id="712a9-154">As mentioned previously, normal WCF exchanges of data are by-value.</span></span>  <span data-ttu-id="712a9-155">Esto garantiza que una llamada a métodos en uno de estos objetos se ejecuta únicamente de forma local y no invoca código en el cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-155">This guarantees that calling methods on one of these objects executes locally only – it will not invoke code on the client.</span></span>  
  
 <span data-ttu-id="712a9-156">Este escenario representa la siguiente llamada de método COM:</span><span class="sxs-lookup"><span data-stu-id="712a9-156">This scenario represents the following COM method call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 <span data-ttu-id="712a9-157">En el escenario se usa la misma interfaz de servicio y el mismo contrato de datos que en el primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="712a9-157">This scenario uses the same service interface and data contract as shown in the first example.</span></span> <span data-ttu-id="712a9-158">Además, el cliente y el servicio se configurarán de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="712a9-158">In addition, the client and service will be configured in the same way.</span></span> <span data-ttu-id="712a9-159">En este ejemplo, se crea un canal para enviar el objeto y que se ejecute de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="712a9-159">In this example, a channel is created to send the object and run the same way.</span></span> <span data-ttu-id="712a9-160">Sin embargo, en este ejemplo, se creará un cliente que llame al servicio pasando un objeto por valor.</span><span class="sxs-lookup"><span data-stu-id="712a9-160">However, for this example, you will create a client that calls the service, passing an object by-value.</span></span> <span data-ttu-id="712a9-161">El método de servicio que llamará el cliente en el contrato de servicio se muestra en negrita:</span><span class="sxs-lookup"><span data-stu-id="712a9-161">The service method the client will call in the service contract is shown in bold:</span></span>  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a><span data-ttu-id="712a9-162">Agregar código al cliente que envíe un objeto por valor</span><span class="sxs-lookup"><span data-stu-id="712a9-162">Add code to the client that sends a by-value object</span></span>  
 <span data-ttu-id="712a9-163">El siguiente código muestra cómo el cliente crea un nuevo objeto de cliente por valor, crea un canal para comunicarse con el servicio `ICustomerManager` y le envía el objeto de cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-163">The following code shows how the client creates a new by-value customer object, creates a channel to communicate with the `ICustomerManager` service, and sends the customer object to it.</span></span>  
  
 <span data-ttu-id="712a9-164">El objeto de cliente se serializa y se envía al servicio, donde se deserializa en una nueva copia del objeto.</span><span class="sxs-lookup"><span data-stu-id="712a9-164">The customer object will be serialized, and sent to the service, where it is deserialized by the service into a new copy of that object.</span></span>  <span data-ttu-id="712a9-165">Cualquier método al que llame el servicio en este objeto solo se ejecutará localmente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="712a9-165">Any methods the service calls on this object will execute only locally on the server.</span></span> <span data-ttu-id="712a9-166">Es importante que tenga en cuenta que este código ejemplifique el envío de un tipo derivado (`PremiumCustomer`).</span><span class="sxs-lookup"><span data-stu-id="712a9-166">It’s important to note that this code illustrates sending a derived type (`PremiumCustomer`).</span></span>  <span data-ttu-id="712a9-167">El contrato de servicio espera un objeto `Customer`, pero los datos del servicio de contrato usan el atributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>] para indicar que `PremiumCustomer` también está permitido.</span><span class="sxs-lookup"><span data-stu-id="712a9-167">The service contract expects a `Customer` object, but the service data contract uses the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute to indicate that `PremiumCustomer` is also allowed.</span></span>  <span data-ttu-id="712a9-168">WCF no podrá serializar ni deserializar cualquier otro tipo a través de esta interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="712a9-168">WCF will fail attempts to serialize or deserialize any other type via this service interface.</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-reference"></a><span data-ttu-id="712a9-169">El servicio devuelve un objeto por referencia</span><span class="sxs-lookup"><span data-stu-id="712a9-169">The service returns an object by reference</span></span>  
 <span data-ttu-id="712a9-170">En este escenario, la aplicación cliente realiza una llamada al servicio remoto y el método devuelve un objeto que se pasa por referencia desde el servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="712a9-170">For this scenario, the client app makes a call to the remote service and the method returns an object, which is passed by reference from the service to the client.</span></span>  
  
 <span data-ttu-id="712a9-171">Como se mencionó anteriormente, los servicios WCF siempre devuelven objetos por valor.</span><span class="sxs-lookup"><span data-stu-id="712a9-171">As mentioned previously, WCF services always return object by value.</span></span>  <span data-ttu-id="712a9-172">Sin embargo, se puede conseguir un resultado similar usando la clase <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="712a9-172">However, you can achieve a similar result by using the <xref:System.ServiceModel.EndpointAddress10> class.</span></span>  <span data-ttu-id="712a9-173"><xref:System.ServiceModel.EndpointAddress10> es un objeto serializable por valor que el cliente puede usar para obtener un objeto por referencia con sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="712a9-173">The <xref:System.ServiceModel.EndpointAddress10> is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span>  
  
 <span data-ttu-id="712a9-174">El comportamiento del objeto por referencia de WCF que se muestra en este escenario es diferente al de DCOM.</span><span class="sxs-lookup"><span data-stu-id="712a9-174">The behavior of the by-reference object in WCF shown in this scenario is different than DCOM.</span></span>  <span data-ttu-id="712a9-175">En DCOM, el servidor puede devolver directamente un objeto por referencia al cliente y el cliente puede llamar a métodos del objeto, que se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="712a9-175">In DCOM, the server can return a by-reference object to the client directly, and the client can call that object’s methods, which execute on the server.</span></span>  <span data-ttu-id="712a9-176">En WCF, sin embargo, el objeto devuelto es siempre por valor.</span><span class="sxs-lookup"><span data-stu-id="712a9-176">In WCF, however, the object returned is always by-value.</span></span>  <span data-ttu-id="712a9-177">El cliente debe tomar ese objeto por valor, representado por <xref:System.ServiceModel.EndpointAddress10>, y usarlo para crear su propio objeto por referencia con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-177">The client must take that by-value object, represented by <xref:System.ServiceModel.EndpointAddress10> and use it to create its own sessionful by-reference object.</span></span>  <span data-ttu-id="712a9-178">Las llamadas de método de cliente en el objeto con sesión se ejecutan en el servidor. En otras palabras, este objeto por referencia en WCF es un servicio WCF normal que se configura para ser con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-178">The client method calls on the sessionful object execute on the server.In other words, this by-reference object in WCF is a normal WCF service that is configured to be sessionful.</span></span>  
  
 <span data-ttu-id="712a9-179">En WCF, una sesión es una manera de asociar varios mensajes enviados entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="712a9-179">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span>  <span data-ttu-id="712a9-180">Esto significa que cuando un cliente obtiene una conexión a este servicio, se establecerá una sesión entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="712a9-180">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span>  <span data-ttu-id="712a9-181">El cliente usará una única instancia del objeto del lado servidor para todas las interacciones dentro de esta sesión única.</span><span class="sxs-lookup"><span data-stu-id="712a9-181">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span> <span data-ttu-id="712a9-182">Los contratos de WCF con sesión son similares a los patrones de solicitud/respuesta de red orientados a conexiones.</span><span class="sxs-lookup"><span data-stu-id="712a9-182">Sessionful WCF contracts are similar to connection-oriented network request/response patterns.</span></span>  
  
 <span data-ttu-id="712a9-183">Este escenario se representa mediante el siguiente método DCOM.</span><span class="sxs-lookup"><span data-stu-id="712a9-183">This scenario is represented by the following DCOM method.</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a><span data-ttu-id="712a9-184">Paso 1: Definir la interfaz de servicio de WCF con sesión y la implementación</span><span class="sxs-lookup"><span data-stu-id="712a9-184">Step 1: Define the Sessionful WCF service interface and implementation</span></span>  
 <span data-ttu-id="712a9-185">En primer lugar, defina una interfaz de servicio WCF que contenga el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-185">First, define a WCF service interface that contains the sessionful object.</span></span>  
  
 <span data-ttu-id="712a9-186">En este código, el objeto con sesión se marca con el atributo `ServiceContract`, que lo identifica como una interfaz de servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="712a9-186">In this code, the sessionful object is marked with the `ServiceContract` attribute, which identifies it as a regular WCF service interface.</span></span>  <span data-ttu-id="712a9-187">Además, se establece la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> para indicar que será un servicio con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-187">In addition, the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> property is set to indicate it will be a sessionful service.</span></span>  
  
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
  
 <span data-ttu-id="712a9-188">En el siguiente código se muestra la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="712a9-188">The following code shows the service implementation.</span></span>  
  
 <span data-ttu-id="712a9-189">El servicio se marca con el atributo [ServiceBehavior] y su propiedad InstanceContextMode se establece en InstanceContextMode.PerSessions para indicar que debe crearse una instancia única de este tipo para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-189">The service is marked with the [ServiceBehavior] attribute, and its InstanceContextMode property set to InstanceContextMode.PerSessions to indicate that a unique instance of this type should be created for each session.</span></span>  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a><span data-ttu-id="712a9-190">Paso 2: Definir el servicio del generador WCF para el objeto con sesión</span><span class="sxs-lookup"><span data-stu-id="712a9-190">Step 2: Define the WCF factory service for the sessionful object</span></span>  
 <span data-ttu-id="712a9-191">El servicio que crea el objeto con sesión debe definirse e implementarse.</span><span class="sxs-lookup"><span data-stu-id="712a9-191">The service that creates the sessionful object must be defined and implemented.</span></span> <span data-ttu-id="712a9-192">El código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="712a9-192">The following code shows how to do this.</span></span> <span data-ttu-id="712a9-193">Este código crea otro servicio WCF que devuelve un objeto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="712a9-193">This code creates another WCF service that returns an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  <span data-ttu-id="712a9-194">Se trata de una forma serializable de un punto de conexión que puede usarse para crear el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-194">This is a serializable form of an endpoint the can use to create the session-full object.</span></span>  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 <span data-ttu-id="712a9-195">En el siguiente ejemplo se muestra la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="712a9-195">The following is the implementation of this service.</span></span> <span data-ttu-id="712a9-196">Esta implementación mantiene un generador de canales de singleton para crear objetos con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-196">This implementation maintains a singleton channel factory to create sessionful objects.</span></span>  <span data-ttu-id="712a9-197">Cuando se llama a `GetInstanceAddress`, este crea un canal y crea un objeto <xref:System.ServiceModel.EndpointAddress10> que apunta a la dirección remota asociada a este canal.</span><span class="sxs-lookup"><span data-stu-id="712a9-197">When `GetInstanceAddress` is called, it creates a channel and creates an <xref:System.ServiceModel.EndpointAddress10> object that points to the remote address associated with this channel.</span></span>   <span data-ttu-id="712a9-198"><xref:System.ServiceModel.EndpointAddress10> es un tipo de datos que se puede devolver al cliente por valor.</span><span class="sxs-lookup"><span data-stu-id="712a9-198"><xref:System.ServiceModel.EndpointAddress10> is a data type that can be returned to the client by-value.</span></span>
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a><span data-ttu-id="712a9-199">Paso 3: Configurar e iniciar los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="712a9-199">Step 3: Configure and start the WCF services</span></span>  
 <span data-ttu-id="712a9-200">Para hospedar estos servicios, deberá agregar lo siguiente al archivo de configuración del servidor (web.config).</span><span class="sxs-lookup"><span data-stu-id="712a9-200">To host these services, you will need to make the following additions to the server’s configuration file (web.config).</span></span>  
  
1. <span data-ttu-id="712a9-201">Agregue una sección `<client>` que describa el extremo para el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-201">Add a `<client>` section that describes the endpoint for the sessionful object.</span></span>  <span data-ttu-id="712a9-202">En este escenario, el servidor también actúa como un cliente y debe configurarse para habilitar esta opción.</span><span class="sxs-lookup"><span data-stu-id="712a9-202">In this scenario, the server also acts as a client and must be configured to enable this.</span></span>  
  
2. <span data-ttu-id="712a9-203">En la sección `<services>`, declare los extremos de servicio para el generador y el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-203">In the `<services>` section, declare service endpoints for the factory and sessionful object.</span></span>  <span data-ttu-id="712a9-204">Esto permite al cliente comunicarse con los puntos de conexión de servicio, adquirir el <xref:System.ServiceModel.EndpointAddress10> y crear el canal con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-204">This enables the client to communicate with the service endpoints, acquire the <xref:System.ServiceModel.EndpointAddress10> and create the sessionful channel.</span></span>  
  
 <span data-ttu-id="712a9-205">En el siguiente ejemplo se muestra un archivo de configuración con estas opciones:</span><span class="sxs-lookup"><span data-stu-id="712a9-205">The following is an example configuration file with these settings:</span></span>  
  
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
  
 <span data-ttu-id="712a9-206">Agregue las siguientes líneas a una aplicación de consola para hospedar el servicio e inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="712a9-206">Add the following lines to a console application, to self-host the service, and start the app.</span></span>  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a><span data-ttu-id="712a9-207">Paso 4: Configurar el cliente y llamar al servicio</span><span class="sxs-lookup"><span data-stu-id="712a9-207">Step 4: Configure the client and call the service</span></span>  
 <span data-ttu-id="712a9-208">Configure el cliente para comunicarse con los servicios WCF; para ello, realice las siguientes entradas en el archivo de configuración de aplicación del proyecto (app.config).</span><span class="sxs-lookup"><span data-stu-id="712a9-208">Configure the client to communicate with the WCF services by making the following entries in the project’s application configuration file (app.config).</span></span>  
  
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
  
 <span data-ttu-id="712a9-209">Para llamar al servicio, agregue el código al cliente para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="712a9-209">To call the service, add the code to the client to do the following:</span></span>  
  
1. <span data-ttu-id="712a9-210">Cree un canal para el servicio `ISessionBoundFactory`.</span><span class="sxs-lookup"><span data-stu-id="712a9-210">Create a channel to the `ISessionBoundFactory` service.</span></span>  
  
2. <span data-ttu-id="712a9-211">Use el canal para invocar el servicio `ISessionBoundFactory` y obtener un objeto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="712a9-211">Use the channel to invoke the `ISessionBoundFactory` service an obtain an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  
  
3. <span data-ttu-id="712a9-212">Use <xref:System.ServiceModel.EndpointAddress10> para crear un canal para obtener un objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="712a9-212">Use the <xref:System.ServiceModel.EndpointAddress10> to create a channel to obtain a sessionful object.</span></span>  
  
4. <span data-ttu-id="712a9-213">Llame a los métodos `SetCurrentValue` y `GetCurrentValue` para mostrar que sigue siendo la misma instancia de objeto que se usa en varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="712a9-213">Call the `SetCurrentValue` and `GetCurrentValue` methods to demonstrate it remains the same object instance is used across multiple calls.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="712a9-214">Vea también</span><span class="sxs-lookup"><span data-stu-id="712a9-214">See also</span></span>

- [<span data-ttu-id="712a9-215">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="712a9-215">Basic WCF Programming</span></span>](../wcf/basic-wcf-programming.md)
- [<span data-ttu-id="712a9-216">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="712a9-216">Designing and Implementing Services</span></span>](../wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="712a9-217">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="712a9-217">Building Clients</span></span>](../wcf/building-clients.md)
- [<span data-ttu-id="712a9-218">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="712a9-218">Duplex Services</span></span>](../wcf/feature-details/duplex-services.md)
