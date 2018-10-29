---
title: Migración de .NET Remoting a WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 91cbfa33c6645fbc0a8d9b513e3a59799114a710
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200103"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="61b81-102">Migración de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-102">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="61b81-103">En este artículo se describe el procedimiento para migrar una aplicación que usa .NET Remoting para que use Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="61b81-103">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="61b81-104">Se comparan conceptos similares entre estos productos y se describe cómo llevar a cabo varios escenarios comunes de comunicación remota en WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-104">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="61b81-105">.NET Remoting es un producto heredado que solo se admite para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="61b81-105">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="61b81-106">No es seguro en entornos de confianza mixta porque no puede mantener los niveles de confianza independientes entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-106">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="61b81-107">Por ejemplo, nunca debe exponer un extremo de .NET Remoting a Internet o a los clientes que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-107">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="61b81-108">Recomendamos que las aplicaciones de Remoting existentes se migren a tecnologías más recientes y seguras.</span><span class="sxs-lookup"><span data-stu-id="61b81-108">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="61b81-109">Si el diseño de la aplicación solo usa HTTP y es RESTful, recomendamos ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="61b81-109">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="61b81-110">Para obtener más información, consulte ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="61b81-110">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="61b81-111">Si la aplicación se basa en SOAP o necesita protocolos que no sean HTTP, como TCP, recomendamos WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-111">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="61b81-112">Comparación de .NET Remoting con WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-112">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="61b81-113">En esta sección se comparan los bloques de creación básicos de .NET Remoting con sus equivalentes de WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-113">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="61b81-114">Usaremos estos bloques de creación más adelante para crear algunos escenarios comunes de cliente-servidor en WCF. El siguiente gráfico resume las principales similitudes y diferencias entre .NET Remoting y WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-114">We will use these building blocks later to create some common client-server scenarios in WCF.The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="61b81-115">.NET Remoting</span><span class="sxs-lookup"><span data-stu-id="61b81-115">.NET Remoting</span></span>|<span data-ttu-id="61b81-116">WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-116">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="61b81-117">Tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="61b81-117">Server type</span></span>|<span data-ttu-id="61b81-118">Subclase de MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="61b81-118">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="61b81-119">Marcar con el atributo [ServiceContract]</span><span class="sxs-lookup"><span data-stu-id="61b81-119">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="61b81-120">Operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="61b81-120">Service operations</span></span>|<span data-ttu-id="61b81-121">Métodos públicos en el tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="61b81-121">Public methods on server type</span></span>|<span data-ttu-id="61b81-122">Marcar con el atributo [OperationContract]</span><span class="sxs-lookup"><span data-stu-id="61b81-122">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="61b81-123">Serialización</span><span class="sxs-lookup"><span data-stu-id="61b81-123">Serialization</span></span>|<span data-ttu-id="61b81-124">ISerializable o [Serializable]</span><span class="sxs-lookup"><span data-stu-id="61b81-124">ISerializable or [Serializable]</span></span>|<span data-ttu-id="61b81-125">DataContractSerializer o XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="61b81-125">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="61b81-126">Objetos pasados</span><span class="sxs-lookup"><span data-stu-id="61b81-126">Objects passed</span></span>|<span data-ttu-id="61b81-127">Por valor o por referencia</span><span class="sxs-lookup"><span data-stu-id="61b81-127">By-value or by-reference</span></span>|<span data-ttu-id="61b81-128">Solo por valor</span><span class="sxs-lookup"><span data-stu-id="61b81-128">By-value only</span></span>|  
|<span data-ttu-id="61b81-129">Errores y excepciones</span><span class="sxs-lookup"><span data-stu-id="61b81-129">Errors/exceptions</span></span>|<span data-ttu-id="61b81-130">Cualquier excepción serializable</span><span class="sxs-lookup"><span data-stu-id="61b81-130">Any serializable exception</span></span>|<span data-ttu-id="61b81-131">FaultContract\<TDetail ></span><span class="sxs-lookup"><span data-stu-id="61b81-131">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="61b81-132">Objetos proxy de cliente</span><span class="sxs-lookup"><span data-stu-id="61b81-132">Client proxy objects</span></span>|<span data-ttu-id="61b81-133">Los servidores proxy transparentes fuertemente tipados se crean automáticamente desde MarshalByRefObjects</span><span class="sxs-lookup"><span data-stu-id="61b81-133">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="61b81-134">Los proxy fuertemente tipados se generan a petición con ChannelFactory\<TChannel ></span><span class="sxs-lookup"><span data-stu-id="61b81-134">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="61b81-135">Plataforma necesaria</span><span class="sxs-lookup"><span data-stu-id="61b81-135">Platform required</span></span>|<span data-ttu-id="61b81-136">Tanto el cliente como el servidor deben usar Microsoft OS y .NET</span><span class="sxs-lookup"><span data-stu-id="61b81-136">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="61b81-137">Multiplataforma</span><span class="sxs-lookup"><span data-stu-id="61b81-137">Cross-platform</span></span>|  
|<span data-ttu-id="61b81-138">Formato del mensaje</span><span class="sxs-lookup"><span data-stu-id="61b81-138">Message format</span></span>|<span data-ttu-id="61b81-139">Privado</span><span class="sxs-lookup"><span data-stu-id="61b81-139">Private</span></span>|<span data-ttu-id="61b81-140">Estándares del sector (SOAP, WS-\*, etc.)</span><span class="sxs-lookup"><span data-stu-id="61b81-140">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="61b81-141">Comparación de la implementación del servidor</span><span class="sxs-lookup"><span data-stu-id="61b81-141">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="61b81-142">Crear un servidor en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="61b81-142">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="61b81-143">Los tipos de servidor de .NET Remoting se deben derivar de MarshalByRefObject y definen los métodos a los que el cliente puede llamar, como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="61b81-143">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="61b81-144">Los métodos públicos de este tipo de servidor se convierten en el contrato público disponible para los clientes.</span><span class="sxs-lookup"><span data-stu-id="61b81-144">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="61b81-145">No hay una separación entre la interfaz pública del servidor y su implementación: un solo tipo controla ambas.</span><span class="sxs-lookup"><span data-stu-id="61b81-145">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="61b81-146">Una vez definido el tipo de servidor, se puede poner a disposición de los clientes, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-146">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
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
  
 <span data-ttu-id="61b81-147">Hay muchas maneras de hacer que el tipo de Remoting esté disponible como servidor, incluido el uso de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="61b81-147">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="61b81-148">Esto es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61b81-148">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="61b81-149">Crear un servidor en WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-149">Creating a Server in WCF</span></span>  
 <span data-ttu-id="61b81-150">El paso equivalente en WCF implica la creación de dos tipos: el "contrato de servicio" público y la implementación concreta.</span><span class="sxs-lookup"><span data-stu-id="61b81-150">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="61b81-151">El primero se declara como una interfaz marcada con [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="61b81-151">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="61b81-152">Los métodos disponibles para los clientes se marcan con [OperationContract]:</span><span class="sxs-lookup"><span data-stu-id="61b81-152">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="61b81-153">la implementación del servidor se define en una clase independiente concreta, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-153">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="61b81-154">Una vez definidos estos tipos, el servidor WCF se puede poner a disposición de los clientes, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-154">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine(String.Format("The WCF server is ready at {0}.",  
                                    baseAddress));  
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="61b81-155">TCP se usa en los dos ejemplos para que sean lo más parecidos posible.</span><span class="sxs-lookup"><span data-stu-id="61b81-155">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="61b81-156">Consulte los tutoriales más adelante en este tema para obtener ejemplos usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="61b81-156">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="61b81-157">Existen muchas formas de configurar y hospedar los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-157">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="61b81-158">Este es solo un ejemplo, conocido como "autohospedado".</span><span class="sxs-lookup"><span data-stu-id="61b81-158">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="61b81-159">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="61b81-159">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="61b81-160">Cómo definir un contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="61b81-160">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
-   [<span data-ttu-id="61b81-161">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="61b81-161">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
-   [<span data-ttu-id="61b81-162">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="61b81-162">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="61b81-163">Comparación de la implementación del cliente</span><span class="sxs-lookup"><span data-stu-id="61b81-163">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="61b81-164">Crear un cliente en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="61b81-164">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="61b81-165">Una vez que un objeto de servidor de .NET Remoting está disponible, los clientes lo pueden consumir, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-165">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),   
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine(String.Format("Customer {0} {1} received.",   
                                 customer.FirstName, customer.LastName));  
```  
  
 <span data-ttu-id="61b81-166">La instancia RemotingServer devuelta desde Activator.GetObject () se denomina "proxy transparente".</span><span class="sxs-lookup"><span data-stu-id="61b81-166">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="61b81-167">Implementa la API pública para el tipo RemotingServer en el cliente, pero todos los métodos llaman al objeto de servidor que se ejecuta en un proceso o una máquina distinta.</span><span class="sxs-lookup"><span data-stu-id="61b81-167">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="61b81-168">Crear un cliente en WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-168">Creating a Client in WCF</span></span>  
 <span data-ttu-id="61b81-169">El paso equivalente en WCF implica el uso de un generador de canales para crear el proxy de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="61b81-169">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="61b81-170">Como en Remoting, el objeto proxy se puede usar para invocar operaciones en el servidor, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-170">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =   
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine(String.Format("  Customer {0} {1} received.",  
                    customer.FirstName, customer.LastName));  
```  
  
 <span data-ttu-id="61b81-171">Este ejemplo muestra la programación en el nivel de canal porque es más similar al ejemplo de Remoting.</span><span class="sxs-lookup"><span data-stu-id="61b81-171">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="61b81-172">También está disponible el **Add Service Reference** enfoque en Visual Studio que genera código para simplificar la programación del cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-172">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="61b81-173">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="61b81-173">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="61b81-174">Programación de nivel de canal de cliente</span><span class="sxs-lookup"><span data-stu-id="61b81-174">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
-   [<span data-ttu-id="61b81-175">Cómo: agregar, actualizar o quitar una referencia de servicio</span><span class="sxs-lookup"><span data-stu-id="61b81-175">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="61b81-176">Uso de la serialización</span><span class="sxs-lookup"><span data-stu-id="61b81-176">Serialization Usage</span></span>  
 <span data-ttu-id="61b81-177">Tanto .NET Remoting como WCF usan la serialización para enviar objetos entre el cliente y el servidor, pero se diferencian en estos aspectos importantes:</span><span class="sxs-lookup"><span data-stu-id="61b81-177">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1.  <span data-ttu-id="61b81-178">Usan convenciones y serializadores diferentes para indicar qué se debe serializar.</span><span class="sxs-lookup"><span data-stu-id="61b81-178">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2.  <span data-ttu-id="61b81-179">.NET Remoting admite la serialización "por referencia" que permite el acceso del método o la propiedad a un nivel para ejecutar el código en el otro nivel que se encuentra fuera de los límites de seguridad.</span><span class="sxs-lookup"><span data-stu-id="61b81-179">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="61b81-180">Esta capacidad expone las vulnerabilidades de seguridad y es uno de los principales motivos por los que no se deben exponer nunca los extremos de Remoting a clientes que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-180">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3.  <span data-ttu-id="61b81-181">La serialización que usa .NET Remoting no es participativa (excluye explícitamente lo que no hay que serializar) y la serialización de WCF es participativa (marca explícitamente los miembros para serializar).</span><span class="sxs-lookup"><span data-stu-id="61b81-181">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="61b81-182">Serialización en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="61b81-182">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="61b81-183">.NET Remoting admite dos modos para serializar y deserializar objetos entre el cliente y el servidor:</span><span class="sxs-lookup"><span data-stu-id="61b81-183">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
-   <span data-ttu-id="61b81-184">*Por valor* : se serializan los valores del objeto a través de los límites del nivel, y se crea una nueva instancia de ese objeto en el otro nivel.</span><span class="sxs-lookup"><span data-stu-id="61b81-184">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="61b81-185">Las llamadas a los métodos o las propiedades de la nueva instancia solo se ejecutan localmente y no afectan al objeto o al nivel original.</span><span class="sxs-lookup"><span data-stu-id="61b81-185">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
-   <span data-ttu-id="61b81-186">*Por referencia* : una "referencia a objeto" especial se serializa a través de los límites del nivel.</span><span class="sxs-lookup"><span data-stu-id="61b81-186">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="61b81-187">Cuando un nivel interactúa con los métodos o las propiedades de ese objeto, se comunica de nuevo al objeto original del nivel original.</span><span class="sxs-lookup"><span data-stu-id="61b81-187">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="61b81-188">Los objetos por referencia pueden fluir en cualquier dirección: de servidor a cliente o de cliente a servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-188">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="61b81-189">Los tipos por valor de Remoting se marcan con el atributo [Serializable] o implementan ISerializable, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-189">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="61b81-190">Los tipos por referencia se derivan de la clase MarshalByRefObject, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-190">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="61b81-191">Es muy importante comprender las implicaciones de los objetos por referencia de Remoting.</span><span class="sxs-lookup"><span data-stu-id="61b81-191">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="61b81-192">Si cualquier nivel (cliente o servidor) envía un objeto por referencia al otro nivel, todas las llamadas de método se ejecutan en el nivel que posee el objeto.</span><span class="sxs-lookup"><span data-stu-id="61b81-192">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="61b81-193">Por ejemplo, un cliente que llame a los métodos en un objeto por referencia devuelto por el servidor ejecutará el código en el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-193">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="61b81-194">De forma similar, un servidor que llame a los métodos en un objeto por referencia que proporciona el cliente ejecutará el código en el cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-194">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="61b81-195">Por este motivo, solo se recomienda el uso de .NET Remoting en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-195">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="61b81-196">Exponer un extremo de .NET Remoting público a clientes sin confianza hará que un servidor de Remoting sea vulnerable a los ataques.</span><span class="sxs-lookup"><span data-stu-id="61b81-196">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="61b81-197">Serialización en WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-197">Serialization in WCF</span></span>  
 <span data-ttu-id="61b81-198">WCF solo admite la serialización por valor.</span><span class="sxs-lookup"><span data-stu-id="61b81-198">WCF supports only by-value serialization.</span></span> <span data-ttu-id="61b81-199">El modo más común de definir un tipo para el intercambio entre el cliente y el servidor es como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-199">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
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
  
 <span data-ttu-id="61b81-200">El atributo [DataContract] identifica este tipo como uno que se puede serializar y deserializar entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-200">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="61b81-201">El atributo [DataMember] identifica las propiedades o los campos individuales para serializar.</span><span class="sxs-lookup"><span data-stu-id="61b81-201">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="61b81-202">Cuando WCF envía un objeto entre niveles, solo serializa los valores y crea una nueva instancia del objeto en el otro nivel.</span><span class="sxs-lookup"><span data-stu-id="61b81-202">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="61b81-203">Cualquier interacción con los valores del objeto se produce solo localmente; no se comunican con el nivel del mismo modo que lo hacen los objetos por referencia de .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="61b81-203">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="61b81-204">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="61b81-204">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="61b81-205">Serialización y deserialización</span><span class="sxs-lookup"><span data-stu-id="61b81-205">Serialization and Deserialization</span></span>](./feature-details/serialization-and-deserialization.md)  
  
-   [<span data-ttu-id="61b81-206">Serialización en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="61b81-206">Serialization in Windows Communication Foundation</span></span>](https://msdn.microsoft.com/magazine/cc163569.aspx)  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="61b81-207">Capacidades de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="61b81-207">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="61b81-208">Excepciones en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="61b81-208">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="61b81-209">Las excepciones producidas por un servidor de Remoting se serializan, se envían al cliente y se producen localmente en el cliente, como cualquier otra excepción.</span><span class="sxs-lookup"><span data-stu-id="61b81-209">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="61b81-210">Las excepciones personalizadas se pueden crear subclasificando el tipo de excepción y marcándolo con [Serializable].</span><span class="sxs-lookup"><span data-stu-id="61b81-210">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="61b81-211">La mayoría de las excepciones de marco ya están marcadas de este modo, lo que permite que el servidor produzca la mayoría, se serialicen y se vuelvan a producir en el cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-211">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="61b81-212">Aunque este diseño es adecuado durante el desarrollo, la información del lado servidor se puede divulgar accidentalmente al cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-212">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="61b81-213">Este es uno de los muchos motivos por los que Remoting solo se debe usar en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-213">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="61b81-214">Excepciones y errores en WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-214">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="61b81-215">WCF no admite la devolución de tipos de excepción arbitrarios del servidor al cliente porque podrían provocar la divulgación accidental de información.</span><span class="sxs-lookup"><span data-stu-id="61b81-215">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="61b81-216">Si una operación de servicio produce una excepción inesperada, hace que se produzca una excepción FaultException de propósito general en el cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-216">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="61b81-217">Esta excepción no contiene información del motivo o el lugar en el que ocurrió el problema y, para algunas aplicaciones, es suficiente.</span><span class="sxs-lookup"><span data-stu-id="61b81-217">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="61b81-218">Las aplicaciones que necesitan comunicar más información del error al cliente lo hacen definiendo un contrato de error.</span><span class="sxs-lookup"><span data-stu-id="61b81-218">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="61b81-219">Para ello, primero crean un tipo [DataContract] para transportar la información del error.</span><span class="sxs-lookup"><span data-stu-id="61b81-219">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
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
  
 <span data-ttu-id="61b81-220">Especifican el contrato de error que se usará para cada operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="61b81-220">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="61b81-221">El servidor informa de las condiciones del error produciendo una excepción  FaultException.</span><span class="sxs-lookup"><span data-stu-id="61b81-221">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {   
        CustomerId = customerId,   
        ErrorMessage = "Illegal customer Id"   
    });  
```  
  
 <span data-ttu-id="61b81-222">Y, siempre que el cliente realice una solicitud al servidor, puede detectar errores como excepciones normales.</span><span class="sxs-lookup"><span data-stu-id="61b81-222">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine(String.Format("Fault received: {0}",  
    fault.Detail.ErrorMessage));  
}  
```  
  
 <span data-ttu-id="61b81-223">Para obtener más información sobre los contratos de errores, consulte <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="61b81-223">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="61b81-224">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="61b81-224">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="61b81-225">Seguridad en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="61b81-225">Security in .NET Remoting</span></span>  
 <span data-ttu-id="61b81-226">Algunos canales de .NET Remoting admiten características de seguridad como la autenticación y el cifrado en el nivel de canal (IPC y TCP).</span><span class="sxs-lookup"><span data-stu-id="61b81-226">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="61b81-227">El canal HTTP se basa en Internet Information Services (IIS) para la autenticación y el cifrado.</span><span class="sxs-lookup"><span data-stu-id="61b81-227">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="61b81-228">A pesar de esta compatibilidad, debe considerar .NET Remoting como un protocolo de comunicación no seguro y usarlo solo en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-228">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="61b81-229">No exponga nunca un extremo de Remoting público a Internet o a clientes que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-229">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="61b81-230">Seguridad en WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-230">Security in WCF</span></span>  
 <span data-ttu-id="61b81-231">WCF se diseñó teniendo en cuenta la seguridad, en parte para tratar los tipos de vulnerabilidades que se encuentran en .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="61b81-231">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="61b81-232">WCF ofrece seguridad a nivel de mensajes y transporte, y ofrece muchas opciones para la autenticación, la autorización, el cifrado, etc.</span><span class="sxs-lookup"><span data-stu-id="61b81-232">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="61b81-233">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="61b81-233">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="61b81-234">Seguridad</span><span class="sxs-lookup"><span data-stu-id="61b81-234">Security</span></span>](./feature-details/security.md)  
  
-   [<span data-ttu-id="61b81-235">Guía de seguridad WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-235">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="61b81-236">Migrar a WCF</span><span class="sxs-lookup"><span data-stu-id="61b81-236">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="61b81-237">¿Por qué migrar de Remoting a WCF?</span><span class="sxs-lookup"><span data-stu-id="61b81-237">Why Migrate from Remoting to WCF?</span></span>  
  
-   <span data-ttu-id="61b81-238">**.NET remoting es un producto heredado.**</span><span class="sxs-lookup"><span data-stu-id="61b81-238">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="61b81-239">Como se describe en [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), se considera un producto heredado y no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="61b81-239">As described in [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="61b81-240">Se recomienda WCF o ASP.NET Web API para aplicaciones nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="61b81-240">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
-   <span data-ttu-id="61b81-241">**WCF usa los estándares multiplataforma.**</span><span class="sxs-lookup"><span data-stu-id="61b81-241">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="61b81-242">WCF se diseñó teniendo en cuenta la interoperabilidad multiplataforma y admite muchos estándares del sector (SOAP, WS-Security, WS-Trust, etc.).</span><span class="sxs-lookup"><span data-stu-id="61b81-242">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="61b81-243">Un servicio WCF puede interoperar con clientes que se ejecuten en sistemas operativos distintos de Windows.</span><span class="sxs-lookup"><span data-stu-id="61b81-243">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="61b81-244">Remoting se diseñó principalmente para entornos donde las aplicaciones de servidor y de cliente se ejecutan con .NET Framework en un sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="61b81-244">Remoting was designed primarily for environments where both the server and client applications run using the .NET framework on a Windows operating system.</span></span>  
  
-   <span data-ttu-id="61b81-245">**WCF tiene seguridad integrada.**</span><span class="sxs-lookup"><span data-stu-id="61b81-245">**WCF has built-in security.**</span></span> <span data-ttu-id="61b81-246">WCF se diseñó teniendo en cuenta la seguridad y ofrece muchas opciones para la autenticación, la seguridad de nivel de transporte, la seguridad de mensajes, etc. Remoting se diseñó para facilitar la interoperabilidad de las aplicaciones, pero no se diseñó para ser seguro en entornos que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-246">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="61b81-247">WCF se diseñó para funcionar en entornos de confianza y de no confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-247">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="61b81-248">Recomendaciones de migración</span><span class="sxs-lookup"><span data-stu-id="61b81-248">Migration Recommendations</span></span>  
 <span data-ttu-id="61b81-249">Estos son los pasos recomendados para migrar de .NET Remoting a WCF:</span><span class="sxs-lookup"><span data-stu-id="61b81-249">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
-   <span data-ttu-id="61b81-250">**Cree el contrato de servicio.**</span><span class="sxs-lookup"><span data-stu-id="61b81-250">**Create the service contract.**</span></span> <span data-ttu-id="61b81-251">Defina los tipos de interfaz de servicio y márquelos con el atributo [ServiceContract]. Marque todos los métodos a los que podrán llamar los clientes con [OperationContract].</span><span class="sxs-lookup"><span data-stu-id="61b81-251">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
-   <span data-ttu-id="61b81-252">**Cree el contrato de datos.**</span><span class="sxs-lookup"><span data-stu-id="61b81-252">**Create the data contract.**</span></span> <span data-ttu-id="61b81-253">Defina los tipos de datos que se intercambiarán entre el cliente y el servidor, y márquelos con el atributo [DataContract].</span><span class="sxs-lookup"><span data-stu-id="61b81-253">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="61b81-254">Marque todos los campos y propiedades que podrá usar el cliente con [DataMember].</span><span class="sxs-lookup"><span data-stu-id="61b81-254">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
-   <span data-ttu-id="61b81-255">**Crear el contrato de error (opcional).**</span><span class="sxs-lookup"><span data-stu-id="61b81-255">**Create the fault contract (optional).**</span></span> <span data-ttu-id="61b81-256">Cree los tipos que se intercambiarán entre el cliente y el servidor cuando se produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="61b81-256">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="61b81-257">Marque estos tipos con [DataContract] y [DataMember] para que se puedan serializar.</span><span class="sxs-lookup"><span data-stu-id="61b81-257">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="61b81-258">Marque también con [FaultContract] todas las operaciones de servicio que marcó con [OperationContract] para indicar qué errores pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="61b81-258">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
-   <span data-ttu-id="61b81-259">**Configurar y hospedar el servicio.**</span><span class="sxs-lookup"><span data-stu-id="61b81-259">**Configure and host the service.**</span></span> <span data-ttu-id="61b81-260">Una vez creado el contrato de servicio, el siguiente paso es configurar un enlace para exponer el servicio a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="61b81-260">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="61b81-261">Para obtener más información, consulte [puntos de conexión: direcciones, enlaces y contratos](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="61b81-261">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="61b81-262">Una vez migrada la aplicación de Remoting a WCF, es importante quitar las dependencias de .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="61b81-262">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="61b81-263">Esto garantiza que se quitan las vulnerabilidades de Remoting de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61b81-263">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="61b81-264">Estos pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="61b81-264">These steps include the following:</span></span>  
  
-   <span data-ttu-id="61b81-265">**Suspender el uso de MarshalByRefObject.**</span><span class="sxs-lookup"><span data-stu-id="61b81-265">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="61b81-266">El tipo MarshalByRefObject solo existe para Remoting y WCF no lo usa.</span><span class="sxs-lookup"><span data-stu-id="61b81-266">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="61b81-267">Se debe quitar o cambiar cualquier tipo de aplicación que subclasifique MarshalByRefObject.</span><span class="sxs-lookup"><span data-stu-id="61b81-267">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span> <span data-ttu-id="61b81-268">El tipo MarshalByRefObject solo existe para Remoting y WCF no lo usa.</span><span class="sxs-lookup"><span data-stu-id="61b81-268">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="61b81-269">Se debe quitar o cambiar cualquier tipo de aplicación que subclasifique MarshalByRefObject.</span><span class="sxs-lookup"><span data-stu-id="61b81-269">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
-   <span data-ttu-id="61b81-270">**Interrumpa el uso de [Serializable] e ISerializable.**</span><span class="sxs-lookup"><span data-stu-id="61b81-270">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="61b81-271">El atributo [Serializable] y la interfaz ISerializable se diseñaron originalmente para serializar los tipos dentro de entornos de confianza y Remoting los usa.</span><span class="sxs-lookup"><span data-stu-id="61b81-271">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="61b81-272">La serialización de WCF se basa en los tipos marcados con [DataContract] y [DataMember].</span><span class="sxs-lookup"><span data-stu-id="61b81-272">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="61b81-273">Los tipos de datos que usa una aplicación se deben modificar para usar [DataContract] y no para usar ISerializable o [Serializable].</span><span class="sxs-lookup"><span data-stu-id="61b81-273">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span> <span data-ttu-id="61b81-274">El atributo [Serializable] y la interfaz ISerializable se diseñaron originalmente para serializar los tipos dentro de entornos de confianza y Remoting los usa.</span><span class="sxs-lookup"><span data-stu-id="61b81-274">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="61b81-275">La serialización de WCF se basa en los tipos marcados con [DataContract] y [DataMember].</span><span class="sxs-lookup"><span data-stu-id="61b81-275">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="61b81-276">Los tipos de datos que usa una aplicación se deben modificar para usar [DataContract] y no para usar ISerializable o [Serializable].</span><span class="sxs-lookup"><span data-stu-id="61b81-276">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="61b81-277">Escenarios de migración</span><span class="sxs-lookup"><span data-stu-id="61b81-277">Migration Scenarios</span></span>  
 <span data-ttu-id="61b81-278">Ahora veamos cómo conseguir los siguientes escenarios comunes de Remoting en WCF:</span><span class="sxs-lookup"><span data-stu-id="61b81-278">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1.  <span data-ttu-id="61b81-279">El servidor devuelve un objeto por valor al cliente</span><span class="sxs-lookup"><span data-stu-id="61b81-279">Server returns an object by-value to the client</span></span>  
  
2.  <span data-ttu-id="61b81-280">El servidor devuelve un objeto por referencia al cliente</span><span class="sxs-lookup"><span data-stu-id="61b81-280">Server returns an object by-reference to the client</span></span>  
  
3.  <span data-ttu-id="61b81-281">El cliente envía un objeto por valor al servidor</span><span class="sxs-lookup"><span data-stu-id="61b81-281">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61b81-282">No se permite el envío de un objeto por referencia desde el cliente al servidor en WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-282">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="61b81-283">Al leer estos escenarios, suponga que nuestras interfaces de línea base para .NET Remoting son parecidas al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61b81-283">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="61b81-284">Aquí, la implementación de .NET Remoting no es importante porque solo queremos mostrar cómo usar WCF para implementar una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="61b81-284">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
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
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="61b81-285">Escenario 1: el servicio devuelve un objeto por valor</span><span class="sxs-lookup"><span data-stu-id="61b81-285">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="61b81-286">Este escenario muestra un servidor que devuelve un objeto al cliente por valor.</span><span class="sxs-lookup"><span data-stu-id="61b81-286">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="61b81-287">WCF siempre devuelve los objetos desde el servidor por valor, por lo que los siguientes pasos solo describen cómo compilar un servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="61b81-287">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1.  <span data-ttu-id="61b81-288">Empiece definiendo una interfaz pública para el servicio WCF y márquela con el atributo [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="61b81-288">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="61b81-289">Usamos [OperationContract] para identificar los métodos del lado servidor a los que llamará nuestro cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-289">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
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
  
2.  <span data-ttu-id="61b81-290">El siguiente paso es crear el contrato de datos para este servicio.</span><span class="sxs-lookup"><span data-stu-id="61b81-290">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="61b81-291">Lo hacemos creando clases (no interfaces) marcadas con el atributo [DataContract].</span><span class="sxs-lookup"><span data-stu-id="61b81-291">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="61b81-292">Las propiedades o los campos individuales que queremos que sean visibles para el cliente y el servidor se marcan con [DataMember].</span><span class="sxs-lookup"><span data-stu-id="61b81-292">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="61b81-293">Si queremos permitir los tipos derivados, debemos usar el atributo [KnownType] para identificarlos.</span><span class="sxs-lookup"><span data-stu-id="61b81-293">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="61b81-294">Los únicos tipos que WCF permite serializar o deserializar para este servicio son los de la interfaz de servicio y estos "tipos conocidos".</span><span class="sxs-lookup"><span data-stu-id="61b81-294">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="61b81-295">Se rechazarán los intentos de intercambiar cualquier otro tipo que no se encuentre en esta lista.</span><span class="sxs-lookup"><span data-stu-id="61b81-295">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
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
  
3.  <span data-ttu-id="61b81-296">A continuación, ofrecemos la implementación de la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="61b81-296">Next, we provide the implementation for the service interface.</span></span>  
  
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
  
4.  <span data-ttu-id="61b81-297">Para ejecutar el servicio WCF, debemos declarar un extremo que exponga esa interfaz de servicio en una dirección URL específica con un enlace WCF específico.</span><span class="sxs-lookup"><span data-stu-id="61b81-297">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="61b81-298">Normalmente, esto se lleva a cabo agregando las siguientes secciones al archivo web.config del proyecto de servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-298">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
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
  
5.  <span data-ttu-id="61b81-299">A continuación, se puede iniciar el servicio WCF con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="61b81-299">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="61b81-300">Cuando se inicia este ServiceHost, usa el archivo web.config para establecer el contrato, el enlace y el punto de conexión adecuados.</span><span class="sxs-lookup"><span data-stu-id="61b81-300">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="61b81-301">Para obtener más información acerca de los archivos de configuración, consulte [configurar servicios mediante archivos de configuración](./configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="61b81-301">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="61b81-302">Este estilo de inicio del servidor se conoce como autohospedaje.</span><span class="sxs-lookup"><span data-stu-id="61b81-302">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="61b81-303">Para obtener más información sobre otras opciones para hospedar servicios WCF, vea [servicios de hospedaje](./hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="61b81-303">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6.  <span data-ttu-id="61b81-304">El archivo app.config del proyecto de cliente debe declarar la información de enlace coincidente para el punto de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="61b81-304">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="61b81-305">La manera más fácil de hacerlo en Visual Studio es usar **Add Service Reference**, que actualizará automáticamente el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="61b81-305">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="61b81-306">Además, estos cambios se pueden agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="61b81-306">Alternatively, these same changes can be added manually.</span></span>  
  
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
  
     <span data-ttu-id="61b81-307">Para obtener más información sobre el uso de **Add Service Reference**, consulte [Cómo: agregar, actualizar o quitar una referencia de servicio](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span><span class="sxs-lookup"><span data-stu-id="61b81-307">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7.  <span data-ttu-id="61b81-308">Ahora podemos llamar al servicio WCF desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="61b81-308">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="61b81-309">Para ello creamos un generador de canales para el servicio, solicitando un canal y llamando directamente al método que queremos en ese canal.</span><span class="sxs-lookup"><span data-stu-id="61b81-309">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="61b81-310">Podemos hacerlo porque el canal implementa la interfaz del servicio y controla la lógica de la solicitud o la respuesta subyacente para nosotros.</span><span class="sxs-lookup"><span data-stu-id="61b81-310">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="61b81-311">El valor devuelto de esta llamada al método es la copia deserializada de la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-311">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine(String.Format("  Customer {0} {1} received.",  
           customer.FirstName, customer.LastName));  
   ```  
  
 <span data-ttu-id="61b81-312">Los objetos devueltos por WCF desde el servidor al cliente siempre son por valor.</span><span class="sxs-lookup"><span data-stu-id="61b81-312">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="61b81-313">Los objetos son copias deserializadas de los datos enviados por el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-313">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="61b81-314">El cliente puede llamar a métodos en estas copias locales sin riesgo de invocar código de servidor a través de devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="61b81-314">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="61b81-315">Escenario 2: el servidor devuelve un objeto por referencia</span><span class="sxs-lookup"><span data-stu-id="61b81-315">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="61b81-316">Este escenario muestra el servidor que proporciona un objeto al cliente por referencia.</span><span class="sxs-lookup"><span data-stu-id="61b81-316">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="61b81-317">En .NET Remoting, esto se controla de forma automática para cualquier tipo derivado de MarshalByRefObject, que se serializa por referencia.</span><span class="sxs-lookup"><span data-stu-id="61b81-317">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="61b81-318">Un ejemplo de este escenario es permitir que varios clientes tengan objetos del lado servidor con sesión independientes.</span><span class="sxs-lookup"><span data-stu-id="61b81-318">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="61b81-319">Como se mencionó anteriormente, los objetos devueltos por un servicio WCF siempre son por valor, por lo que no hay ningún equivalente directo de un objeto por referencia, pero es posible conseguir algo similar a la semántica por referencia con un objeto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="61b81-319">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="61b81-320">Se trata de un objeto por valor serializable que puede usar el cliente para obtener un objeto por referencia con sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-320">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="61b81-321">Esto habilita el escenario de tener varios clientes con objetos del lado servidor con sesión independientes.</span><span class="sxs-lookup"><span data-stu-id="61b81-321">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1.  <span data-ttu-id="61b81-322">Primero necesitamos definir un contrato de servicio WCF que se corresponda con el propio objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-322">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
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
    >  <span data-ttu-id="61b81-323">Tenga en cuenta que el objeto con sesión está marcado con [ServiceContract], lo que hace que sea una interfaz de servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="61b81-323">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="61b81-324">El hecho de establecer la propiedad SessionMode indica que será un servicio con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-324">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="61b81-325">En WCF, una sesión es un modo de asociar varios mensajes enviados entre dos extremos.</span><span class="sxs-lookup"><span data-stu-id="61b81-325">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="61b81-326">Esto significa que cuando un cliente obtiene una conexión a este servicio, se establecerá una sesión entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-326">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="61b81-327">El cliente usará una única instancia del objeto del lado servidor para todas las interacciones dentro de esta sesión única.</span><span class="sxs-lookup"><span data-stu-id="61b81-327">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2.  <span data-ttu-id="61b81-328">A continuación, debemos proporcionar la implementación de esta interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="61b81-328">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="61b81-329">Al representarlo con [ServiceBehavior] y al configurar InstanceContextMode, le indicamos a WCF que queremos usar una instancia única de este tipo para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-329">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
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
  
3.  <span data-ttu-id="61b81-330">Ahora necesitamos un modo de obtener una instancia de este objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-330">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="61b81-331">Para ello, creamos otra interfaz de servicio WCF que devuelva un objeto EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="61b81-331">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="61b81-332">Se trata de un formato serializable de un extremo que el cliente puede usar para crear el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-332">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="61b81-333">E implementamos este servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="61b81-333">And we implement this WCF service:</span></span>  
  
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
  
     <span data-ttu-id="61b81-334">Esta implementación mantiene un generador de canales de singleton para crear objetos con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-334">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="61b81-335">Cuando se llama a GetInstanceAddress(), crea un canal y crea un objeto EndpointAddress10 que apunta de forma efectiva a la dirección remota asociada a este canal.</span><span class="sxs-lookup"><span data-stu-id="61b81-335">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="61b81-336">EndpointAddress10 es simplemente un tipo de datos que se puede devolver al cliente por valor.</span><span class="sxs-lookup"><span data-stu-id="61b81-336">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4.  <span data-ttu-id="61b81-337">Debemos modificar el archivo de configuración del servidor mediante las siguientes dos cosas que se muestran en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="61b81-337">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1.  <span data-ttu-id="61b81-338">Declarar un \<cliente > sección que describe el punto de conexión para el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-338">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="61b81-339">Esto es necesario porque el servidor también actúa como un cliente en esta situación.</span><span class="sxs-lookup"><span data-stu-id="61b81-339">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2.  <span data-ttu-id="61b81-340">Declare los extremos para el objeto de generador y el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-340">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="61b81-341">Esto es necesario para permitir que el cliente se comunique con los extremos del servicio para adquirir EndpointAddress10 y para crear el canal con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-341">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
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
  
     <span data-ttu-id="61b81-342">A continuación, podemos iniciar estos servicios:</span><span class="sxs-lookup"><span data-stu-id="61b81-342">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5.  <span data-ttu-id="61b81-343">Configuramos el cliente declarando estos mismos extremos en el archivo app.config de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="61b81-343">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
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
  
6.  <span data-ttu-id="61b81-344">Para crear y usar este objeto con sesión, el cliente debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="61b81-344">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1.  <span data-ttu-id="61b81-345">Crear un canal para el servicio ISessionBoundFactory.</span><span class="sxs-lookup"><span data-stu-id="61b81-345">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2.  <span data-ttu-id="61b81-346">Usar ese canal para invocar el servicio para obtener EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="61b81-346">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3.  <span data-ttu-id="61b81-347">Usar EndpointAddress10 para crear un canal para obtener un objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="61b81-347">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4.  <span data-ttu-id="61b81-348">Interactuar con el objeto con sesión para mostrar que sigue siendo la misma instancia en varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="61b81-348">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
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
  
 <span data-ttu-id="61b81-349">WCF siempre devuelve objetos por valor, pero es posible que admita el equivalente de la semántica por referencia con EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="61b81-349">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="61b81-350">Esto permite que el cliente solicite una instancia de servicio WCF con sesión, tras lo cual puede interactuar con ella como con cualquier otro servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="61b81-350">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="61b81-351">Escenario 3: el cliente envía al servidor una instancia por valor</span><span class="sxs-lookup"><span data-stu-id="61b81-351">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="61b81-352">Este escenario muestra el cliente enviando una instancia de objeto no primitivo al servidor por valor.</span><span class="sxs-lookup"><span data-stu-id="61b81-352">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="61b81-353">Dado que WCF solo envía objetos por valor, este escenario muestra el uso de WCF normal.</span><span class="sxs-lookup"><span data-stu-id="61b81-353">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1.  <span data-ttu-id="61b81-354">Use el mismo servicio WCF del escenario 1.</span><span class="sxs-lookup"><span data-stu-id="61b81-354">Use the same WCF Service from Scenario 1.</span></span>  
  
2.  <span data-ttu-id="61b81-355">Use el cliente para crear un nuevo objeto por valor (Customer), cree un canal para comunicarse con el servicio ICustomerService y envíele el objeto.</span><span class="sxs-lookup"><span data-stu-id="61b81-355">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
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
   Console.WriteLine(String.Format("  Server returned {0}.", success));  
   ```  
  
     <span data-ttu-id="61b81-356">El objeto de cliente se serializa y se envía al servidor, donde se deserializa en una nueva copia de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="61b81-356">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61b81-357">Este código también muestra el envío de un tipo derivado (PremiumCustomer).</span><span class="sxs-lookup"><span data-stu-id="61b81-357">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="61b81-358">La interfaz de servicio espera un objeto Customer, pero el atributo [KnownType] de la clase Customer indica que también se permite PremiumCustomer.</span><span class="sxs-lookup"><span data-stu-id="61b81-358">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="61b81-359">WCF no podrá serializar o deserializar cualquier otro tipo a través de esta interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="61b81-359">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="61b81-360">Los intercambios de datos de WCF normales son por valor.</span><span class="sxs-lookup"><span data-stu-id="61b81-360">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="61b81-361">Esto garantiza que la invocación de métodos en uno de estos objetos de datos solo se ejecuta localmente; no invocará código en el otro nivel.</span><span class="sxs-lookup"><span data-stu-id="61b81-361">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="61b81-362">Aunque es posible lograr algo parecido a los objetos por referencia devueltos *desde* el servidor, no es posible que un cliente pasar un objeto por referencia *a* el servidor.</span><span class="sxs-lookup"><span data-stu-id="61b81-362">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="61b81-363">En WCF puede conseguir un escenario que necesite una conversación entre el cliente y el servidor con un servicio dúplex.</span><span class="sxs-lookup"><span data-stu-id="61b81-363">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="61b81-364">Para obtener más información, consulte [servicios dúplex](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="61b81-364">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="61b81-365">Resumen</span><span class="sxs-lookup"><span data-stu-id="61b81-365">Summary</span></span>  
 <span data-ttu-id="61b81-366">.NET Remoting es un marco de comunicación diseñado para su uso únicamente en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="61b81-366">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="61b81-367">Se trata de un producto heredado que solo se admite para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="61b81-367">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="61b81-368">No se debe usar para compilar nuevas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="61b81-368">It should not be used to build new applications.</span></span> <span data-ttu-id="61b81-369">En cambio, WCF se diseñó teniendo en cuenta la seguridad y se recomienda para las aplicaciones nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="61b81-369">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="61b81-370">Microsoft recomienda la migración de las aplicaciones Remoting existentes para usar WCF o ASP.NET Web API en su lugar.</span><span class="sxs-lookup"><span data-stu-id="61b81-370">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>