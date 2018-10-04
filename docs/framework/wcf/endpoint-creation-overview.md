---
title: Información general acerca de la creación de puntos finales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: b72c3959b2a42c6a5abc8ef31975d5bdb9ce220e
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48781614"
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="1528a-102">Información general acerca de la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="1528a-102">Endpoint Creation Overview</span></span>
<span data-ttu-id="1528a-103">Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de la *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="1528a-104">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="1528a-104">Endpoints provide the clients access to the functionality that a WCF service offers.</span></span> <span data-ttu-id="1528a-105">Esta sección describe la estructura de un punto de conexión, y detalla cómo definir un punto de conexión en la configuración y el código.</span><span class="sxs-lookup"><span data-stu-id="1528a-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="1528a-106">Estructura de un extremo</span><span class="sxs-lookup"><span data-stu-id="1528a-106">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="1528a-107">Cada punto de conexión contiene una dirección que indica dónde se encuentra el punto de conexión, un enlace que especifica cómo puede comunicarse un cliente con el punto de conexión, y un contrato que identifica los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="1528a-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>  
  
-   <span data-ttu-id="1528a-108">**Dirección**.</span><span class="sxs-lookup"><span data-stu-id="1528a-108">**Address**.</span></span> <span data-ttu-id="1528a-109">La dirección identifica únicamente el punto de conexión e indica a los consumidores potenciales dónde se ubica el servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="1528a-110">Se representa en el modelo de objetos WCF mediante el <xref:System.ServiceModel.EndpointAddress> dirección, que contiene un identificador uniforme de recursos (URI) y las propiedades de dirección que incluyen una identidad, algunos elementos de lenguaje de descripción de servicios Web (WSDL) y una colección de opcional encabezados.</span><span class="sxs-lookup"><span data-stu-id="1528a-110">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="1528a-111">Los encabezados opcionales proporcionan información de direccionamiento adicional para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1528a-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="1528a-112">Para obtener más información, consulte [especificando una dirección de extremo](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="1528a-112">For more information, see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="1528a-113">**Enlace**.</span><span class="sxs-lookup"><span data-stu-id="1528a-113">**Binding**.</span></span> <span data-ttu-id="1528a-114">El enlace especifica cómo comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1528a-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="1528a-115">El enlace especifica cómo se comunica el punto de conexión con el mundo, incluido el protocolo de transporte que utiliza (por ejemplo, TCP o HTTP), la codificación utilizada en los mensajes (por ejemplo, texto o binario) y los requisitos de seguridad necesarios (por ejemplo, capa de sockets seguros [SSL] o seguridad del mensaje SOAP).</span><span class="sxs-lookup"><span data-stu-id="1528a-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="1528a-116">Para obtener más información, consulte [uso de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1528a-116">For more information, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
-   <span data-ttu-id="1528a-117">**Contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="1528a-117">**Service contract**.</span></span> <span data-ttu-id="1528a-118">El contrato de servicios describe qué funcionalidad expone el punto de conexión al cliente.</span><span class="sxs-lookup"><span data-stu-id="1528a-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="1528a-119">Un contrato especifica las operaciones a las que puede llamar un cliente, la forma del mensaje y el tipo de parámetros de entrada o los datos necesarios para llamar a la operación, así como el tipo de mensaje de procesamiento o respuesta que puede esperar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1528a-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="1528a-120">Existen tres tipos básicos de contratos que se corresponden con los patrones de intercambio de mensajes básicos (MEP): datagrama (unidireccional), solicitud/respuesta y dúplex (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="1528a-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="1528a-121">El contrato de servicio también puede emplear contratos de datos y mensajes para exigir tipos de datos y formatos de mensaje específicos cuando se obtiene acceso.</span><span class="sxs-lookup"><span data-stu-id="1528a-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="1528a-122">Para obtener más información sobre cómo definir un contrato de servicio, consulte [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="1528a-122">For more information about how to define a service contract, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span> <span data-ttu-id="1528a-123">Tenga en cuenta que también pueden exigírsele a un cliente que implemente un contrato definido por servicio, denominado un contrato de devolución de llamada, para recibir los mensajes del servicio en un MEP dúplex.</span><span class="sxs-lookup"><span data-stu-id="1528a-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="1528a-124">Para obtener más información, consulte [servicios dúplex](../../../docs/framework/wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="1528a-124">For more information, see [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="1528a-125">El punto de conexión de un servicio puede especificarse de manera imperativa, mediante el código, o de manera declarativa a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="1528a-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="1528a-126">Si no se especifica ningún extremo, el tiempo de ejecución proporciona extremos predeterminados, agregando uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="1528a-127">Normalmente, no resulta muy práctico definir los extremos en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="1528a-128">Generalmente, es más práctico definir extremos de servicio mediante la configuración en lugar del código.</span><span class="sxs-lookup"><span data-stu-id="1528a-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="1528a-129">Mantener la información del enlace y el direccionamiento fuera del código les permite cambiar sin tener que recompilar e implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1528a-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1528a-130">Cuando se agrega un extremo de servicio que realiza la suplantación, debe utilizarse uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>, o el método <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> para cargar correctamente el contrato en un nuevo objeto <xref:System.ServiceModel.Description.ServiceDescription>.</span><span class="sxs-lookup"><span data-stu-id="1528a-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>  
  
## <a name="defining-endpoints-in-code"></a><span data-ttu-id="1528a-131">Definir los extremos en código</span><span class="sxs-lookup"><span data-stu-id="1528a-131">Defining Endpoints in Code</span></span>  
 <span data-ttu-id="1528a-132">El siguiente ejemplo muestra cómo especificar un punto de conexión en código:</span><span class="sxs-lookup"><span data-stu-id="1528a-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>  
  
-   <span data-ttu-id="1528a-133">Defina un contrato para un `IEcho` tipo de servicio que acepta el nombre de alguien y eco con la respuesta "Hello \<nombre >!".</span><span class="sxs-lookup"><span data-stu-id="1528a-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>  
  
-   <span data-ttu-id="1528a-134">Implemente un servicio `Echo` del tipo definido por el contrato `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="1528a-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>  
  
-   <span data-ttu-id="1528a-135">Especifique una dirección de punto de conexión de `http://localhost:8000/Echo` para el servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-135">Specify an endpoint address of `http://localhost:8000/Echo` for the service.</span></span>  
  
-   <span data-ttu-id="1528a-136">Configure el servicio `Echo` mediante un enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="1528a-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  <span data-ttu-id="1528a-137">El host del servicio se crea con una dirección base y, a continuación, se especifica el resto de la dirección, relacionada con la dirección base, como parte de un extremo.</span><span class="sxs-lookup"><span data-stu-id="1528a-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="1528a-138">Esta subdivisión de la dirección permite definir varios extremos de manera más conveniente para los servicios de un host.</span><span class="sxs-lookup"><span data-stu-id="1528a-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1528a-139">Las propiedades de <xref:System.ServiceModel.Description.ServiceDescription> en la aplicación de servicio no deben modificarse después del método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="1528a-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="1528a-140">Algunos miembros, como la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> y los métodos `AddServiceEndpoint` en <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.ServiceHost>, inician una excepción si se modifican pasado ese punto.</span><span class="sxs-lookup"><span data-stu-id="1528a-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="1528a-141">Otros permiten modificarlos, pero el resultado no está definido.</span><span class="sxs-lookup"><span data-stu-id="1528a-141">Others permit you to modify them, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="1528a-142">De igual forma, en el cliente no se deben modificar los valores <xref:System.ServiceModel.Description.ServiceEndpoint> después de la llamada a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ChannelFactory>.</span><span class="sxs-lookup"><span data-stu-id="1528a-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="1528a-143">La propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> inicia una excepción si se modifican pasado ese punto.</span><span class="sxs-lookup"><span data-stu-id="1528a-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="1528a-144">Los otros valores de descripción del cliente pueden modificarse sin el error, pero el resultado no está definido.</span><span class="sxs-lookup"><span data-stu-id="1528a-144">The other client description values can be modified without error, but the result is undefined.</span></span>  
>   
>  <span data-ttu-id="1528a-145">Tanto si es para el servicio como para el cliente, se recomienda modificar la descripción antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="1528a-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="1528a-146">Definir los extremos en configuración</span><span class="sxs-lookup"><span data-stu-id="1528a-146">Defining Endpoints in Configuration</span></span>  
 <span data-ttu-id="1528a-147">Con frecuencia al crear una aplicación se desea delegar las decisiones al administrador que está implementando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1528a-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="1528a-148">Por ejemplo, es habitual que no pueda saberse de antemano cuál será la dirección de servicio (una URI).</span><span class="sxs-lookup"><span data-stu-id="1528a-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="1528a-149">En lugar de incluir una dirección en el código, es preferible permitir a un administrador hacerlo después de crear un servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="1528a-150">Esta flexibilidad se logra a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="1528a-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="1528a-151">Para obtener más información, consulte [configurar Services](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="1528a-151">For details, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1528a-152">Use la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con el `/config:` *filename*`[,`*filename* `]` cambiar a crear rápidamente archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="1528a-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>  
  
## <a name="using-default-endpoints"></a><span data-ttu-id="1528a-153">Usar puntos de conexión predeterminados</span><span class="sxs-lookup"><span data-stu-id="1528a-153">Using Default Endpoints</span></span>  
 <span data-ttu-id="1528a-154">Si no se especifica ningún extremo en el código ni en la configuración, el tiempo de ejecución proporciona extremos predeterminados, agregando uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="1528a-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="1528a-155">La dirección base se puede especificar en el código o en la configuración, y los extremos predeterminados se agregan al llamar al método <xref:System.ServiceModel.ICommunicationObject.Open> en el objeto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1528a-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1528a-156">Este ejemplo es el mismo que el de la sección anterior, pero como no se han especificado extremos, se agregan los predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1528a-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 <span data-ttu-id="1528a-157">Si se proporcionan extremos de forma explícita, es posible agregar extremos predeterminados llamando a <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> en el objeto <xref:System.ServiceModel.ServiceHost> antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="1528a-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="1528a-158">Para obtener más información sobre los puntos de conexión predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1528a-158">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1528a-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="1528a-159">See Also</span></span>  
 [<span data-ttu-id="1528a-160">Implementación de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="1528a-160">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
