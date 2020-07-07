---
title: Procedimiento Migrar código administrado DCOM a WCF
description: Migre las llamadas de código administrado del modelo de objetos componentes distribuido (DCOM) entre servidores y clientes a Windows Communication Foundation (WCF).
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: cc6ac1dd01e17bb184d1f1faca372134d6130d33
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619096"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a><span data-ttu-id="240c8-103">Procedimiento Migrar código administrado DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="240c8-103">How to: Migrate Managed-Code DCOM to WCF</span></span>
<span data-ttu-id="240c8-104">Windows Communication Foundation (WCF) es la opción recomendada y segura para reemplazar al modelo de objetos de componentes distribuidos (DCOM) en las llamadas de código administrado entre servidores y clientes en un entorno distribuido.</span><span class="sxs-lookup"><span data-stu-id="240c8-104">Windows Communication Foundation (WCF) is the recommended and secure choice over Distributed Component Object Model (DCOM) for managed code calls between servers and clients in a distributed environment.</span></span> <span data-ttu-id="240c8-105">En este artículo se muestra cómo migrar el código de DCOM a WCF en los escenarios siguientes.</span><span class="sxs-lookup"><span data-stu-id="240c8-105">This article shows how you to migrate code from DCOM to WCF for the following scenarios.</span></span>  
  
- <span data-ttu-id="240c8-106">El servicio remoto devuelve un objeto por valor al cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-106">The remote service returns an object by-value to the client</span></span>  
  
- <span data-ttu-id="240c8-107">El cliente envía un objeto por valor al servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="240c8-107">The client sends an object by-value to the remote service</span></span>  
  
- <span data-ttu-id="240c8-108">El servicio remoto devuelve un objeto por referencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-108">The remote service returns an object by-reference to the client</span></span>  
  
 <span data-ttu-id="240c8-109">Por motivos de seguridad, en WCF no se permite enviar objetos por referencia desde el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="240c8-109">For security reasons, sending an object by-reference from the client to the service is not allowed in WCF.</span></span> <span data-ttu-id="240c8-110">En WCF puede conseguir un escenario que necesite una conversación entre el cliente y el servidor con un servicio dúplex.</span><span class="sxs-lookup"><span data-stu-id="240c8-110">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span>  <span data-ttu-id="240c8-111">Para más información sobre los servicios dúplex, vea [Duplex Services](../wcf/feature-details/duplex-services.md) (Servicios dúplex).</span><span class="sxs-lookup"><span data-stu-id="240c8-111">For more information about duplex services, see [Duplex Services](../wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="240c8-112">Para obtener más detalles sobre cómo crear servicios WCF y clientes para esos servicios, vea [Programación basica de WFC](../wcf/basic-wcf-programming.md), [Diseño e implementación de servicios](../wcf/designing-and-implementing-services.md) y [Creación de clientes](../wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="240c8-112">For more details about creating WCF services and clients for those services, see [Basic WCF Programming](../wcf/basic-wcf-programming.md), [Designing and Implementing Services](../wcf/designing-and-implementing-services.md), and [Building Clients](../wcf/building-clients.md).</span></span>  
  
## <a name="dcom-example-code"></a><span data-ttu-id="240c8-113">Código de ejemplo DCOM</span><span class="sxs-lookup"><span data-stu-id="240c8-113">DCOM example code</span></span>  
 <span data-ttu-id="240c8-114">Para estos escenarios, las interfaces DCOM que se muestran con WCF tienen la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="240c8-114">For these scenarios, the DCOM interfaces that are illustrated using WCF have the following structure:</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-value"></a><span data-ttu-id="240c8-115">El servicio devuelve un objeto por valor</span><span class="sxs-lookup"><span data-stu-id="240c8-115">The service returns an object by-value</span></span>  
 <span data-ttu-id="240c8-116">En este escenario, se realiza una llamada a un servicio y el método devuelve un objeto que se pasa por valor desde el servidor al cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-116">For this scenario, you make a call to a service and it method returns an object, which is passed by-value from the server to the client.</span></span> <span data-ttu-id="240c8-117">Este escenario representa la siguiente llamada COM:</span><span class="sxs-lookup"><span data-stu-id="240c8-117">This scenario represents the following COM call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 <span data-ttu-id="240c8-118">En este escenario, el cliente recibe una copia deserializada de un objeto desde el servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="240c8-118">In this scenario, the client receives a deserialized copy of an object from the remote service.</span></span> <span data-ttu-id="240c8-119">El cliente puede interactuar con esta copia local sin tener que volver a llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="240c8-119">The client can interact with this local copy without calling back to the service.</span></span>  <span data-ttu-id="240c8-120">En otras palabras, se garantiza al cliente que el servicio no participará en modo alguno cuando se llame a métodos en la copia local.</span><span class="sxs-lookup"><span data-stu-id="240c8-120">In other words, the client is guaranteed the service will not be involved in any way when methods on the local copy are called.</span></span> <span data-ttu-id="240c8-121">WCF siempre devuelve objetos desde el servicio por valor, por lo que los pasos siguientes describen la creación de un servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="240c8-121">WCF always returns objects from the service by value, so the following steps describe creating a regular WCF service.</span></span>  
  
### <a name="step-1-define-the-wcf-service-interface"></a><span data-ttu-id="240c8-122">Paso 1: Definir la interfaz de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="240c8-122">Step 1: Define the WCF service interface</span></span>  
 <span data-ttu-id="240c8-123">Defina una interfaz pública para el servicio WCF y márquela con el atributo [<xref:System.ServiceModel.ServiceContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="240c8-123">Define a public interface for the WCF service and mark it with the [<xref:System.ServiceModel.ServiceContractAttribute>] attribute.</span></span>  <span data-ttu-id="240c8-124">Marque los métodos que desea exponer a los clientes con el atributo [<xref:System.ServiceModel.OperationContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="240c8-124">Mark the methods you want to expose to clients with the [<xref:System.ServiceModel.OperationContractAttribute>] attribute.</span></span> <span data-ttu-id="240c8-125">En el ejemplo siguiente se muestra cómo usar estos atributos para identificar la interfaz del servidor y los métodos de interfaz a los que puede llamar un cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-125">The following example shows using these attributes to identify the server-side interface and interface methods a client can call.</span></span> <span data-ttu-id="240c8-126">El método usado para este escenario se muestra en negrita.</span><span class="sxs-lookup"><span data-stu-id="240c8-126">The method used for this scenario is shown in bold.</span></span>  
  
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
  
### <a name="step-2-define-the-data-contract"></a><span data-ttu-id="240c8-127">Paso 2: Definir el contrato de datos</span><span class="sxs-lookup"><span data-stu-id="240c8-127">Step 2: Define the data contract</span></span>  
 <span data-ttu-id="240c8-128">A continuación debe crear un contrato de datos para el servicio, en el que se describirá cómo se intercambian los datos entre el servicio y sus clientes.</span><span class="sxs-lookup"><span data-stu-id="240c8-128">Next you should create a data contract for the service, which will describe how the data will be exchanged between the service and its clients.</span></span>  <span data-ttu-id="240c8-129">Las clases descritas en el contrato de datos deben marcarse con el atributo [<xref:System.Runtime.Serialization.DataContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="240c8-129">Classes described in the data contract should be marked with the [<xref:System.Runtime.Serialization.DataContractAttribute>] attribute.</span></span> <span data-ttu-id="240c8-130">Las propiedades o los campos individuales que quiera que sean visibles para el cliente y el servidor deben marcarse con el atributo [<xref:System.Runtime.Serialization.DataMemberAttribute>].</span><span class="sxs-lookup"><span data-stu-id="240c8-130">The individual properties or fields you want visible to both client and server should be marked with the [<xref:System.Runtime.Serialization.DataMemberAttribute>] attribute.</span></span> <span data-ttu-id="240c8-131">Si quiere que los tipos derivados de una clase estén permitidos en el contrato de datos, debe identificarlos con el atributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>].</span><span class="sxs-lookup"><span data-stu-id="240c8-131">If you want types derived from a class in the data contract to be allowed, you must identify them with the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute.</span></span> <span data-ttu-id="240c8-132">WCF solo serializará o deserializará tipos en la interfaz de servicio y tipos identificados como tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="240c8-132">WCF will only serialize or deserialize types in the service interface and types identified as known types.</span></span> <span data-ttu-id="240c8-133">Si intenta usar un tipo que no sea un tipo conocido, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="240c8-133">If you attempt to use a type that is not a known type, an exception will occur.</span></span>  
  
 <span data-ttu-id="240c8-134">Para más información sobre los contratos de datos, vea [Data Contracts](../wcf/samples/data-contracts.md) (Contratos de datos).</span><span class="sxs-lookup"><span data-stu-id="240c8-134">For more information about data contracts, see [Data Contracts](../wcf/samples/data-contracts.md).</span></span>  
  
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
  
### <a name="step-3-implement-the-wcf-service"></a><span data-ttu-id="240c8-135">Paso 3: Implementar el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="240c8-135">Step 3: Implement the WCF service</span></span>  
 <span data-ttu-id="240c8-136">A continuación, debe implementar la clase de servicio WCF que implementa la interfaz que definió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="240c8-136">Next, you should implement the WCF service class that implements the interface you defined in the previous step.</span></span>  
  
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
  
### <a name="step-4-configure-the-service-and-the-client"></a><span data-ttu-id="240c8-137">Paso 4: Configurar el servicio y el cliente</span><span class="sxs-lookup"><span data-stu-id="240c8-137">Step 4: Configure the service and the client</span></span>  
 <span data-ttu-id="240c8-138">Para ejecutar un servicio WCF, deberá declarar un punto de conexión que exponga esa interfaz de servicio en una dirección URL específica mediante un enlace WCF específico.</span><span class="sxs-lookup"><span data-stu-id="240c8-138">To run a WCF service, you need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="240c8-139">Un enlace especifica los detalles de transporte, codificación y protocolo para que los clientes y el servidor puedan comunicarse.</span><span class="sxs-lookup"><span data-stu-id="240c8-139">A binding specifies the transport, encoding and protocol details for the clients and server to communicate.</span></span> <span data-ttu-id="240c8-140">Normalmente, los enlaces se agregan al archivo de configuración del proyecto de servicio (web.config).</span><span class="sxs-lookup"><span data-stu-id="240c8-140">You typically add bindings to the service project’s configuration file (web.config).</span></span> <span data-ttu-id="240c8-141">A continuación se muestra una entrada de enlace para el servicio de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="240c8-141">The following shows a binding entry for the example service:</span></span>  
  
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
  
 <span data-ttu-id="240c8-142">Después, deberá configurar el cliente para que coincida con la información de enlace especificada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="240c8-142">Next, you need to configure the client to match the binding information specified by the service.</span></span> <span data-ttu-id="240c8-143">Para ello, agregue lo siguiente al archivo de configuración (app.config) de la aplicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-143">To do so, add the following to the client’s application configuration (app.config) file.</span></span>  
  
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
  
### <a name="step-5-run-the-service"></a><span data-ttu-id="240c8-144">Paso 5: Ejecutar el servicio</span><span class="sxs-lookup"><span data-stu-id="240c8-144">Step 5: Run the service</span></span>  
 <span data-ttu-id="240c8-145">Por último, puede probarlo internamente en una aplicación de consola; para ello, agregue las líneas siguientes a la aplicación de servicio e inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="240c8-145">Finally, you can self-host it in a console application by adding the following lines to the service app, and starting the app.</span></span> <span data-ttu-id="240c8-146">Para más información sobre otras formas de hospedar una aplicación de servicio WCF, vea [Hosting Services](../wcf/hosting-services.md) (Servicios de hospedaje).</span><span class="sxs-lookup"><span data-stu-id="240c8-146">For more information about other ways to host a WCF service application, [Hosting Services](../wcf/hosting-services.md).</span></span>  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a><span data-ttu-id="240c8-147">Paso 6: Llamar al servicio desde el cliente</span><span class="sxs-lookup"><span data-stu-id="240c8-147">Step 6: Call the service from the client</span></span>  
 <span data-ttu-id="240c8-148">Para llamar al servicio desde el cliente, deberá crear un generador de canales para el servicio y solicitar un canal, lo que le permitirá llamar directamente al método `GetCustomer` desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-148">To call the service from the client, you need to create a channel factory for the service, and request a channel, which will enable you to directly call the `GetCustomer` method directly from the client.</span></span> <span data-ttu-id="240c8-149">El canal implementa la interfaz del servicio y controla automáticamente la lógica de solicitud/respuesta subyacente.</span><span class="sxs-lookup"><span data-stu-id="240c8-149">The channel implements the service’s interface and handles the underlying request/reply logic for you.</span></span>  <span data-ttu-id="240c8-150">El valor devuelto de esta llamada de método es la copia deserializada de la respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="240c8-150">The return value from that method call is the deserialized copy of the service response.</span></span>  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a><span data-ttu-id="240c8-151">El cliente envía un objeto por valor al servidor</span><span class="sxs-lookup"><span data-stu-id="240c8-151">The client sends a by-value object to the server</span></span>  
 <span data-ttu-id="240c8-152">En este escenario, el cliente envía un objeto en el servidor por valor.</span><span class="sxs-lookup"><span data-stu-id="240c8-152">In this scenario, the client sends an object to the server, by-value.</span></span> <span data-ttu-id="240c8-153">Esto significa que el servidor recibirá una copia del objeto deserializada.</span><span class="sxs-lookup"><span data-stu-id="240c8-153">This means that the server will receive a deserialized copy of the object.</span></span>  <span data-ttu-id="240c8-154">El servidor puede llamar a métodos en esa copia con la garantía de que no habrá ninguna devolución de llamada en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-154">The server can call methods on that copy and be guaranteed there is no callback into client code.</span></span> <span data-ttu-id="240c8-155">Como se mencionó anteriormente, los intercambios normales de datos de WCF son por valor.</span><span class="sxs-lookup"><span data-stu-id="240c8-155">As mentioned previously, normal WCF exchanges of data are by-value.</span></span>  <span data-ttu-id="240c8-156">Esto garantiza que una llamada a métodos en uno de estos objetos se ejecuta únicamente de forma local y no invoca código en el cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-156">This guarantees that calling methods on one of these objects executes locally only – it will not invoke code on the client.</span></span>  
  
 <span data-ttu-id="240c8-157">Este escenario representa la siguiente llamada de método COM:</span><span class="sxs-lookup"><span data-stu-id="240c8-157">This scenario represents the following COM method call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 <span data-ttu-id="240c8-158">En el escenario se usa la misma interfaz de servicio y el mismo contrato de datos que en el primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="240c8-158">This scenario uses the same service interface and data contract as shown in the first example.</span></span> <span data-ttu-id="240c8-159">Además, el cliente y el servicio se configurarán de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="240c8-159">In addition, the client and service will be configured in the same way.</span></span> <span data-ttu-id="240c8-160">En este ejemplo, se crea un canal para enviar el objeto y que se ejecute de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="240c8-160">In this example, a channel is created to send the object and run the same way.</span></span> <span data-ttu-id="240c8-161">Sin embargo, en este ejemplo, se creará un cliente que llame al servicio pasando un objeto por valor.</span><span class="sxs-lookup"><span data-stu-id="240c8-161">However, for this example, you will create a client that calls the service, passing an object by-value.</span></span> <span data-ttu-id="240c8-162">El método de servicio que llamará el cliente en el contrato de servicio se muestra en negrita:</span><span class="sxs-lookup"><span data-stu-id="240c8-162">The service method the client will call in the service contract is shown in bold:</span></span>  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a><span data-ttu-id="240c8-163">Agregar código al cliente que envíe un objeto por valor</span><span class="sxs-lookup"><span data-stu-id="240c8-163">Add code to the client that sends a by-value object</span></span>  
 <span data-ttu-id="240c8-164">El siguiente código muestra cómo el cliente crea un nuevo objeto de cliente por valor, crea un canal para comunicarse con el servicio `ICustomerManager` y le envía el objeto de cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-164">The following code shows how the client creates a new by-value customer object, creates a channel to communicate with the `ICustomerManager` service, and sends the customer object to it.</span></span>  
  
 <span data-ttu-id="240c8-165">El objeto de cliente se serializa y se envía al servicio, donde se deserializa en una nueva copia del objeto.</span><span class="sxs-lookup"><span data-stu-id="240c8-165">The customer object will be serialized, and sent to the service, where it is deserialized by the service into a new copy of that object.</span></span>  <span data-ttu-id="240c8-166">Cualquier método al que llame el servicio en este objeto solo se ejecutará localmente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="240c8-166">Any methods the service calls on this object will execute only locally on the server.</span></span> <span data-ttu-id="240c8-167">Es importante que tenga en cuenta que este código ejemplifique el envío de un tipo derivado (`PremiumCustomer`).</span><span class="sxs-lookup"><span data-stu-id="240c8-167">It’s important to note that this code illustrates sending a derived type (`PremiumCustomer`).</span></span>  <span data-ttu-id="240c8-168">El contrato de servicio espera un objeto `Customer`, pero los datos del servicio de contrato usan el atributo [<xref:System.Runtime.Serialization.KnownTypeAttribute>] para indicar que `PremiumCustomer` también está permitido.</span><span class="sxs-lookup"><span data-stu-id="240c8-168">The service contract expects a `Customer` object, but the service data contract uses the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute to indicate that `PremiumCustomer` is also allowed.</span></span>  <span data-ttu-id="240c8-169">WCF no podrá serializar ni deserializar cualquier otro tipo a través de esta interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="240c8-169">WCF will fail attempts to serialize or deserialize any other type via this service interface.</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-reference"></a><span data-ttu-id="240c8-170">El servicio devuelve un objeto por referencia</span><span class="sxs-lookup"><span data-stu-id="240c8-170">The service returns an object by reference</span></span>  
 <span data-ttu-id="240c8-171">En este escenario, la aplicación cliente realiza una llamada al servicio remoto y el método devuelve un objeto que se pasa por referencia desde el servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="240c8-171">For this scenario, the client app makes a call to the remote service and the method returns an object, which is passed by reference from the service to the client.</span></span>  
  
 <span data-ttu-id="240c8-172">Como se mencionó anteriormente, los servicios WCF siempre devuelven objetos por valor.</span><span class="sxs-lookup"><span data-stu-id="240c8-172">As mentioned previously, WCF services always return object by value.</span></span>  <span data-ttu-id="240c8-173">Sin embargo, se puede conseguir un resultado similar usando la clase <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="240c8-173">However, you can achieve a similar result by using the <xref:System.ServiceModel.EndpointAddress10> class.</span></span>  <span data-ttu-id="240c8-174"><xref:System.ServiceModel.EndpointAddress10> es un objeto serializable por valor que el cliente puede usar para obtener un objeto por referencia con sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="240c8-174">The <xref:System.ServiceModel.EndpointAddress10> is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span>  
  
 <span data-ttu-id="240c8-175">El comportamiento del objeto por referencia de WCF que se muestra en este escenario es diferente al de DCOM.</span><span class="sxs-lookup"><span data-stu-id="240c8-175">The behavior of the by-reference object in WCF shown in this scenario is different than DCOM.</span></span>  <span data-ttu-id="240c8-176">En DCOM, el servidor puede devolver directamente un objeto por referencia al cliente y el cliente puede llamar a métodos del objeto, que se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="240c8-176">In DCOM, the server can return a by-reference object to the client directly, and the client can call that object’s methods, which execute on the server.</span></span>  <span data-ttu-id="240c8-177">En WCF, sin embargo, el objeto devuelto es siempre por valor.</span><span class="sxs-lookup"><span data-stu-id="240c8-177">In WCF, however, the object returned is always by-value.</span></span>  <span data-ttu-id="240c8-178">El cliente debe tomar ese objeto por valor, representado por <xref:System.ServiceModel.EndpointAddress10>, y usarlo para crear su propio objeto por referencia con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-178">The client must take that by-value object, represented by <xref:System.ServiceModel.EndpointAddress10> and use it to create its own sessionful by-reference object.</span></span>  <span data-ttu-id="240c8-179">Las llamadas de método de cliente en el objeto con sesión se ejecutan en el servidor. En otras palabras, este objeto por referencia en WCF es un servicio WCF normal que se configura para ser con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-179">The client method calls on the sessionful object execute on the server.In other words, this by-reference object in WCF is a normal WCF service that is configured to be sessionful.</span></span>  
  
 <span data-ttu-id="240c8-180">En WCF, una sesión es una manera de asociar varios mensajes enviados entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="240c8-180">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span>  <span data-ttu-id="240c8-181">Esto significa que cuando un cliente obtiene una conexión a este servicio, se establecerá una sesión entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="240c8-181">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span>  <span data-ttu-id="240c8-182">El cliente usará una única instancia del objeto del lado servidor para todas las interacciones dentro de esta sesión única.</span><span class="sxs-lookup"><span data-stu-id="240c8-182">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span> <span data-ttu-id="240c8-183">Los contratos de WCF con sesión son similares a los patrones de solicitud/respuesta de red orientados a conexiones.</span><span class="sxs-lookup"><span data-stu-id="240c8-183">Sessionful WCF contracts are similar to connection-oriented network request/response patterns.</span></span>  
  
 <span data-ttu-id="240c8-184">Este escenario se representa mediante el siguiente método DCOM.</span><span class="sxs-lookup"><span data-stu-id="240c8-184">This scenario is represented by the following DCOM method.</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a><span data-ttu-id="240c8-185">Paso 1: Definir la interfaz de servicio de WCF con sesión y la implementación</span><span class="sxs-lookup"><span data-stu-id="240c8-185">Step 1: Define the Sessionful WCF service interface and implementation</span></span>  
 <span data-ttu-id="240c8-186">En primer lugar, defina una interfaz de servicio WCF que contenga el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-186">First, define a WCF service interface that contains the sessionful object.</span></span>  
  
 <span data-ttu-id="240c8-187">En este código, el objeto con sesión se marca con el atributo `ServiceContract`, que lo identifica como una interfaz de servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="240c8-187">In this code, the sessionful object is marked with the `ServiceContract` attribute, which identifies it as a regular WCF service interface.</span></span>  <span data-ttu-id="240c8-188">Además, se establece la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> para indicar que será un servicio con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-188">In addition, the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> property is set to indicate it will be a sessionful service.</span></span>  
  
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
  
 <span data-ttu-id="240c8-189">En el siguiente código se muestra la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="240c8-189">The following code shows the service implementation.</span></span>  
  
 <span data-ttu-id="240c8-190">El servicio se marca con el atributo [ServiceBehavior] y su propiedad InstanceContextMode se establece en InstanceContextMode.PerSessions para indicar que debe crearse una instancia única de este tipo para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-190">The service is marked with the [ServiceBehavior] attribute, and its InstanceContextMode property set to InstanceContextMode.PerSessions to indicate that a unique instance of this type should be created for each session.</span></span>  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a><span data-ttu-id="240c8-191">Paso 2: Definir el servicio del generador WCF para el objeto con sesión</span><span class="sxs-lookup"><span data-stu-id="240c8-191">Step 2: Define the WCF factory service for the sessionful object</span></span>  
 <span data-ttu-id="240c8-192">El servicio que crea el objeto con sesión debe definirse e implementarse.</span><span class="sxs-lookup"><span data-stu-id="240c8-192">The service that creates the sessionful object must be defined and implemented.</span></span> <span data-ttu-id="240c8-193">El código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="240c8-193">The following code shows how to do this.</span></span> <span data-ttu-id="240c8-194">Este código crea otro servicio WCF que devuelve un objeto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="240c8-194">This code creates another WCF service that returns an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  <span data-ttu-id="240c8-195">Se trata de una forma serializable de un punto de conexión que puede usarse para crear el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-195">This is a serializable form of an endpoint the can use to create the session-full object.</span></span>  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 <span data-ttu-id="240c8-196">En el siguiente ejemplo se muestra la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="240c8-196">The following is the implementation of this service.</span></span> <span data-ttu-id="240c8-197">Esta implementación mantiene un generador de canales de singleton para crear objetos con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-197">This implementation maintains a singleton channel factory to create sessionful objects.</span></span>  <span data-ttu-id="240c8-198">Cuando se llama a `GetInstanceAddress`, este crea un canal y crea un objeto <xref:System.ServiceModel.EndpointAddress10> que apunta a la dirección remota asociada a este canal.</span><span class="sxs-lookup"><span data-stu-id="240c8-198">When `GetInstanceAddress` is called, it creates a channel and creates an <xref:System.ServiceModel.EndpointAddress10> object that points to the remote address associated with this channel.</span></span>   <span data-ttu-id="240c8-199"><xref:System.ServiceModel.EndpointAddress10> es un tipo de datos que se puede devolver al cliente por valor.</span><span class="sxs-lookup"><span data-stu-id="240c8-199"><xref:System.ServiceModel.EndpointAddress10> is a data type that can be returned to the client by-value.</span></span>
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a><span data-ttu-id="240c8-200">Paso 3: Configurar e iniciar los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="240c8-200">Step 3: Configure and start the WCF services</span></span>  
 <span data-ttu-id="240c8-201">Para hospedar estos servicios, deberá agregar lo siguiente al archivo de configuración del servidor (web.config).</span><span class="sxs-lookup"><span data-stu-id="240c8-201">To host these services, you will need to make the following additions to the server’s configuration file (web.config).</span></span>  
  
1. <span data-ttu-id="240c8-202">Agregue una sección `<client>` que describa el extremo para el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-202">Add a `<client>` section that describes the endpoint for the sessionful object.</span></span>  <span data-ttu-id="240c8-203">En este escenario, el servidor también actúa como un cliente y debe configurarse para habilitar esta opción.</span><span class="sxs-lookup"><span data-stu-id="240c8-203">In this scenario, the server also acts as a client and must be configured to enable this.</span></span>  
  
2. <span data-ttu-id="240c8-204">En la sección `<services>`, declare los extremos de servicio para el generador y el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-204">In the `<services>` section, declare service endpoints for the factory and sessionful object.</span></span>  <span data-ttu-id="240c8-205">Esto permite al cliente comunicarse con los puntos de conexión de servicio, adquirir el <xref:System.ServiceModel.EndpointAddress10> y crear el canal con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-205">This enables the client to communicate with the service endpoints, acquire the <xref:System.ServiceModel.EndpointAddress10> and create the sessionful channel.</span></span>  
  
 <span data-ttu-id="240c8-206">En el siguiente ejemplo se muestra un archivo de configuración con estas opciones:</span><span class="sxs-lookup"><span data-stu-id="240c8-206">The following is an example configuration file with these settings:</span></span>  
  
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
  
 <span data-ttu-id="240c8-207">Agregue las siguientes líneas a una aplicación de consola para hospedar el servicio e inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="240c8-207">Add the following lines to a console application, to self-host the service, and start the app.</span></span>  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a><span data-ttu-id="240c8-208">Paso 4: Configurar el cliente y llamar al servicio</span><span class="sxs-lookup"><span data-stu-id="240c8-208">Step 4: Configure the client and call the service</span></span>  
 <span data-ttu-id="240c8-209">Configure el cliente para comunicarse con los servicios WCF; para ello, realice las siguientes entradas en el archivo de configuración de aplicación del proyecto (app.config).</span><span class="sxs-lookup"><span data-stu-id="240c8-209">Configure the client to communicate with the WCF services by making the following entries in the project’s application configuration file (app.config).</span></span>  
  
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
  
 <span data-ttu-id="240c8-210">Para llamar al servicio, agregue el código al cliente para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="240c8-210">To call the service, add the code to the client to do the following:</span></span>  
  
1. <span data-ttu-id="240c8-211">Cree un canal para el servicio `ISessionBoundFactory`.</span><span class="sxs-lookup"><span data-stu-id="240c8-211">Create a channel to the `ISessionBoundFactory` service.</span></span>  
  
2. <span data-ttu-id="240c8-212">Use el canal para invocar el servicio `ISessionBoundFactory` y obtener un objeto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="240c8-212">Use the channel to invoke the `ISessionBoundFactory` service an obtain an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  
  
3. <span data-ttu-id="240c8-213">Use <xref:System.ServiceModel.EndpointAddress10> para crear un canal para obtener un objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="240c8-213">Use the <xref:System.ServiceModel.EndpointAddress10> to create a channel to obtain a sessionful object.</span></span>  
  
4. <span data-ttu-id="240c8-214">Llame a los métodos `SetCurrentValue` y `GetCurrentValue` para mostrar que sigue siendo la misma instancia de objeto que se usa en varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="240c8-214">Call the `SetCurrentValue` and `GetCurrentValue` methods to demonstrate it remains the same object instance is used across multiple calls.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="240c8-215">Vea también</span><span class="sxs-lookup"><span data-stu-id="240c8-215">See also</span></span>

- [<span data-ttu-id="240c8-216">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="240c8-216">Basic WCF Programming</span></span>](../wcf/basic-wcf-programming.md)
- [<span data-ttu-id="240c8-217">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="240c8-217">Designing and Implementing Services</span></span>](../wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="240c8-218">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="240c8-218">Building Clients</span></span>](../wcf/building-clients.md)
- [<span data-ttu-id="240c8-219">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="240c8-219">Duplex Services</span></span>](../wcf/feature-details/duplex-services.md)
