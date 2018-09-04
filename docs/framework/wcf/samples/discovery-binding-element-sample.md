---
title: Ejemplo de elemento de enlace de detección
ms.date: 03/30/2017
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
ms.openlocfilehash: d906d9a389c50095f2af5d52e3874c3e43199e68
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535782"
---
# <a name="discovery-binding-element-sample"></a><span data-ttu-id="dcdc2-102">Ejemplo de elemento de enlace de detección</span><span class="sxs-lookup"><span data-stu-id="dcdc2-102">Discovery Binding Element Sample</span></span>
<span data-ttu-id="dcdc2-103">En este ejemplo se muestra cómo utilizar el elemento de enlace de cliente de detección para detectar un servicio.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-103">This sample demonstrates how to use the discovery client binding element to discover a service.</span></span> <span data-ttu-id="dcdc2-104">Esta característica permite a los desarrolladores de software agregar un canal de cliente de detección a su pila del canal de clientes existente, con lo que el modelo de programación resulta muy intuitivo.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-104">This feature enables developers to add a discovery client channel to their existing client channel stack, making the programming model very intuitive.</span></span> <span data-ttu-id="dcdc2-105">Cuando se abre el canal asociado, la dirección del servicio se resuelve utilizando la detección.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-105">When the associated channel is opened, the address of the service is resolved using discovery.</span></span> <span data-ttu-id="dcdc2-106">Este ejemplo consta de los siguientes proyectos:</span><span class="sxs-lookup"><span data-stu-id="dcdc2-106">This sample consists of the following projects:</span></span>  
  
-   <span data-ttu-id="dcdc2-107">**CalculatorService**: un servicio WCF reconocible.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-107">**CalculatorService**: A discoverable WCF service.</span></span>  
  
-   <span data-ttu-id="dcdc2-108">**CalculatorClient**: aplicación de cliente de WCF que utiliza el canal de cliente de detección para buscar y llamar a CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-108">**CalculatorClient**: A WCF client application that uses the discovery client channel to search for and call the CalculatorService.</span></span>  
  
-   <span data-ttu-id="dcdc2-109">**DynamicCalculatorClient**: aplicación de cliente de WCF que usa un extremo dinámico para buscar y llamar a CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-109">**DynamicCalculatorClient**: A WCF client application that uses a dynamic endpoint to search for and call the CalculatorService.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dcdc2-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dcdc2-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dcdc2-112">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dcdc2-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a><span data-ttu-id="dcdc2-114">CalculatorService</span><span class="sxs-lookup"><span data-stu-id="dcdc2-114">CalculatorService</span></span>  
 <span data-ttu-id="dcdc2-115">Este proyecto contiene un servicio de calculadora sencillo que implementa el contrato de la interfaz `ICalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-115">This project contains a simple calculator service that implements the `ICalculatorService` contract.</span></span>  
  
 <span data-ttu-id="dcdc2-116">El siguiente archivo App.config se utiliza para agregar un comportamiento `<serviceDiscovery>` en los comportamientos del servicio, así como el extremo de detección.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-116">The following App.config file is used to add a `<serviceDiscovery>` behavior in the service behaviors as well as the discovery endpoint.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="dcdc2-117">Esto hace que el servicio y sus extremos se puedan detectar.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-117">This makes the service and its endpoints discoverable.</span></span> <span data-ttu-id="dcdc2-118">CalculatorService es un servicio autohospedado que agrega un extremo mediante el enlace NetTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-118">The CalculatorService is a self-hosted service that adds one endpoint using the NetTcpBinding binding.</span></span> <span data-ttu-id="dcdc2-119">También agrega un `EndpointDiscoveryBehavior` al extremo y especifica un ámbito como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-119">It also adds an `EndpointDiscoveryBehavior` to the endpoint and specifies a scope as shown in the following code.</span></span>  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a><span data-ttu-id="dcdc2-120">CalculatorClient</span><span class="sxs-lookup"><span data-stu-id="dcdc2-120">CalculatorClient</span></span>  
 <span data-ttu-id="dcdc2-121">Este proyecto contiene una implementación del cliente que envía los mensajes a CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-121">This project contains a client implementation that sends messages to the CalculatorService.</span></span> <span data-ttu-id="dcdc2-122">Este programa utiliza el método `CreateCustomBindingWithDiscoveryElement()` para crear un enlace personalizado que utiliza el canal de cliente de detección.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-122">This program uses the `CreateCustomBindingWithDiscoveryElement()` method to create a custom binding that uses the Discovery Client Channel.</span></span>  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <span data-ttu-id="dcdc2-123">Una vez creado el objeto <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, el desarrollador de software especifica los criterios que se usan al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-123">After the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is instantiated, the developer specifies the criteria to use when searching for a service.</span></span> <span data-ttu-id="dcdc2-124">En este caso, el criterio de búsqueda de detección es el tipo de la interfaz `ICalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-124">In this case, the discovery find criterion is the `ICalculatorService` type.</span></span> <span data-ttu-id="dcdc2-125">Además, el desarrollador de software especifica un <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> que devuelve un <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> que especifica dónde buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-125">Additionally, the developer specifies a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> which returns a <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> that specifies where to look for the services.</span></span> <span data-ttu-id="dcdc2-126">El <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> devuelve una nueva instancia de <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-126">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> returns a new <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance.</span></span> <span data-ttu-id="dcdc2-127">Para obtener más información, consulte [mediante un enlace personalizado con el canal de cliente de detección](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="dcdc2-127">For more information, see [Using a Custom Binding with the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 <span data-ttu-id="dcdc2-128">En este caso, el cliente utiliza el mecanismo de multidifusión de UDP definido por el protocolo de detección para buscar los servicios en la subred local.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-128">In this case, the client uses the UDP multicast mechanism defined by the Discovery protocol to search for services on the local subnet.</span></span> <span data-ttu-id="dcdc2-129">El resto del método crea un enlace personalizado e inserta el elemento de enlace de detección en la parte superior de la pila.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-129">The remainder of the method creates a custom binding and inserts the Discovery binding element at the top of the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcdc2-130"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> se debe colocar en la parte superior de la pila de enlaces.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-130">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must be placed on the top of the binding stack.</span></span> <span data-ttu-id="dcdc2-131">El objeto <xref:System.ServiceModel.Channels.BindingElement> sobre <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> debe asegurarse de que el generador de canales o el canal que crea no use las propiedades `EndpointAddress` o `Via`, porque la dirección real solo se encuentra en el canal del cliente de detección.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-131">Any <xref:System.ServiceModel.Channels.BindingElement> on top of <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the channel factory or channel it creates does not use the `EndpointAddress` or `Via` properties, because the actual address is found only at the Discovery client channel.</span></span>  
  
 <span data-ttu-id="dcdc2-132">Después, se puede crear una instancia de `CalculatorClient` pasando este enlace personalizado así como una dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-132">Next, the `CalculatorClient` can be instantiated by passing in this custom binding as well as an endpoint address.</span></span>  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 <span data-ttu-id="dcdc2-133">Al usar el canal de cliente de detección, se pasa la dirección constante de extremo especificada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-133">When using the Discovery Client Channel, the constant endpoint address specified previously is passed in.</span></span> <span data-ttu-id="dcdc2-134">Ahora en tiempo de ejecución, el canal de cliente de detección encuentra el servicio especificado por los criterios de búsqueda y se conecta a él.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-134">Now at runtime, the Discovery Client Channel finds the service specified by the find criteria and connects to it.</span></span> <span data-ttu-id="dcdc2-135">Para que el servicio y el cliente establezcan una conexión, deben tener también la misma pila de enlaces subyacente.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-135">For the service and the client to establish a connection, they must also have the same underlying binding stack.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dcdc2-136">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcdc2-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="dcdc2-137">Abra la solución en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcdc2-137">Open the solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="dcdc2-138">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-138">Build the solution.</span></span>  
  
3.  <span data-ttu-id="dcdc2-139">Ejecute la aplicación de servicio y cada una de las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-139">Run the service application and each of the client applications.</span></span>  
  
4.  <span data-ttu-id="dcdc2-140">Observe que el cliente pudo encontrar el servicio sin conocer su dirección.</span><span class="sxs-lookup"><span data-stu-id="dcdc2-140">Observe that the client was able to find the service without knowing its address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcdc2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcdc2-141">See Also</span></span>
