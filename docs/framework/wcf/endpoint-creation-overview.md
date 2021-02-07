---
description: 'Más información sobre: Introducción a la creación de puntos de conexión'
title: Información general acerca de la creación de puntos finales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: ff806428922f2097f0d570118d6b5f7836c1797b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756830"
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="0f815-103">Información general acerca de la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="0f815-103">Endpoint Creation Overview</span></span>

<span data-ttu-id="0f815-104">Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de los *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="0f815-105">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="0f815-105">Endpoints provide the clients access to the functionality that a WCF service offers.</span></span> <span data-ttu-id="0f815-106">Esta sección describe la estructura de un punto de conexión, y detalla cómo definir un punto de conexión en la configuración y el código.</span><span class="sxs-lookup"><span data-stu-id="0f815-106">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="0f815-107">Estructura de un extremo</span><span class="sxs-lookup"><span data-stu-id="0f815-107">The Structure of an Endpoint</span></span>

<span data-ttu-id="0f815-108">Cada punto de conexión contiene una dirección que indica dónde se encuentra el punto de conexión, un enlace que especifica cómo puede comunicarse un cliente con el punto de conexión, y un contrato que identifica los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="0f815-108">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>

- <span data-ttu-id="0f815-109">**Dirección**.</span><span class="sxs-lookup"><span data-stu-id="0f815-109">**Address**.</span></span> <span data-ttu-id="0f815-110">La dirección identifica únicamente el punto de conexión e indica a los consumidores potenciales dónde se ubica el servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-110">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="0f815-111">Se representa en el modelo de objetos WCF mediante la <xref:System.ServiceModel.EndpointAddress> dirección, que contiene un identificador uniforme de recursos (URI) y propiedades de dirección que incluyen una identidad, algunos elementos del lenguaje de descripción de servicios web (WSDL) y una colección de encabezados opcionales.</span><span class="sxs-lookup"><span data-stu-id="0f815-111">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="0f815-112">Los encabezados opcionales proporcionan información de direccionamiento adicional para identificar o interactuar con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0f815-112">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="0f815-113">Para obtener más información, vea [especificar una dirección de extremo](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="0f815-113">For more information, see [Specifying an Endpoint Address](specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="0f815-114">**Enlace**.</span><span class="sxs-lookup"><span data-stu-id="0f815-114">**Binding**.</span></span> <span data-ttu-id="0f815-115">El enlace especifica cómo comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0f815-115">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="0f815-116">El enlace especifica cómo se comunica el punto de conexión con el mundo, incluido el protocolo de transporte que utiliza (por ejemplo, TCP o HTTP), la codificación utilizada en los mensajes (por ejemplo, texto o binario) y los requisitos de seguridad necesarios (por ejemplo, capa de sockets seguros [SSL] o seguridad del mensaje SOAP).</span><span class="sxs-lookup"><span data-stu-id="0f815-116">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="0f815-117">Para obtener más información, consulte [uso de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0f815-117">For more information, see [Using Bindings to Configure Services and Clients](using-bindings-to-configure-services-and-clients.md).</span></span>

- <span data-ttu-id="0f815-118">**Contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="0f815-118">**Service contract**.</span></span> <span data-ttu-id="0f815-119">El contrato de servicios describe qué funcionalidad expone el extremo al cliente.</span><span class="sxs-lookup"><span data-stu-id="0f815-119">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="0f815-120">Un contrato especifica las operaciones a las que puede llamar un cliente, la forma del mensaje y el tipo de parámetros de entrada o los datos necesarios para llamar a la operación, así como el tipo de mensaje de procesamiento o respuesta que puede esperar el cliente.</span><span class="sxs-lookup"><span data-stu-id="0f815-120">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="0f815-121">Existen tres tipos básicos de contratos que se corresponden con los patrones de intercambio de mensajes básicos (MEP): datagrama (unidireccional), solicitud/respuesta y dúplex (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="0f815-121">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="0f815-122">El contrato de servicio también puede emplear contratos de datos y mensajes para exigir tipos de datos y formatos de mensaje específicos cuando se obtiene acceso.</span><span class="sxs-lookup"><span data-stu-id="0f815-122">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="0f815-123">Para obtener más información sobre cómo definir un contrato de servicios, consulte [diseño de contratos](designing-service-contracts.md)de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-123">For more information about how to define a service contract, see [Designing Service Contracts](designing-service-contracts.md).</span></span> <span data-ttu-id="0f815-124">Tenga en cuenta que también pueden exigírsele a un cliente que implemente un contrato definido por servicio, denominado un contrato de devolución de llamada, para recibir los mensajes del servicio en un MEP dúplex.</span><span class="sxs-lookup"><span data-stu-id="0f815-124">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="0f815-125">Para obtener más información, vea [servicios dúplex](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f815-125">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>

<span data-ttu-id="0f815-126">El punto de conexión de un servicio puede especificarse de manera imperativa, mediante el código, o de manera declarativa a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0f815-126">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="0f815-127">Si no se especifica ningún extremo, el tiempo de ejecución proporciona extremos predeterminados, agregando uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-127">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="0f815-128">Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-128">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="0f815-129">Generalmente, es más práctico definir extremos de servicio mediante la configuración en lugar del código.</span><span class="sxs-lookup"><span data-stu-id="0f815-129">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="0f815-130">Mantener la información del enlace y el direccionamiento fuera del código les permite cambiar sin tener que recompilar e implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f815-130">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>

> [!NOTE]
> <span data-ttu-id="0f815-131">Cuando se agrega un extremo de servicio que realiza la suplantación, debe utilizarse uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>, o el método <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> para cargar correctamente el contrato en un nuevo objeto <xref:System.ServiceModel.Description.ServiceDescription>.</span><span class="sxs-lookup"><span data-stu-id="0f815-131">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>

## <a name="defining-endpoints-in-code"></a><span data-ttu-id="0f815-132">Definir los extremos en código</span><span class="sxs-lookup"><span data-stu-id="0f815-132">Defining Endpoints in Code</span></span>

<span data-ttu-id="0f815-133">El siguiente ejemplo muestra cómo especificar un extremo en código:</span><span class="sxs-lookup"><span data-stu-id="0f815-133">The following example illustrates how to specify an endpoint in code with the following:</span></span>

- <span data-ttu-id="0f815-134">Defina un contrato para un `IEcho` tipo de servicio que acepte el nombre de alguien y echo con la respuesta "Hello \<name> !".</span><span class="sxs-lookup"><span data-stu-id="0f815-134">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>

- <span data-ttu-id="0f815-135">Implemente un servicio `Echo` del tipo definido por el contrato `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="0f815-135">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>

- <span data-ttu-id="0f815-136">Especifique una dirección de extremo de `http://localhost:8000/Echo` para el servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-136">Specify an endpoint address of `http://localhost:8000/Echo` for the service.</span></span>

- <span data-ttu-id="0f815-137">Configure el servicio `Echo` mediante un enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="0f815-137">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>

```csharp
namespace Echo
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
> <span data-ttu-id="0f815-138">El host del servicio se crea con una dirección base y, a continuación, se especifica el resto de la dirección, relacionada con la dirección base, como parte de un extremo.</span><span class="sxs-lookup"><span data-stu-id="0f815-138">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="0f815-139">Esta subdivisión de la dirección permite definir varios extremos de manera más conveniente para los servicios de un host.</span><span class="sxs-lookup"><span data-stu-id="0f815-139">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>

> [!NOTE]
> <span data-ttu-id="0f815-140">Las propiedades de <xref:System.ServiceModel.Description.ServiceDescription> en la aplicación de servicio no deben modificarse después del método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="0f815-140">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="0f815-141">Algunos miembros, como la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> y los métodos `AddServiceEndpoint` en <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.ServiceHost>, inician una excepción si se modifican pasado ese punto.</span><span class="sxs-lookup"><span data-stu-id="0f815-141">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="0f815-142">Otros permiten modificarlos, pero el resultado no está definido.</span><span class="sxs-lookup"><span data-stu-id="0f815-142">Others permit you to modify them, but the result is undefined.</span></span>
>
> <span data-ttu-id="0f815-143">De igual forma, en el cliente no se deben modificar los valores <xref:System.ServiceModel.Description.ServiceEndpoint> después de la llamada a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ChannelFactory>.</span><span class="sxs-lookup"><span data-stu-id="0f815-143">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="0f815-144">La propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> inicia una excepción si se modifican pasado ese punto.</span><span class="sxs-lookup"><span data-stu-id="0f815-144">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="0f815-145">Los otros valores de descripción del cliente pueden modificarse sin el error, pero el resultado no está definido.</span><span class="sxs-lookup"><span data-stu-id="0f815-145">The other client description values can be modified without error, but the result is undefined.</span></span>
>
> <span data-ttu-id="0f815-146">Tanto si es para el servicio como para el cliente, se recomienda modificar la descripción antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f815-146">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>

## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="0f815-147">Definir los puntos de conexión en configuración</span><span class="sxs-lookup"><span data-stu-id="0f815-147">Defining Endpoints in Configuration</span></span>

<span data-ttu-id="0f815-148">Con frecuencia al crear una aplicación se desea delegar las decisiones al administrador que está implementando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f815-148">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="0f815-149">Por ejemplo, es habitual que no pueda saberse de antemano cuál será la dirección de servicio (una URI).</span><span class="sxs-lookup"><span data-stu-id="0f815-149">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="0f815-150">En lugar de incluir una dirección en el código, es preferible permitir a un administrador hacerlo después de crear un servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-150">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="0f815-151">Esta flexibilidad se logra a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0f815-151">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="0f815-152">Para obtener más información, vea [configuración de servicios](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f815-152">For details, see [Configuring Services](configuring-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0f815-153">Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) con el modificador nombre de archivo `/config:`  `[,`  `]` para crear rápidamente archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="0f815-153">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>

## <a name="using-default-endpoints"></a><span data-ttu-id="0f815-154">Usar puntos de conexión predeterminados</span><span class="sxs-lookup"><span data-stu-id="0f815-154">Using Default Endpoints</span></span>

<span data-ttu-id="0f815-155">Si no se especifica ningún extremo en el código ni en la configuración, el tiempo de ejecución proporciona extremos predeterminados, agregando uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="0f815-155">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="0f815-156">La dirección base se puede especificar en el código o en la configuración, y los extremos predeterminados se agregan al llamar al método <xref:System.ServiceModel.ICommunicationObject.Open> en el objeto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0f815-156">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="0f815-157">Este ejemplo es el mismo que el de la sección anterior, pero como no se han especificado puntos de conexión, se agregan los predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0f815-157">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   public class Echo : IEcho
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

 <span data-ttu-id="0f815-158">Si se proporcionan puntos de conexión de forma explícita, es posible agregar puntos de conexión predeterminados llamando a <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> en el objeto <xref:System.ServiceModel.ServiceHost> antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f815-158">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="0f815-159">Para obtener más información sobre los puntos de conexión predeterminados, vea [configuración simplificada](simplified-configuration.md) y [configuración simplificada para servicios WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f815-159">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f815-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f815-160">See also</span></span>

- [<span data-ttu-id="0f815-161">Implementación de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="0f815-161">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
