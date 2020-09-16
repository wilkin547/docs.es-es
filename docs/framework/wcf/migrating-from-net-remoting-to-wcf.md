---
title: Migración de .NET Remoting a WCF
description: Obtenga información sobre cómo migrar una aplicación que usa .NET Remoting para usar WCF. Puede realizar varios escenarios comunes de comunicación remota en WCF.
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 73bdac5d8f4d39694f038bb600828c79e527efb0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542855"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="783d9-104">Migración de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-104">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="783d9-105">En este artículo se describe el procedimiento para migrar una aplicación que usa .NET Remoting para que use Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="783d9-105">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="783d9-106">Se comparan conceptos similares entre estos productos y se describe cómo llevar a cabo varios escenarios comunes de comunicación remota en WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-106">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="783d9-107">.NET Remoting es un producto heredado que solo se admite para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="783d9-107">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="783d9-108">No es seguro en entornos de confianza mixta porque no puede mantener los niveles de confianza independientes entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-108">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="783d9-109">Por ejemplo, nunca debe exponer un punto de conexión de .NET Remoting a Internet o a los clientes que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-109">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="783d9-110">Recomendamos que las aplicaciones de Remoting existentes se migren a tecnologías más recientes y seguras.</span><span class="sxs-lookup"><span data-stu-id="783d9-110">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="783d9-111">Si el diseño de la aplicación solo usa HTTP y es RESTful, recomendamos ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="783d9-111">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="783d9-112">Para obtener más información, consulte ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="783d9-112">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="783d9-113">Si la aplicación se basa en SOAP o necesita protocolos que no sean HTTP, como TCP, recomendamos WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-113">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="783d9-114">Comparación de .NET Remoting con WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-114">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="783d9-115">En esta sección se comparan los bloques de creación básicos de .NET Remoting con sus equivalentes de WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-115">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="783d9-116">Usaremos estos bloques de creación más adelante para crear algunos escenarios comunes de cliente-servidor en WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-116">We will use these building blocks later to create some common client-server scenarios in WCF.</span></span> <span data-ttu-id="783d9-117">En el gráfico siguiente se resumen las similitudes y diferencias principales entre .NET Remoting y WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-117">The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="783d9-118">.NET Remoting</span><span class="sxs-lookup"><span data-stu-id="783d9-118">.NET Remoting</span></span>|<span data-ttu-id="783d9-119">WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-119">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="783d9-120">Tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="783d9-120">Server type</span></span>|<span data-ttu-id="783d9-121">Subclase de MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="783d9-121">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="783d9-122">Marcar con el atributo [ServiceContract]</span><span class="sxs-lookup"><span data-stu-id="783d9-122">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="783d9-123">Operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="783d9-123">Service operations</span></span>|<span data-ttu-id="783d9-124">Métodos públicos en el tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="783d9-124">Public methods on server type</span></span>|<span data-ttu-id="783d9-125">Marcar con el atributo [OperationContract]</span><span class="sxs-lookup"><span data-stu-id="783d9-125">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="783d9-126">Serialización</span><span class="sxs-lookup"><span data-stu-id="783d9-126">Serialization</span></span>|<span data-ttu-id="783d9-127">ISerializable o [Serializable]</span><span class="sxs-lookup"><span data-stu-id="783d9-127">ISerializable or [Serializable]</span></span>|<span data-ttu-id="783d9-128">DataContractSerializer o XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="783d9-128">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="783d9-129">Objetos pasados</span><span class="sxs-lookup"><span data-stu-id="783d9-129">Objects passed</span></span>|<span data-ttu-id="783d9-130">Por valor o por referencia</span><span class="sxs-lookup"><span data-stu-id="783d9-130">By-value or by-reference</span></span>|<span data-ttu-id="783d9-131">Solo por valor</span><span class="sxs-lookup"><span data-stu-id="783d9-131">By-value only</span></span>|  
|<span data-ttu-id="783d9-132">Errores y excepciones</span><span class="sxs-lookup"><span data-stu-id="783d9-132">Errors/exceptions</span></span>|<span data-ttu-id="783d9-133">Cualquier excepción serializable</span><span class="sxs-lookup"><span data-stu-id="783d9-133">Any serializable exception</span></span>|<span data-ttu-id="783d9-134">FaultContract\<TDetail></span><span class="sxs-lookup"><span data-stu-id="783d9-134">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="783d9-135">Objetos proxy de cliente</span><span class="sxs-lookup"><span data-stu-id="783d9-135">Client proxy objects</span></span>|<span data-ttu-id="783d9-136">Los servidores proxy transparentes fuertemente tipados se crean automáticamente desde MarshalByRefObjects</span><span class="sxs-lookup"><span data-stu-id="783d9-136">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="783d9-137">Los proxies fuertemente tipados se generan a petición mediante ChannelFactory\<TChannel></span><span class="sxs-lookup"><span data-stu-id="783d9-137">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="783d9-138">Plataforma necesaria</span><span class="sxs-lookup"><span data-stu-id="783d9-138">Platform required</span></span>|<span data-ttu-id="783d9-139">Tanto el cliente como el servidor deben usar Microsoft OS y .NET</span><span class="sxs-lookup"><span data-stu-id="783d9-139">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="783d9-140">Multiplataforma</span><span class="sxs-lookup"><span data-stu-id="783d9-140">Cross-platform</span></span>|  
|<span data-ttu-id="783d9-141">Formato de los mensajes</span><span class="sxs-lookup"><span data-stu-id="783d9-141">Message format</span></span>|<span data-ttu-id="783d9-142">Private</span><span class="sxs-lookup"><span data-stu-id="783d9-142">Private</span></span>|<span data-ttu-id="783d9-143">Estándares del sector (SOAP, WS-\*, etc.)</span><span class="sxs-lookup"><span data-stu-id="783d9-143">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="783d9-144">Comparación de la implementación del servidor</span><span class="sxs-lookup"><span data-stu-id="783d9-144">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="783d9-145">Crear un servidor en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="783d9-145">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="783d9-146">Los tipos de servidor de .NET Remoting se deben derivar de MarshalByRefObject y definen los métodos a los que el cliente puede llamar, como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="783d9-146">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="783d9-147">Los métodos públicos de este tipo de servidor se convierten en el contrato público disponible para los clientes.</span><span class="sxs-lookup"><span data-stu-id="783d9-147">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="783d9-148">No hay una separación entre la interfaz pública del servidor y su implementación: un solo tipo controla ambas.</span><span class="sxs-lookup"><span data-stu-id="783d9-148">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="783d9-149">Una vez definido el tipo de servidor, se puede poner a disposición de los clientes, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-149">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
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
  
 <span data-ttu-id="783d9-150">Hay muchas maneras de hacer que el tipo de Remoting esté disponible como servidor, incluido el uso de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="783d9-150">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="783d9-151">Esto es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="783d9-151">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="783d9-152">Crear un servidor en WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-152">Creating a Server in WCF</span></span>  
 <span data-ttu-id="783d9-153">El paso equivalente en WCF implica la creación de dos tipos: el "contrato de servicio" público y la implementación concreta.</span><span class="sxs-lookup"><span data-stu-id="783d9-153">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="783d9-154">El primero se declara como una interfaz marcada con [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="783d9-154">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="783d9-155">Los métodos disponibles para los clientes se marcan con [OperationContract]:</span><span class="sxs-lookup"><span data-stu-id="783d9-155">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="783d9-156">la implementación del servidor se define en una clase independiente concreta, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-156">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="783d9-157">Una vez definidos estos tipos, el servidor WCF se puede poner a disposición de los clientes, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-157">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
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
> <span data-ttu-id="783d9-158">TCP se usa en los dos ejemplos para que sean lo más parecidos posible.</span><span class="sxs-lookup"><span data-stu-id="783d9-158">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="783d9-159">Consulte los tutoriales más adelante en este tema para obtener ejemplos usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="783d9-159">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="783d9-160">Existen muchas formas de configurar y hospedar los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-160">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="783d9-161">Este es solo un ejemplo, conocido como "autohospedado".</span><span class="sxs-lookup"><span data-stu-id="783d9-161">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="783d9-162">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="783d9-162">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="783d9-163">Cómo definir un contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="783d9-163">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
- [<span data-ttu-id="783d9-164">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="783d9-164">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
- [<span data-ttu-id="783d9-165">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="783d9-165">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="783d9-166">Comparación de la implementación del cliente</span><span class="sxs-lookup"><span data-stu-id="783d9-166">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="783d9-167">Crear un cliente en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="783d9-167">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="783d9-168">Una vez que un objeto de servidor de .NET Remoting está disponible, los clientes lo pueden consumir, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-168">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="783d9-169">La instancia RemotingServer devuelta desde Activator.GetObject () se denomina "proxy transparente".</span><span class="sxs-lookup"><span data-stu-id="783d9-169">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="783d9-170">Implementa la API pública para el tipo RemotingServer en el cliente, pero todos los métodos llaman al objeto de servidor que se ejecuta en un proceso o una máquina distinta.</span><span class="sxs-lookup"><span data-stu-id="783d9-170">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="783d9-171">Crear un cliente en WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-171">Creating a Client in WCF</span></span>  
 <span data-ttu-id="783d9-172">El paso equivalente en WCF implica el uso de un generador de canales para crear el proxy de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="783d9-172">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="783d9-173">Como en Remoting, el objeto proxy se puede usar para invocar operaciones en el servidor, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-173">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
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
  
 <span data-ttu-id="783d9-174">Este ejemplo muestra la programación en el nivel de canal porque es más similar al ejemplo de Remoting.</span><span class="sxs-lookup"><span data-stu-id="783d9-174">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="783d9-175">También está disponible el enfoque de **Agregar referencia de servicio** en Visual Studio que genera código para simplificar la programación de cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-175">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="783d9-176">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="783d9-176">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="783d9-177">Programación a nivel de canal de cliente</span><span class="sxs-lookup"><span data-stu-id="783d9-177">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
- [<span data-ttu-id="783d9-178">Cómo: Agregar, actualizar o quitar una referencia de servicio</span><span class="sxs-lookup"><span data-stu-id="783d9-178">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="783d9-179">Uso de la serialización</span><span class="sxs-lookup"><span data-stu-id="783d9-179">Serialization Usage</span></span>  
 <span data-ttu-id="783d9-180">Tanto .NET Remoting como WCF usan la serialización para enviar objetos entre el cliente y el servidor, pero se diferencian en estos aspectos importantes:</span><span class="sxs-lookup"><span data-stu-id="783d9-180">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1. <span data-ttu-id="783d9-181">Usan convenciones y serializadores diferentes para indicar qué se debe serializar.</span><span class="sxs-lookup"><span data-stu-id="783d9-181">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2. <span data-ttu-id="783d9-182">.NET Remoting admite la serialización "por referencia" que permite el acceso del método o la propiedad a un nivel para ejecutar el código en el otro nivel que se encuentra fuera de los límites de seguridad.</span><span class="sxs-lookup"><span data-stu-id="783d9-182">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="783d9-183">Esta capacidad expone las vulnerabilidades de seguridad y es uno de los principales motivos por los que no se deben exponer nunca los extremos de Remoting a clientes que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-183">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3. <span data-ttu-id="783d9-184">La serialización que usa .NET Remoting no es participativa (excluye explícitamente lo que no hay que serializar) y la serialización de WCF es participativa (marca explícitamente los miembros para serializar).</span><span class="sxs-lookup"><span data-stu-id="783d9-184">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="783d9-185">Serialización en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="783d9-185">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="783d9-186">.NET Remoting admite dos modos para serializar y deserializar objetos entre el cliente y el servidor:</span><span class="sxs-lookup"><span data-stu-id="783d9-186">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
- <span data-ttu-id="783d9-187">*Por valor* : los valores del objeto se serializan a través de los límites del nivel y se crea una nueva instancia de ese objeto en el otro nivel.</span><span class="sxs-lookup"><span data-stu-id="783d9-187">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="783d9-188">Las llamadas a los métodos o las propiedades de la nueva instancia solo se ejecutan localmente y no afectan al objeto o al nivel original.</span><span class="sxs-lookup"><span data-stu-id="783d9-188">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
- <span data-ttu-id="783d9-189">*Por referencia* : una "referencia de objeto" especial se serializa a través de los límites del nivel.</span><span class="sxs-lookup"><span data-stu-id="783d9-189">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="783d9-190">Cuando un nivel interactúa con los métodos o las propiedades de ese objeto, se comunica de nuevo al objeto original del nivel original.</span><span class="sxs-lookup"><span data-stu-id="783d9-190">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="783d9-191">Los objetos por referencia pueden fluir en cualquier dirección: de servidor a cliente o de cliente a servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-191">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="783d9-192">Los tipos por valor de Remoting se marcan con el atributo [Serializable] o implementan ISerializable, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-192">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="783d9-193">Los tipos por referencia se derivan de la clase MarshalByRefObject, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-193">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="783d9-194">Es muy importante comprender las implicaciones de los objetos por referencia de Remoting.</span><span class="sxs-lookup"><span data-stu-id="783d9-194">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="783d9-195">Si cualquier nivel (cliente o servidor) envía un objeto por referencia al otro nivel, todas las llamadas de método se ejecutan en el nivel que posee el objeto.</span><span class="sxs-lookup"><span data-stu-id="783d9-195">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="783d9-196">Por ejemplo, un cliente que llame a los métodos en un objeto por referencia devuelto por el servidor ejecutará el código en el servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-196">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="783d9-197">De forma similar, un servidor que llame a los métodos en un objeto por referencia que proporciona el cliente ejecutará el código en el cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-197">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="783d9-198">Por este motivo, solo se recomienda el uso de .NET Remoting en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-198">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="783d9-199">Exponer un extremo de .NET Remoting público a clientes sin confianza hará que un servidor de Remoting sea vulnerable a los ataques.</span><span class="sxs-lookup"><span data-stu-id="783d9-199">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="783d9-200">Serialización en WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-200">Serialization in WCF</span></span>  
 <span data-ttu-id="783d9-201">WCF solo admite la serialización por valor.</span><span class="sxs-lookup"><span data-stu-id="783d9-201">WCF supports only by-value serialization.</span></span> <span data-ttu-id="783d9-202">El modo más común de definir un tipo para el intercambio entre el cliente y el servidor es como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-202">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
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
  
 <span data-ttu-id="783d9-203">El atributo [DataContract] identifica este tipo como uno que se puede serializar y deserializar entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-203">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="783d9-204">El atributo [DataMember] identifica las propiedades o los campos individuales para serializar.</span><span class="sxs-lookup"><span data-stu-id="783d9-204">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="783d9-205">Cuando WCF envía un objeto entre niveles, solo serializa los valores y crea una nueva instancia del objeto en el otro nivel.</span><span class="sxs-lookup"><span data-stu-id="783d9-205">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="783d9-206">Cualquier interacción con los valores del objeto se produce solo localmente; no se comunican con el nivel del mismo modo que lo hacen los objetos por referencia de .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="783d9-206">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="783d9-207">Para obtener más información, vea [serialización y deserialización](./feature-details/serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="783d9-207">For more information, see [Serialization and Deserialization](./feature-details/serialization-and-deserialization.md).</span></span>  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="783d9-208">Capacidades de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="783d9-208">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="783d9-209">Excepciones en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="783d9-209">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="783d9-210">Las excepciones producidas por un servidor de Remoting se serializan, se envían al cliente y se producen localmente en el cliente, como cualquier otra excepción.</span><span class="sxs-lookup"><span data-stu-id="783d9-210">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="783d9-211">Las excepciones personalizadas se pueden crear subclasificando el tipo de excepción y marcándolo con [Serializable].</span><span class="sxs-lookup"><span data-stu-id="783d9-211">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="783d9-212">La mayoría de las excepciones de marco ya están marcadas de este modo, lo que permite que el servidor produzca la mayoría, se serialicen y se vuelvan a producir en el cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-212">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="783d9-213">Aunque este diseño es adecuado durante el desarrollo, la información del lado servidor se puede divulgar accidentalmente al cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-213">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="783d9-214">Este es uno de los muchos motivos por los que Remoting solo se debe usar en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-214">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="783d9-215">Excepciones y errores en WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-215">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="783d9-216">WCF no admite la devolución de tipos de excepción arbitrarios del servidor al cliente porque podrían provocar la divulgación accidental de información.</span><span class="sxs-lookup"><span data-stu-id="783d9-216">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="783d9-217">Si una operación de servicio produce una excepción inesperada, hace que se produzca una excepción FaultException de propósito general en el cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-217">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="783d9-218">Esta excepción no contiene información del motivo o el lugar en el que ocurrió el problema y, para algunas aplicaciones, es suficiente.</span><span class="sxs-lookup"><span data-stu-id="783d9-218">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="783d9-219">Las aplicaciones que necesitan comunicar más información del error al cliente lo hacen definiendo un contrato de error.</span><span class="sxs-lookup"><span data-stu-id="783d9-219">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="783d9-220">Para ello, primero crean un tipo [DataContract] para transportar la información del error.</span><span class="sxs-lookup"><span data-stu-id="783d9-220">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
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
  
 <span data-ttu-id="783d9-221">Especifican el contrato de error que se usará para cada operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="783d9-221">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="783d9-222">El servidor informa de las condiciones del error produciendo una excepción  FaultException.</span><span class="sxs-lookup"><span data-stu-id="783d9-222">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {
        CustomerId = customerId,
        ErrorMessage = "Illegal customer Id"
    });  
```  
  
 <span data-ttu-id="783d9-223">Y, siempre que el cliente realice una solicitud al servidor, puede detectar errores como excepciones normales.</span><span class="sxs-lookup"><span data-stu-id="783d9-223">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
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
  
 <span data-ttu-id="783d9-224">Para obtener más información sobre los contratos de errores, consulte <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="783d9-224">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="783d9-225">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="783d9-225">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="783d9-226">Seguridad en .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="783d9-226">Security in .NET Remoting</span></span>  
 <span data-ttu-id="783d9-227">Algunos canales de .NET Remoting admiten características de seguridad como la autenticación y el cifrado en el nivel de canal (IPC y TCP).</span><span class="sxs-lookup"><span data-stu-id="783d9-227">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="783d9-228">El canal HTTP se basa en Internet Information Services (IIS) para la autenticación y el cifrado.</span><span class="sxs-lookup"><span data-stu-id="783d9-228">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="783d9-229">A pesar de esta compatibilidad, debe considerar .NET Remoting como un protocolo de comunicación no seguro y usarlo solo en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-229">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="783d9-230">No exponga nunca un extremo de Remoting público a Internet o a clientes que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-230">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="783d9-231">Seguridad en WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-231">Security in WCF</span></span>  
 <span data-ttu-id="783d9-232">WCF se diseñó teniendo en cuenta la seguridad, en parte para tratar los tipos de vulnerabilidades que se encuentran en .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="783d9-232">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="783d9-233">WCF ofrece seguridad a nivel de mensajes y transporte, y ofrece muchas opciones para la autenticación, la autorización, el cifrado, etc.</span><span class="sxs-lookup"><span data-stu-id="783d9-233">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="783d9-234">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="783d9-234">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="783d9-235">Seguridad</span><span class="sxs-lookup"><span data-stu-id="783d9-235">Security</span></span>](./feature-details/security.md)  
  
- [<span data-ttu-id="783d9-236">Instrucciones de seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-236">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="783d9-237">Migrar a WCF</span><span class="sxs-lookup"><span data-stu-id="783d9-237">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="783d9-238">¿Por qué migrar de Remoting a WCF?</span><span class="sxs-lookup"><span data-stu-id="783d9-238">Why Migrate from Remoting to WCF?</span></span>  
  
- <span data-ttu-id="783d9-239">**.NET Remoting es un producto heredado.**</span><span class="sxs-lookup"><span data-stu-id="783d9-239">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="783d9-240">Tal y como se describe en [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)), se considera un producto heredado y no se recomienda para el nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="783d9-240">As described in [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="783d9-241">Se recomienda WCF o ASP.NET Web API para aplicaciones nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="783d9-241">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
- <span data-ttu-id="783d9-242">**WCF usa los estándares multiplataforma.**</span><span class="sxs-lookup"><span data-stu-id="783d9-242">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="783d9-243">WCF se diseñó teniendo en cuenta la interoperabilidad multiplataforma y admite muchos estándares del sector (SOAP, WS-Security, WS-Trust, etc.).</span><span class="sxs-lookup"><span data-stu-id="783d9-243">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="783d9-244">Un servicio WCF puede interoperar con clientes que se ejecuten en sistemas operativos distintos de Windows.</span><span class="sxs-lookup"><span data-stu-id="783d9-244">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="783d9-245">La comunicación remota se diseñó principalmente para entornos en los que las aplicaciones cliente y servidor se ejecutan con .NET Framework en un sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="783d9-245">Remoting was designed primarily for environments where both the server and client applications run using .NET Framework on a Windows operating system.</span></span>
  
- <span data-ttu-id="783d9-246">**WCF tiene seguridad integrada.**</span><span class="sxs-lookup"><span data-stu-id="783d9-246">**WCF has built-in security.**</span></span> <span data-ttu-id="783d9-247">WCF se diseñó teniendo en cuenta la seguridad y ofrece muchas opciones de autenticación, seguridad de nivel de transporte, seguridad de nivel de mensaje, etc. La comunicación remota se diseñó para facilitar la interoperabilidad de las aplicaciones, pero no se diseñó para ser segura en entornos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-247">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="783d9-248">WCF se diseñó para funcionar en entornos de confianza y de no confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-248">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="783d9-249">Recomendaciones de migración</span><span class="sxs-lookup"><span data-stu-id="783d9-249">Migration Recommendations</span></span>  
 <span data-ttu-id="783d9-250">Estos son los pasos recomendados para migrar de .NET Remoting a WCF:</span><span class="sxs-lookup"><span data-stu-id="783d9-250">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
- <span data-ttu-id="783d9-251">**Cree el contrato de servicio.**</span><span class="sxs-lookup"><span data-stu-id="783d9-251">**Create the service contract.**</span></span> <span data-ttu-id="783d9-252">Defina los tipos de interfaz de servicio y márquelos con el atributo [ServiceContract]. Marque todos los métodos a los que podrán llamar los clientes con [OperationContract].</span><span class="sxs-lookup"><span data-stu-id="783d9-252">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
- <span data-ttu-id="783d9-253">**Cree el contrato de datos.**</span><span class="sxs-lookup"><span data-stu-id="783d9-253">**Create the data contract.**</span></span> <span data-ttu-id="783d9-254">Defina los tipos de datos que se intercambiarán entre el cliente y el servidor, y márquelos con el atributo [DataContract].</span><span class="sxs-lookup"><span data-stu-id="783d9-254">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="783d9-255">Marque todos los campos y propiedades que podrá usar el cliente con [DataMember].</span><span class="sxs-lookup"><span data-stu-id="783d9-255">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
- <span data-ttu-id="783d9-256">**Cree el contrato de error (opcional).**</span><span class="sxs-lookup"><span data-stu-id="783d9-256">**Create the fault contract (optional).**</span></span> <span data-ttu-id="783d9-257">Cree los tipos que se intercambiarán entre el cliente y el servidor cuando se produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="783d9-257">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="783d9-258">Marque estos tipos con [DataContract] y [DataMember] para que se puedan serializar.</span><span class="sxs-lookup"><span data-stu-id="783d9-258">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="783d9-259">Marque también con [FaultContract] todas las operaciones de servicio que marcó con [OperationContract] para indicar qué errores pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="783d9-259">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
- <span data-ttu-id="783d9-260">**Configurar y hospedar el servicio.**</span><span class="sxs-lookup"><span data-stu-id="783d9-260">**Configure and host the service.**</span></span> <span data-ttu-id="783d9-261">Una vez creado el contrato de servicio, el siguiente paso es configurar un enlace para exponer el servicio a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="783d9-261">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="783d9-262">Para obtener más información, vea [puntos de conexión: direcciones, enlaces y contratos](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="783d9-262">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="783d9-263">Una vez migrada la aplicación de Remoting a WCF, es importante quitar las dependencias de .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="783d9-263">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="783d9-264">Esto garantiza que se quitan las vulnerabilidades de Remoting de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="783d9-264">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="783d9-265">Estos pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="783d9-265">These steps include the following:</span></span>  
  
- <span data-ttu-id="783d9-266">**Interrumpa el uso de MarshalByRefObject.**</span><span class="sxs-lookup"><span data-stu-id="783d9-266">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="783d9-267">El tipo MarshalByRefObject solo existe para Remoting y WCF no lo usa.</span><span class="sxs-lookup"><span data-stu-id="783d9-267">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="783d9-268">Se debe quitar o cambiar cualquier tipo de aplicación que subclasifique MarshalByRefObject.</span><span class="sxs-lookup"><span data-stu-id="783d9-268">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
- <span data-ttu-id="783d9-269">**Interrumpa el uso de [Serializable] e ISerializable.**</span><span class="sxs-lookup"><span data-stu-id="783d9-269">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="783d9-270">El atributo [Serializable] y la interfaz ISerializable se diseñaron originalmente para serializar los tipos dentro de entornos de confianza y Remoting los usa.</span><span class="sxs-lookup"><span data-stu-id="783d9-270">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="783d9-271">La serialización de WCF se basa en los tipos marcados con [DataContract] y [DataMember].</span><span class="sxs-lookup"><span data-stu-id="783d9-271">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="783d9-272">Los tipos de datos que usa una aplicación se deben modificar para usar [DataContract] y no para usar ISerializable o [Serializable].</span><span class="sxs-lookup"><span data-stu-id="783d9-272">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="783d9-273">Escenarios de migración</span><span class="sxs-lookup"><span data-stu-id="783d9-273">Migration Scenarios</span></span>  
 <span data-ttu-id="783d9-274">Ahora veamos cómo conseguir los siguientes escenarios comunes de Remoting en WCF:</span><span class="sxs-lookup"><span data-stu-id="783d9-274">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1. <span data-ttu-id="783d9-275">El servidor devuelve un objeto por valor al cliente</span><span class="sxs-lookup"><span data-stu-id="783d9-275">Server returns an object by-value to the client</span></span>  
  
2. <span data-ttu-id="783d9-276">El servidor devuelve un objeto por referencia al cliente</span><span class="sxs-lookup"><span data-stu-id="783d9-276">Server returns an object by-reference to the client</span></span>  
  
3. <span data-ttu-id="783d9-277">El cliente envía un objeto por valor al servidor</span><span class="sxs-lookup"><span data-stu-id="783d9-277">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
> <span data-ttu-id="783d9-278">No se permite el envío de un objeto por referencia desde el cliente al servidor en WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-278">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="783d9-279">Al leer estos escenarios, suponga que nuestras interfaces de línea base para .NET Remoting son parecidas al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="783d9-279">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="783d9-280">Aquí, la implementación de .NET Remoting no es importante porque solo queremos mostrar cómo usar WCF para implementar una funcionalidad equivalente.</span><span class="sxs-lookup"><span data-stu-id="783d9-280">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
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
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="783d9-281">Escenario 1: el servicio devuelve un objeto por valor</span><span class="sxs-lookup"><span data-stu-id="783d9-281">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="783d9-282">Este escenario muestra un servidor que devuelve un objeto al cliente por valor.</span><span class="sxs-lookup"><span data-stu-id="783d9-282">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="783d9-283">WCF siempre devuelve los objetos desde el servidor por valor, por lo que los siguientes pasos solo describen cómo compilar un servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="783d9-283">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1. <span data-ttu-id="783d9-284">Empiece definiendo una interfaz pública para el servicio WCF y márquela con el atributo [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="783d9-284">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="783d9-285">Usamos [OperationContract] para identificar los métodos del lado servidor a los que llamará nuestro cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-285">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
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
  
2. <span data-ttu-id="783d9-286">El siguiente paso es crear el contrato de datos para este servicio.</span><span class="sxs-lookup"><span data-stu-id="783d9-286">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="783d9-287">Lo hacemos creando clases (no interfaces) marcadas con el atributo [DataContract].</span><span class="sxs-lookup"><span data-stu-id="783d9-287">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="783d9-288">Las propiedades o los campos individuales que queremos que sean visibles para el cliente y el servidor se marcan con [DataMember].</span><span class="sxs-lookup"><span data-stu-id="783d9-288">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="783d9-289">Si queremos permitir los tipos derivados, debemos usar el atributo [KnownType] para identificarlos.</span><span class="sxs-lookup"><span data-stu-id="783d9-289">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="783d9-290">Los únicos tipos que WCF permite serializar o deserializar para este servicio son los de la interfaz de servicio y estos "tipos conocidos".</span><span class="sxs-lookup"><span data-stu-id="783d9-290">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="783d9-291">Se rechazarán los intentos de intercambiar cualquier otro tipo que no se encuentre en esta lista.</span><span class="sxs-lookup"><span data-stu-id="783d9-291">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
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
  
3. <span data-ttu-id="783d9-292">A continuación, ofrecemos la implementación de la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="783d9-292">Next, we provide the implementation for the service interface.</span></span>  
  
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
  
4. <span data-ttu-id="783d9-293">Para ejecutar el servicio WCF, debemos declarar un extremo que exponga esa interfaz de servicio en una dirección URL específica con un enlace WCF específico.</span><span class="sxs-lookup"><span data-stu-id="783d9-293">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="783d9-294">Normalmente, esto se lleva a cabo agregando las siguientes secciones al archivo web.config del proyecto de servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-294">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
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
  
5. <span data-ttu-id="783d9-295">A continuación, se puede iniciar el servicio WCF con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="783d9-295">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="783d9-296">Cuando se inicia este ServiceHost, usa el archivo web.config para establecer el contrato, el enlace y el extremo adecuados.</span><span class="sxs-lookup"><span data-stu-id="783d9-296">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="783d9-297">Para obtener más información sobre los archivos de configuración, vea [configuración de servicios mediante archivos de configuración](./configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="783d9-297">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="783d9-298">Este estilo de inicio del servidor se conoce como autohospedaje.</span><span class="sxs-lookup"><span data-stu-id="783d9-298">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="783d9-299">Para obtener más información sobre otras opciones para hospedar servicios WCF, vea [servicios de hospedaje](./hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="783d9-299">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6. <span data-ttu-id="783d9-300">El archivo app.config del proyecto de cliente debe declarar la información de enlace coincidente para el punto de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="783d9-300">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="783d9-301">La forma más fácil de hacerlo en Visual Studio es usar **Agregar referencia de servicio**, que actualizará automáticamente el archivo de app.config.</span><span class="sxs-lookup"><span data-stu-id="783d9-301">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="783d9-302">Además, estos cambios se pueden agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="783d9-302">Alternatively, these same changes can be added manually.</span></span>  
  
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
  
     <span data-ttu-id="783d9-303">Para obtener más información acerca del uso de **Agregar referencia de servicio**, consulte [Cómo: agregar, actualizar o quitar una referencia de servicio](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span><span class="sxs-lookup"><span data-stu-id="783d9-303">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7. <span data-ttu-id="783d9-304">Ahora podemos llamar al servicio WCF desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="783d9-304">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="783d9-305">Para ello creamos un generador de canales para el servicio, solicitando un canal y llamando directamente al método que queremos en ese canal.</span><span class="sxs-lookup"><span data-stu-id="783d9-305">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="783d9-306">Podemos hacerlo porque el canal implementa la interfaz del servicio y controla la lógica de la solicitud o la respuesta subyacente para nosotros.</span><span class="sxs-lookup"><span data-stu-id="783d9-306">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="783d9-307">El valor devuelto de esta llamada al método es la copia deserializada de la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-307">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 <span data-ttu-id="783d9-308">Los objetos devueltos por WCF desde el servidor al cliente siempre son por valor.</span><span class="sxs-lookup"><span data-stu-id="783d9-308">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="783d9-309">Los objetos son copias deserializadas de los datos enviados por el servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-309">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="783d9-310">El cliente puede llamar a métodos en estas copias locales sin riesgo de invocar código de servidor a través de devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="783d9-310">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="783d9-311">Escenario 2: el servidor devuelve un objeto por referencia</span><span class="sxs-lookup"><span data-stu-id="783d9-311">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="783d9-312">Este escenario muestra el servidor que proporciona un objeto al cliente por referencia.</span><span class="sxs-lookup"><span data-stu-id="783d9-312">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="783d9-313">En .NET Remoting, esto se controla de forma automática para cualquier tipo derivado de MarshalByRefObject, que se serializa por referencia.</span><span class="sxs-lookup"><span data-stu-id="783d9-313">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="783d9-314">Un ejemplo de este escenario es permitir que varios clientes tengan objetos del lado servidor con sesión independientes.</span><span class="sxs-lookup"><span data-stu-id="783d9-314">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="783d9-315">Como se mencionó anteriormente, los objetos devueltos por un servicio WCF siempre son por valor, por lo que no hay ningún equivalente directo de un objeto por referencia, pero es posible conseguir algo similar a la semántica por referencia con un objeto <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="783d9-315">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="783d9-316">Se trata de un objeto por valor serializable que puede usar el cliente para obtener un objeto por referencia con sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-316">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="783d9-317">Esto habilita el escenario de tener varios clientes con objetos del lado servidor con sesión independientes.</span><span class="sxs-lookup"><span data-stu-id="783d9-317">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1. <span data-ttu-id="783d9-318">Primero necesitamos definir un contrato de servicio WCF que se corresponda con el propio objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-318">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
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
    > <span data-ttu-id="783d9-319">Tenga en cuenta que el objeto con sesión está marcado con [ServiceContract], lo que hace que sea una interfaz de servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="783d9-319">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="783d9-320">El hecho de establecer la propiedad SessionMode indica que será un servicio con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-320">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="783d9-321">En WCF, una sesión es una manera de asociar varios mensajes enviados entre dos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="783d9-321">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="783d9-322">Esto significa que cuando un cliente obtiene una conexión a este servicio, se establecerá una sesión entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-322">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="783d9-323">El cliente usará una única instancia del objeto del lado servidor para todas las interacciones dentro de esta sesión única.</span><span class="sxs-lookup"><span data-stu-id="783d9-323">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2. <span data-ttu-id="783d9-324">A continuación, debemos proporcionar la implementación de esta interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="783d9-324">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="783d9-325">Al representarlo con [ServiceBehavior] y al configurar InstanceContextMode, le indicamos a WCF que queremos usar una instancia única de este tipo para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-325">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
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
  
3. <span data-ttu-id="783d9-326">Ahora necesitamos un modo de obtener una instancia de este objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-326">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="783d9-327">Para ello, creamos otra interfaz de servicio WCF que devuelva un objeto EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="783d9-327">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="783d9-328">Se trata de un formato serializable de un punto de conexión que el cliente puede usar para crear el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-328">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="783d9-329">E implementamos este servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="783d9-329">And we implement this WCF service:</span></span>  
  
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
  
     <span data-ttu-id="783d9-330">Esta implementación mantiene un generador de canales de singleton para crear objetos con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-330">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="783d9-331">Cuando se llama a GetInstanceAddress(), crea un canal y crea un objeto EndpointAddress10 que apunta de forma efectiva a la dirección remota asociada a este canal.</span><span class="sxs-lookup"><span data-stu-id="783d9-331">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="783d9-332">EndpointAddress10 es simplemente un tipo de datos que se puede devolver al cliente por valor.</span><span class="sxs-lookup"><span data-stu-id="783d9-332">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4. <span data-ttu-id="783d9-333">Debemos modificar el archivo de configuración del servidor mediante las siguientes dos cosas que se muestran en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="783d9-333">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1. <span data-ttu-id="783d9-334">Declare una \<client> sección que describa el punto de conexión para el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-334">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="783d9-335">Esto es necesario porque el servidor también actúa como un cliente en esta situación.</span><span class="sxs-lookup"><span data-stu-id="783d9-335">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2. <span data-ttu-id="783d9-336">Declare los extremos para el objeto de generador y el objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-336">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="783d9-337">Esto es necesario para permitir que el cliente se comunique con los puntos de conexión del servicio para adquirir EndpointAddress10 y para crear el canal con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-337">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
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
  
     <span data-ttu-id="783d9-338">A continuación, podemos iniciar estos servicios:</span><span class="sxs-lookup"><span data-stu-id="783d9-338">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. <span data-ttu-id="783d9-339">Configuramos el cliente declarando estos mismos puntos de conexión en el archivo app.config de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="783d9-339">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
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
  
6. <span data-ttu-id="783d9-340">Para crear y usar este objeto con sesión, el cliente debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="783d9-340">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1. <span data-ttu-id="783d9-341">Crear un canal para el servicio ISessionBoundFactory.</span><span class="sxs-lookup"><span data-stu-id="783d9-341">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2. <span data-ttu-id="783d9-342">Usar ese canal para invocar el servicio para obtener EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="783d9-342">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3. <span data-ttu-id="783d9-343">Usar EndpointAddress10 para crear un canal para obtener un objeto con sesión.</span><span class="sxs-lookup"><span data-stu-id="783d9-343">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4. <span data-ttu-id="783d9-344">Interactuar con el objeto con sesión para mostrar que sigue siendo la misma instancia en varias llamadas.</span><span class="sxs-lookup"><span data-stu-id="783d9-344">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
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
  
 <span data-ttu-id="783d9-345">WCF siempre devuelve objetos por valor, pero es posible que admita el equivalente de la semántica por referencia con EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="783d9-345">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="783d9-346">Esto permite que el cliente solicite una instancia de servicio WCF con sesión, tras lo cual puede interactuar con ella como con cualquier otro servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="783d9-346">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="783d9-347">Escenario 3: el cliente envía al servidor una instancia por valor</span><span class="sxs-lookup"><span data-stu-id="783d9-347">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="783d9-348">Este escenario muestra el cliente enviando una instancia de objeto no primitivo al servidor por valor.</span><span class="sxs-lookup"><span data-stu-id="783d9-348">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="783d9-349">Dado que WCF solo envía objetos por valor, este escenario muestra el uso de WCF normal.</span><span class="sxs-lookup"><span data-stu-id="783d9-349">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1. <span data-ttu-id="783d9-350">Use el mismo servicio WCF del escenario 1.</span><span class="sxs-lookup"><span data-stu-id="783d9-350">Use the same WCF Service from Scenario 1.</span></span>  
  
2. <span data-ttu-id="783d9-351">Use el cliente para crear un nuevo objeto por valor (Customer), cree un canal para comunicarse con el servicio ICustomerService y envíele el objeto.</span><span class="sxs-lookup"><span data-stu-id="783d9-351">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
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
  
     <span data-ttu-id="783d9-352">El objeto de cliente se serializa y se envía al servidor, donde se deserializa en una nueva copia de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="783d9-352">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="783d9-353">Este código también muestra el envío de un tipo derivado (PremiumCustomer).</span><span class="sxs-lookup"><span data-stu-id="783d9-353">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="783d9-354">La interfaz de servicio espera un objeto Customer, pero el atributo [KnownType] de la clase Customer indica que también se permite PremiumCustomer.</span><span class="sxs-lookup"><span data-stu-id="783d9-354">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="783d9-355">WCF no podrá serializar o deserializar cualquier otro tipo a través de esta interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="783d9-355">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="783d9-356">Los intercambios de datos de WCF normales son por valor.</span><span class="sxs-lookup"><span data-stu-id="783d9-356">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="783d9-357">Esto garantiza que la invocación de métodos en uno de estos objetos de datos solo se ejecuta localmente; no invocará código en el otro nivel.</span><span class="sxs-lookup"><span data-stu-id="783d9-357">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="783d9-358">Aunque es posible lograr algo similar a los objetos por referencia devueltos *desde* el servidor, no es posible que un cliente pase un objeto por referencia *al* servidor.</span><span class="sxs-lookup"><span data-stu-id="783d9-358">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="783d9-359">En WCF puede conseguir un escenario que necesite una conversación entre el cliente y el servidor con un servicio dúplex.</span><span class="sxs-lookup"><span data-stu-id="783d9-359">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="783d9-360">Para obtener más información, vea [servicios dúplex](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="783d9-360">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="783d9-361">Resumen</span><span class="sxs-lookup"><span data-stu-id="783d9-361">Summary</span></span>  
 <span data-ttu-id="783d9-362">.NET Remoting es un marco de comunicación diseñado para su uso únicamente en entornos de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="783d9-362">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="783d9-363">Se trata de un producto heredado que solo se admite para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="783d9-363">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="783d9-364">No se debe usar para compilar nuevas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="783d9-364">It should not be used to build new applications.</span></span> <span data-ttu-id="783d9-365">En cambio, WCF se diseñó teniendo en cuenta la seguridad y se recomienda para las aplicaciones nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="783d9-365">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="783d9-366">Microsoft recomienda la migración de las aplicaciones Remoting existentes para usar WCF o ASP.NET Web API en su lugar.</span><span class="sxs-lookup"><span data-stu-id="783d9-366">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>
